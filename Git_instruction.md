![GitLogo](Git-Logo-1788C.png)
# Работа с Git и GitHub
## 1. Проверка наличия установленного Git
В териминале выполнить команду `git version`.
Если Git установлен появится сообщение с  информацией о версии программы, иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию Git с сайта https://git-scm.com/download. 
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно выполнить в терминале две команды:
```
 git config --global user.name "Your Name" 
 git config --global user.email "you@example.com"
```
## 4. Ининциализация репозитория
В терминале переходим к папке, в которой хотим создать репозиторий. Выполняем команду:
```
git init
```
В исходной папке появится скрытая папка **.git**
Для отслеживания изменений файла, его необходимо добавить в список отслеживаемых командой:
```
git add <имя файла>
```
## 5. Запись изменений в репозиторий
Для записи изменений в репозиторий использу ются команды:
```
git add <название файла>
git commit -m <название файла>
```
`add` - подгатавливает (индексирует) файл отслеживания для коммита.
`commit` - добавляет коммит в подготовленный файл для отслеживания.

Можно применить комбинированную команду, если мы используем один файл либо коммит довавляется во все отслеживаемые файлы:
```
git commit -am <Текст комментария>
```
Каждый коммит имеет свой уникальный номер.

Просмотреть изменения в закоммиченном файле и текущем можно командой:
```
git diff
```

## 6. Просмотр истории коммитов
История коммитов можно просмотреть командой:
```
git log
```
Также применяется команда для более копактного (однострочного) вывода информации:
```
git log --oneline
```
Для более наглядного изображения в виде схемы веток применяется команда:
```
git log --graph
```

## 7. Перемещение между сохранениями
Для перемещения между сохранениями применяется команда
```
git checkout <уникальный номер коммита>
```
Уникальный номер коммита можно указать не весь, а первые 5-7 символов.
Вернуться к актуальному состоянию можно командой:
```
git checkout master
```

## 8. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенных файлы и папки, необходимо создать файл ***.gitignore*** и записать в него названия или шаблоны, соответствующие таким файлам или папкам.
Этот файл (.gitignore)  добавляется в список отслеживаемых файлов Git.

## 9. Создание веток в Git
По умолчание имя основной ветки в Git это **master**.
Создать ветку можно командой:
```
git branch "имя новой ветки"
```
Список веток в репозитории можно посмотреть с помощью команды `git branch`. Текущая ветка будет отмечена звездочкой: __*master__

Перемещение между ветками 

## 10. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей, нужно выполнить команду:
```
git merge <название ветки>
```
При возникновении конфликтов при слиянии веток, необходимо выбрать одну из выбранных версий для слияния:

## 11. Удаление веток
Ветку можно удалить командой:
```
git branch -d <название ветки>
```
При удалении ветки с которой не выполнено слияние Git выдаст сообщение об ощибке.
Для явного удаления ветки, необходимо выполнить команду:
```
git branch -D <название ветки>
```
__Примечание:__
`Удалить текущую ветку нельзя, для этого необходимо перейти на другую ветку. Ветка master является такой же веткой, которую можно удалить находясь на другой ветке`

## 12. Работа с удаленными репозиториями
Удалённые репозитории представляют собой версии вашего проекта, сохранённые в интернете или ещё где-то в сети. У вас может быть несколько удалённых репозиториев, каждый из которых может быть доступен для чтения или для чтения-записи.
### 12.1. Создание аккаунта на  GitHub
Для создания учетной записи (аккаунта) в GitHub, необходимо выполнить следующие действия:
Открываем в браузере страницу https://github.com/join и заполняем поля:
- Username — ваше будущее имя пользователя на сайте GitHub.
- Email Address — ваш адрес электронной почты.
- Password — ваш будущий пароль на сайте GitHub.
- 
![](001.png)

После чего нажмимаем на Create an account.

### 12.2. Создать удаленный репозиторий
Нажмите + > New repository в командной панели вверху страницы.

![](002.png)

Заполняем основные свойства создаваемого репозитория:
- В поле **Repository** name вводим имя создаваемого репозитория.
- Устанавливаем флажок **Initialize this repository with a README**, чтобы в дальнейшем мы имели возможность сразу клонировать репозиторий на свой компьютер.
- Нажмимаем **Create repository**.

![](003.png)

Имя вашего репозитория будет показано в верхнем левом углу страницы.

![](004.png)

### 12.3. Связать удаленный репозиторий с локальным

Добавить удаленный репозиторий к проекту:
```
git remote add <имя для репозитория> <url адрес репозитория в сети>
```
Для получения и слияния изменений из удаленного репозитория используется команда:
```
git pull
```
Для слияния изменений локального репозитория с удаленным репозиторием используется команда:
```
git push <url Репозитория>
```
