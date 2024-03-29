## Что такое Git?
**Git** - свободная и с открытым исходным кодом распределенная система контроля версий, предназначенная для обработки *всех*, от маленьких до очень больших проектов с **высокой скоростью и эффективностью**.

## Краткое руководство
### Скачиваем Git по ссылки: http://git-scm.com/

- Далее устанавливаем его;
- Затем заходим на **сайт**: https://github.com/ и регистрируемся там;
- Далее входим в личный кабинет и создаем новый репозиторий, нажав на кнопку 
**New Repository**;
- Далее заполняем данные и нажимаем **Create Repository**;

## Создаем папку для репозитория

**Далее** создаем папку на любом диски. (Например C:\Example);
- Запускаем программу git bash(Пуск->Все программы->Git);
- Переходим в нужную нам папку: (Папка и диск могут быть **другие**) 
```
cd C:
cd Example 
```

**Далее** выполняем следующие команды
* **touch** - создаем файл
```
touch README.md
```
* **git init** - инициализируем репозиторий.
``` 
$ git init
```

* **git add file.txt** - добавляем файл.
```
$ git add README.md
```
При возникновении ошибки: 

fatal: LF would be replaced by CRLF in file.txt

**Нужно ввести команды:** 
``` 
$ git  config  --global  core.autocrlf  false

$ git  config  --global  core.safecrlf  false
```

* **git commit -m "Initial commit"** - сохраняем изменения c пометкой "Initial commit".
``` 
$ git commit -m "Initial commit" 
```

* **git remote add origin https://github.com/Путь_к_вашему_репозиторию.git** - добавление вашего локального репозитория и связывание его с текущей папкой(Путь к репозиторию можно **скопировать на сайт** зайдя в папку с проектом).
```
git remote add origin htttps://githun.com/Путь_к_вашему_репозиторию.git
```

**Далее**, если всё правильно, нужно закинуть ваши данные на локальный репозиторий.

Это делается с помощью: 
* **git push -u origin master** - закидываем данные.
```
git push -u origin master
```
**Ну вот и всё!** Далее можно создавать любые файлы и добавлять их на свой репозиторий.
Используя для это: **git add**, **git commmit** и **git push**

# Полезные команды

## Настройка

### Указать глобальный username:
```
$ git config --global user.name "John Doe"
```
### Указать глобальный user email:
```
$ git config --global user.email johndoe@example.com
```
### Указать редактор, который будет использоваться, когда нужно ввести сообщение в Git:
```
$ git config --global core.editor emacs
```
### Указать утилиту сравнения, которая будет использоваться для разрешения конфликтов слияния:
```
$ git config --global merge.tool vimdiff
```
### Просмотреть используемые настройки:
```
$ git config --list
```

## Работа с репозиторием

### Инициализировать репозиторий:
```
$ git init
```
### Показать статус репозитория:
```
$ git status
```
### Коммитит с указанием комментария:
```
$ git commit -m 'some entry script fixes'
```
### Коммитит с указанием комментария и автоматической индексацией:
```
$git commit -a -m 'some entry script fixes'
```
### Добавить файл в индекс:
```
$ git add index.php
```
### Посмотреть изменения между рабочим каталогом и индексом:
```
$ git diff
```
### Посмотреть изменения между последним коммитом и индексом:
```
$ git diff --cached
```
### Удалить файл из индекса и из рабочего каталога:
```
$ git rm readme.txt
```
### Удалить файл из индекса, оставив его при этом в рабочем каталоге:
```
$ git rm --cached readme.txt
```
### Исключить файл (который находится в индексе, но еще не за коммитен) из индексации:
```
$ git reset HEAD readme.txt
```
### Просмотр истории коммитов:
```
$ git log
```
### Просмотр истории коммитов в GUI:
```
$ gitk
```

## Работа с удаленным сервером

### Просмотреть какие удалённые серверы уже настроены, параметр -v отображает так же url сервера:
```
$ git remote -v
```
### Добавить новый удалённый репозиторий под именем pb:
```
$ git remote add pb git://github.com/paulboone/ticgit.git
```
### Посмотреть список коммитов репозитория pb ветки master, которые были выполнены после последнего pull-а:
```
git log pb/master
```
### Извлечь (fetch) всю информацию, которая есть в репозитории pb:
```
$ git fetch pb
```
### Слить (merge) информацию, которую получили через fetch с рабочим каталогом:
```
$ git merge pb/master
```
### Отправить (push) код в ветку master удаленного репозитория pb:
```
$ git push pb master
```
### Переименовать удаленный репозиторий из pb на paul:
```
$ git remote rename pb paul
```
### Удалить удаленный репозиторий paul:
```
$ git remote rm paul
```

## Работа с метками

### Просмотр имеющихся меток:
```
$ git tag
```
### Создание аннотированной метки:
```
$ git tag -a v1.4 -m 'my version 1.4'
```
### Создание легковесной метки:
```
$ git tag v1.4
```
### Просмотр данных метки:
```
$ git show v1.4
```
### Создание метки для какого-либо существующего коммита (9fceb02 - контрольная сумма коммита, или ее часть):
```
$ git tag -a v1.2 9fceb02
```
### Отправить метку на удалённый сервер:
```
$ git push pb v1.5
```

## Работа с ветками

### Отобразить список веток проекта:
```
$ git branch
```
### Отобразить список веток с последними коммитами:
```
$ git branch -v
```
### Создать новую ветку с названием "iss53":
```
$ git branch iss53
```
### Переключиться на ветку iss53:
```
$ git checkout iss53
```
### Создать ветку с названием "iss53" и переключиться на нее:
```
$ git checkout -b iss53
```
### Создать ветку с названием "articles" на основе ветки "articles" из удаленного сервера pb и переключиться на нее:
```
git checkout -b articles pb/articles
```
### Слить текущую ветку с веткой hotfix:
```
$ git merge hotfix
```
### Переименовать ветку "articles" в "content":
```
$ git branch -m articles content
```
### Удалить ветку hotfix:
```
$ git branch -d hotfix
```
### Удалить ветку hotfix на удаленном сервере pb:
```
$ git push pb :hotfix
```
### Запустить графический инструмент для отображения конфликтных ситуаций:
```
$ git mergetool
```
### Посмотреть список веток, которые уже слиты с текущей:
```
$ git branch --merged
```
### Посмотреть список веток, которые содержат наработки, но еще не слиты с текущей:
```
$ git branch --no-merged
```

## Как получить помощь? ##

Если вам нужна помощь при использовании Git'а, есть три способа открыть страницу руководства по любой команде Git'а:

	$ git help <команда>
	$ git <команда> --help
	$ man git-<команда>

Например, так можно открыть руководство по команде config:

	$ git help config

## Дальнейшее изучение Git
**Очень рекомендую книгу**: https://github.com/progit/progit/
В разделе ru - **русская весрия**.