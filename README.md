# Kottans Backend Course

## Korotych Danyil

#### 1. [Git and GitHub](https://github.com/kottans/backend/blob/master/tasks/git-intro.md):

- Learned Git basic syntax.
- Learned the basics of work with GitHub.
- Created the Git repository.
- Learned the basics of [Markdown](https://www.markdownguide.org/basic-syntax/#links) syntax.
- Learned to work with branches and make pull-requests.
- Created my [Git Shortlist](https://github.com/dankor1498/kottans-backend/blob/master/GitShortlist.md).

#### 2. [Unix Shell](https://github.com/kottans/backend/blob/master/tasks/unix-shell.md):

- Learned basic bash commands.
- Added my [Bash Shortlist](https://github.com/dankor1498/kottans-backend/blob/master/task_unix_shell/BashShortlist.pdf).
- Started to use bash commands in my terminal.

#### 3. [Git for Team Collaboration](https://github.com/kottans/backend/blob/master/tasks/git-collaboration.md):

- Learned the basics of working with GitHub.
- Updated my [Git Shortlist](https://github.com/dankor1498/kottans-backend/blob/master/GitShortlist.md).

#### 4. [JavaScript & NodeJS Basics. Part I](https://github.com/kottans/backend/blob/master/tasks/js_basics_1.md):

- Completed the courses:
  - [learnyounode](https://github.com/workshopper/learnyounode)
  - [functional-javascript-workshop](https://github.com/timoxley/functional-javascript-workshop)
  - [stream adventure](https://github.com/workshopper/stream-adventure)
- Created useful notes:
  - [Async Loops](https://github.com/dankor1498/kottans-backend/blob/master/node_basic_1/Async_loops.md)
  - [The JavaScript Event Loop](https://github.com/dankor1498/kottans-backend/blob/master/node_basic_1/Blocking_event_loop.md)
  - [Trampoline functions](https://github.com/dankor1498/kottans-backend/blob/master/node_basic_1/Trampoline_functions.md)

#### 4. [Program in Memory](https://github.com/kottans/backend/blob/master/tasks/memory-management.md):

- What's going to happen if program reaches maximum limit of stack?<br>
  It is possible to exhaust the area mapping the stack by pushing more data than it can fit. If the maximum stack size has been reached, we have a stack overflow and the program receives a Segmentation Fault. While the mapped stack area expands to meet demand, it does not shrink back when the stack gets smaller.

- What's going to happen if program requests a big (more then 128KB) memory allocation on heap?<br>
  If there is enough space in the heap to satisfy a memory request, it can be handled by the language runtime without kernel involvement. Otherwise, the heap is enlarged system call (implementation) to make room for the requested block.

- What's the difference between Text and Data memory segments?<br>
  The code segment, also known as text segment contains the machine instructions of the program. The code can be thought of like the text of a novel: It tells the story of what the program does.<br>
  The data segment contains the static data of the program, i.e. the variables that exist throughout program execution. Global variables in a C or C++ program are static, as are variables declared as static in C, C++, or Java.
