UPD: Я понял совсем базовые понятия и решил подойти к изучению гит более серьезно, поэтому отсюда пойдет ссылка на книгу [[Git Pro Book]]

Также если есть вопросы, https://libera.chat/ очень хороший ресурс для вопросов по гиту.

Перед началом работы нужно указать имя пользователя и  email. Не знаю какие конкретно но я указал те на которые у меня зареган гит.
Указать их можно так:

`git config --global user.name "Имя"`
`git config --global user.email Почта"

# Добавление проекта в облако

На примере моего резерва заметок в obsidian. Они находятся в Desktop/vaults.

Я перехожу в эту папку с помощью cd и пишу:
`git init`

Затем получаю ответ от гита:
`Initialized empty Git repository in .git/`
Это означает что в моей рабочей директории создана папка гит, в которой находятся все нужные для взаимодействия с облаком файлы. Другими словами создан локальный репозиторий который 

С этого момента он может начать отслеживать эту папку, но.
Пока я не вызову `git add .`, что означает: Добавь **все изменения** в текущей директории и всех её поддиректориях в **индекс Git (staging area)**.

- `git add .` — добавит всё из текущей директории вниз
- `git add file.расш file2.расш` — добавит какие то  файлы
- `git add -A` — тоже добавит всё, включая удалённые файлы
- `git add -u` — только изменённые и удалённые (но не новые)

Индекс как я понял это своеобразная корзина в которой промежуточно находятся изменения которые вступят в силу после коммита. Кстати каждый последующий add перезаписывает прошлый.

А потом я пишу.
git commit -m "сохрани вот это, добавил информацию о пауках например"
И после коммита это все сохраняется в истории гит. В коммитах важно постепенно отмечать значимые изменения в коде.

потом нужно связать локальный репозиторий с внешним написав git remote add <имя(в основном origin)> <link на репозиторий>

и чтобы установить между ними поток обмена пишем git push -u(--set-upstream) <имя remote репозитория> <имя локальной ветки>

типо например я из ветки


Ну и заключительный этап это git push
Нужно потом ввести имя пользователя и токен. И вуаля данные на гитхабе.

# Просмотр логов


# Также нужно упомянуть просмотр состояния: 

git diff  показывает разницу между файлом в системе и файлом который был в staging(индекс гит) после последнего add. (Если ты изменил файл и еще не делал add)

git diff --cached(--staged тоже самое) показывает разницу между staging и commit. 

git diff HEAD(Указатель на последний коммит) показывает отличие текущей директории от последнего коммита.

# Ветви и их команды

```
git branch temporary
```

Эта команда создает ветвь с названием temporary. Выполняю ее

Если вызвать команду без третьего аргумента то выведется список ветвей. Вот что вижу я.

```
* main
temporary
```
