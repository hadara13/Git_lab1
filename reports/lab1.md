# Git_lab1 
##  *Этап 1 :  Установка и настройка Git*  
 ### 1. Проверка установки Git
- Установите программу [git](https://git-scm.com/install/windows).
- После установки откройте свой терминал и введите следующую команду: `git --version `.
**Вывод:**
git version 2.40.0.windows.1
    **Описание:**
Проверил, что Git установлен и доступен в командной строке. Убедился в версии программы.
## 2. Настройка имени пользователя и email
**Команды:** 
```git
. git config --global user.name "Name"
. git config --global user.email "@email" 
```
**Проверка настроек:**
`git config --list`
**Описание:**
Задал глобальные настройки Git: имя пользователя и адрес электронной почты. Эти данные будут использоваться для подписи коммитов.

## 3. Изучение основных команд Git
**Команда:** 
``git --help``
**Описание:**
Вывел список всех доступных команд Git. Для получения подробной информации о конкретной команде можно использовать `git <команда> --help.`
# *Этап 2 : Начало работы с новым проектом*
### 1. Создание директории проекта и инициализация репозитория
**Команды:**
```bash
# Создаем новую директорию для проекта
mkdir my_project

# Переходим в созданную директорию
cd my_project

# Инициализируем новый Git репозиторий
git init
```
**Вывод `git init` :** Initialized empty Git repository in path/my_project/.git/
**Описание:** 
Создал новую папку my_project, перешел в нее и инициализировал пустой Git репозиторий. Появилась скрытая папка .git, где Git будет хранить всю историю изменений.
### 2. Создание файлов и директорий :
**Команды:**
``` bash 
#Создаем файл README.md в корне проекта
New-Item README.md -ItemType File

#Создаем директорию reports 
mkdir reports

#Создаем файл lab1.md внутри директории reports
New-Item lab1.md -ItemType File
```
**Описание:**
Создал файл `README.md` в корне проекта и файл отчета `reports/lab1.md`. Структура проекта готова для работы.
_______________________________________________________________
**Что такое Markdown**? *Markdown* — это облегчённый язык разметки, который создан для форматирования текста с использованием простых символов. Он легко читается в исходном виде и преобразуется в HTML .
### Основные элементы Markdown
| Элемент | Синтаксис | Результат |
|---------|-----------|-----------|
| **Заголовки** | `# H1`<br>`## H2`<br>`### H3` | **Заголовки разных уровней** |
| **Жирный текст** | `**жирный текст**` | **жирный текст** |
| **Курсив** | `*курсив*` | *курсив* |
| **Зачёркнутый** | `~~текст~~` | ~~текст~~ |
| **Ссылки** | `[текст](https://example.com)` | [текст](https://example.com) |
| **Изображения** | `![alt текст](image.jpg)` | (изображение) |
| **Код** | `` `код` `` | `код` |
| **Блок кода** | \```язык<br>код<br>\``` | (блок с подсветкой) |
| **Цитаты** | `> текст цитаты` | > текст цитаты |
| **Горизонтальная линия** | `---` или `***` | ——— |
Полезные ссылки для изучения _Markdown_
. https://www.youtube.com/watch?v=NX1Sht1tAA0&t=59s 
. https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#headings
### 3. Написать в файле `README.md` заголовок, информацию о дисциплине и о нас.

```
# My_Git_Lab1 

## О проекте
Этот проект создан для выполнения лабораторной работы по дисциплине ""Современные технологии разработки ПО".

## Об авторе
- **Студент:** Haydara Saleh
- **Группа:** 5130203/50001
- **Дата:** 2026
```
### 4. Создать коммит с файлами
 *__Важная рекомендация перед коммитом__* 
 Всегда проверяйте состояние репозитория!
Перед тем как сделать коммит, настоятельно рекомендуется выполнить команду:
`git status`

**Вывод:**
``` 
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        reports/
``` 
***Видим, что файлы не отслеживаются***

- __Добавляем файлы:__
`git add README.md`
`git add reports/lab1.md`
- ***Проверка ПОСЛЕ добавления:***
`git status`

**Вывод:**
```
PS C:\Users\Shaam\Desktop\my_project> git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
        new file:   reports/lab1.md
```
- **Делаем коммит:**
`git commit -m "the files are commited"`
 
**Вывод:**
```
[master (root-commit) 15c87d3] FIRST COMMIT IS DONE
 2 files changed, 9 insertions(+)
 create mode 100644 README.md
 create mode 100644 reports/lab1.md
```
## *Этап 3: Отслеживание состояния кода*
### 1. Первое использование git status и git diff
**Команды:**
```
# Проверяем состояние репозитория
git status
```
**Результат:**
```
On branch master
nothing to commit, working tree clean
```
**Описание:**
- `git status` показывает текущее состояние рабочей директории и индекса. Сейчас рабочая директория чистая (clean) — нет изменений для коммита.
- `git diff` показывает различия между рабочим каталогом и индексом (staging area). Так как изменений нет, команда ничего не выводит.
EOF.
### 2. Использование git status и git diff после добавления описания в отчет
После добавления нового раздела в файл `reports/lab1.md`, я выполнил **команду**:
`git status`

**Результат:**
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   reports/lab1.md

no changes added to commit (use "git add" and/or "git commit -a")
```
**Что показывает `git status` ?**
- Файл reports/lab1.md был изменен (modified).
- Изменения не добавлены в индекс (staging area).
- Git предлагает использовать git add для добавления файла или git restore для отмены изменений.
**командa:**
`git diff` 

**Результат:**
```
Строки с + (зелёные) — это добавленный текст

Строки с - (красные) — это удалённый текст
```
**Что показывает `git diff` ?**
- Какой файл я менял: Я работал над файлом reports/lab1.md — это мой отчёт по лабораторной работе.
### 3. Добавление изменений в индекс
**Команда:**
```
git add reports/lab1.md
git status
```
**Результат:**
```
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   reports/lab1.md
```
**Описание:**
После git add файл reports/lab1.md находится в индексе (staging area) и готов к коммиту.
### 4. Изменения в `README.md`
Я открыл файл ,
и внёс изменения

**Описание:**
`git diff README.md` показывает изменения только в указанном файле.
### 5. Коммит только `lab1.md`
**Команда:**
 ```
 git commit -m "new version of lab1.md"
```
**Результат:**
```
[master d2c9460] Обновлен отчет lab1.md
 1 file changed, 15 insertions(+)
```
**Результат** `git status`:
```
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

**Описание:**
Коммит создан только для файла `reports/lab1.md`**.**` README.md` остался измененным, но не добавленным в индекс.

## *Этап 4: Откат изменений*
### 1. Проверка незакоммиченных изменений в `README`.md
Перед откатом убедимся, что в файле`README.md` есть незакоммиченные изменения:
``` bash 
PS C:\Users\Shaam\Desktop\my_project> git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
### 2. Откат изменений в `README.md` с помощью `git restore`
Отменяем изменения в файле `README.md`:
```
git restore README.md 
```
Проверяем, что изменения исчезли:
```
git status

\Users\Shaam\Desktop\my_project> git status
On branch master
nothing to commit, working tree clean


# to read what is written in the file 
cat README.md
```
**Описание:** Команда `git restore README.md` полностью отменила все изменения в файле, вернув его к состоянию последнего коммита.
### 3. Удаление файла reports/lab1.md
```
# Сначала создадим резервную копию 
cp reports/lab1.md reports/lab1.md.backup

# Удаляем файл
rm reports/lab1.md


# Проверка удаления:
ls reports/
```
**Результат:**  `lab1.md.backup`
 ### 4. Выполнить команду `git status` и объяснить ее вывод.
 ```
 git status
 
 # Результат
 >>> On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    reports/lab1.md
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        reports/lab1.md.backup
 ```
  **Описание:**
 - deleted: reports/lab1.md — Git обнаружил, что файл `lab1.md` был удален. Он отслеживался Git, поэтому удаление отображается как изменение.
- Untracked files: reports/lab1.md.backup — резервная копия файла, которую Git видит, но не отслеживает (новый файл).
- Git предлагает два варианта для удаленного файла:
 **`git add`** — зафиксировать удаление (удалить из репозитория)
**`git restore`** — восстановить файл

### 5.  Восстановление удаленного файла
`git restore reports/lab1.md`
 
 **Проверка состояния после восстановления:**
 `git status`
**Результат:** 
```
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        reports/lab1.md.backup

no changes added to commit (use "git add" and/or "git commit -a")
```
 **Проверка наличия файла:**
`ls reports/`
**Результат:**
```
lab1.md  lab1.md.backup
```
**Объяснение:**
 - Команда git restore reports/lab1.md восстановила удаленный файл из последнего коммита
 - Файл `lab1.md` снова появился в директории reports/
 - Git больше не показывает deleted:
**reports/lab1.md** в статусе
 - Резервная копия lab1.md.backup осталась как untracked file (неотслеживаемый файл)
 
## *Этап 5: Ветвление версий*
### 1. Вывод имени текущей ветки
Для просмотра текущей ветки используется **команда**:
` git branch`
*Эта команда показывает список всех веток. Текущая ветка отмечена символом*
**вывод : **
` * master `
### 2. Создание новой ветки 
` git branch lab1-1 `
**Проверка состояния после восстановления:**
`git branch`

**Результат:**
```
  lab1-1
* master
```
### 3. Переключение на новую ветку
Переключимся на созданную ветку:
` git checkout lab1-1 `
**Результат:**
```
Switched to branch 'lab1-1'
```
Проверим, что переключение прошло успешно:
` git status `
**Результат:**
```
* lab1-1
  master
```
** изменения есть в файлах ?**
Сначала я открыл файл README.md и вручную добавил изменения.
С помощью команды `git status` можно увидеть, что в файле есть изменения.
```
On branch lab1-1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   reports/lab1.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        reports/lab1.md.backup
```
*Объяснение действий по шагам:*
- Я был в ветке `lab1-1`
 изменил файл `reports/lab1.md`
Но я **не сделал** `git add` и `git commit`.

- Я переключился на `master`
`git checkout master`
Git показал:
M       `reports/lab1.md`
M = Modified (изменён).
Git перенёс изменения с собой в master, потому что они ещё не закоммичены.
- Я проверил статус в `master`
`git status`
Git показал:
```
modified:   reports/lab1.md
untracked: reports/lab1.md.backup
```
Значит, изменения всё ещё здесь, но они не привязаны ни к одной ветке.

 - вернулся обратно в `lab1-1`
 `git checkout lab1-1`
Git снова сказал:
```
M       reports/lab1.md
```
Изменения вернулись со мной обратно в ветку `lab1-1`.

- Наконец, я сделал `add` и `commit` в ветке `lab1-1`
```
git add reports/lab1.md`
git commit -m "new text has been added to the branch lab1-1"
```
 - Я снова переключился на master
```
git checkout master
git status
```

**Результат:**
Изменения остались только в `lab1-1`, потому что они закоммичены туда.

**Когда мы работаем в разных ветках, изменения скрыты и не видны в других ветках, пока мы не сделаем коммит в нужной ветке.**

**Это особенность Git, а не ошибка.**
**Она позволяет работать над разными задачами отдельно, не мешая основной ветке master**.
