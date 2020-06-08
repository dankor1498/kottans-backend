# GIT Short list

**git config --list** Вивести список конфігурації.

**git config --global core.editor "code --wait"** Налаштувати VSCode як редактор тексту.

**git init** Створити новий проект.

**git clone “URL” “newname”** Клонувати репозиторій з URL та по бажанню перейменувати.

**git status** Дізнатись статус ***(alias: st)***.

**git log** Вивести інформацію по комітах.

**git log --oneline** Вивести інформацію в короткому форматі ***(alias: lone)***.

**git log --oneline --decorate --graph --all** Показати інформацію в короткому форматі + всі вітки ***(alias: git hist)***.

**git log --stat** Вивести інформацію по комітах + кількість доданих/видалених рядків.

**git log -p** Вивести інформацію по комітах + фактичні зміни.

**git show “SHA”** Показати конкретний коміт.

**git add .** Перемісти всі файли зі змінами до Staging Index.

**git commit** Створити коміт з описом ***(alias: ci)***.

**git commit -m "Initial commit"** Швидко створити коміт ***(alias: com)***.

**git commit --amend** Перейменувати останній коміт.

**git diff** Переглянути зміни що були створені але не додані до Staging Index.

**git tag** Показати всі прапорці.

**git tag - a v1.0** Створює анотований прапорець що містить додаткову інформацію.

**git tag - d v1.0** Видалити прапорець.

**git branch** Показати всі вітки ***(alias: br)***.

**git branch “branch”** Створити нові вітку “branch”.

**git branch -d “branch”** Видалити вітку “branch”.

**git checkout “branch”** Перемкнутись на вітку “branch” ***(alias: co)***.

**git checkout -b “branch”** Перемкнутись і створити вітку “branch”.

**git merge <name-of-branch-to-merge-in>** Змерджити вітки.

**git revert <SHA-of-commit-to-revert>** Відмінити зміни коміта + створити новий коміт для запису змін.

**git reset <reference-to-commit>** Видалити коміт.

**git reset --mixed <reference-to-commit>** Видалити коміт до рівня робочої папки.

**git reset --soft <reference-to-commit>** Видалити коміт до рівня Staging Index.

**git reset --hard <reference-to-commit>** Видалити коміт майже назавжди і всі наступні.

**HEAD^** Вказує на батьківський коміт.

**HEAD~** Вказує на перший батьківський коміт.

**.gitignore** Файл для файлів що будуть ігноруватись:
- blank lines can be used for spacing
- \# - marks line as a comment
- \* - matches 0 or more characters
- ? - matches 1 character
- [abc] - matches a, b, _or_ c
- \*\* - matches nested directories - a/**/z matches
  - a/z
  - a/b/z
  - a/b/c/z