## Асинхронні цикли
### Async Loops

**Ціль:** Для коректного виклуку асинхронної функції та функцій що від неї залежать.

**Проблема:**

```js
function loadUsers(userIds, load, done) {
  var users = [];
  for (var i = 0; i < userIds.length; i++) {
    users.push(load(userIds[i]));
  }
  return users;
}
```
Для тестування такої функції підготуємо наступні дані:
```js
function load(id, callback) {
  console.log(`Loading user ${id}...`);
  setTimeout(() => {
    console.log(`User ${id} is loaded.`);
    callback({ name: `User ${id}`, ID: id });
  }, 3000);
}

function done(users) {
  console.log("-------Done function-------");
  users.forEach((user) => console.log(`Name: ${user.name}, ID: ${user.ID}`));
}

loadUsers([135, 256, 311, 104, 523, 697], load, done);
```
Функція ***load*** створює видимість завантаження користувачів і у випадку успіху викликає callback з підготовленими даними.

Функція ***done*** отримує масив підготовлених юзерів та виводить їх на консоль.

Функція ***load*** - асинхронна. Це означає, що в результуючий масив ***users*** можуть бути не записані дані. Відповідно викликати функцію ***done*** немає сенсу, адже дані не будуть коректно підготовлені.

**Рішення 1:**

```js
function loadUsers(userIds, load, done) {
  var completed = 0;
  var users = [];
  userIds.forEach(function (id, index) {
    load(id, function (user) {
      users[index] = user;
      if (++completed === userIds.length) return done(users);
    });
  });
}
```
Цикл ***for*** не очікує завершення асинхронної операції, перш ніж перейти до наступної ітерації циклу, саме тому ми використовуємо функцію ***forEach*** яка містить власну функцію закриття. Функція ***done*** буде викликана лише тоді, коли весь масив буде опрацьований а дані - правильно підготовлені.

Це рішення дієве, проте є набагато сучасніший спосіб.

**Рішення 2:**

```js
async function loadUsers(userIds, load, done) {
  let promises = userIds.map((user) => load(user));
  let users = await Promise.all(promises);
  done(users);
}

function loadPromise(id) {
  return new Promise((resolve) => {
    load(id, (user) => {
      resolve(user);
    });
  });
}

loadUsers([135, 256, 311, 104, 523, 697], loadPromise, done);
```
Сучасний синтаксис дозволяє використовувати асинхронні функції, що дозволяє значно вкоротити код. ***await*** буде очікувати виконання Promise, тому, за необхідності, функцію необхідно змінити, щоб вона вертала Promise. Саме для цього створена функція ***loadPromise*** яка обертає функцію ***load*** в Promise. За допомогою ***map*** ми створюємо масив промісів та одночасно запускаємо їх в ***Promise.all***. Ця функція гарантує правильний порядок результатів та коректність завантажених даних. Завдяки ***await*** всі дані будуть завантажені в масив ***users***. 

Перевагою даних методів є паралельність завантажень, хоча при великій кількості даних це може бути негативним фактором.