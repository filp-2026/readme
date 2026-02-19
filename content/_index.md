---
title: Подготовка к курсу Функциональное и логическое программирование
toc: true
---

### Установка Intellij IDEA

1. Скачать и установить Intellij Idea - [https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download/)
2. Альтернативный вариант - воспользоваться Jetbrains Toolbox [https://www.jetbrains.com/toolbox-app/](https://www.jetbrains.com/toolbox-app/)
3. Если при загрузке продукта вылетает ошибка, это значит, что нужно включить браузерный или ваш установленный на компьютер VPN
4. Если с VPN возникли проблемы, и таким путем не получается скачать, 
можно написать в телеграмм @ananastyyyyy, она скинет архивы с установочными файлами

> Альтернативный вариант - VS Code + плагин Metals, но он значительно хуже заточен под работу со Scala, чем Intellij
> IDEA и в это случае мы вряд ли сможем вам помочь :). Так же вы можете использовать версию Ultimate edition по студенческой
> лицензии - подробнее на сайте Jetbrains.

### В уже установленной Intellij IDEA

1. Перейти в Файл > Настройки > Плагины > Установить Scala плагин
   ![](/images/scala_plugin.png "Scala плагин")
    
### Создание SSH ключа

1. Windows
    1. Открыть cmd.exe
    2. Ввести команду `ssh-keygen -b 2048 -t rsa`
    3. Если не сработало, то надо установить клиент OpenSSH:
        1. Открыть Настройки > Приложения > Приложения и возможности > Дополнительные компоненты
        2. Нажать сверху "Добавить компонент" и там через поиск установить "Клиент OpenSSH".
    4. Проследовать всем пунктам установки, пароль устанавливать смысла нет, менять путь тоже не стоит
    5. После завершения будет сгенерирована пара файлов - `id_rsa` и `id_rsa.pub`, путь к ним был указан в процессе
       установки
    6. Необходимо скопировать в буфер обмена содержимое файла `id_rsa.pub`
2. Linux / Macos
    1. Открыть терминал
    2. Аналогично windows, начиная с 3-го шага

### Установка SSH ключа в GitHub

1. Зарегистрироваться на [https://github.com](https://github.com)
2. Перейти на [https://github.com/settings/keys](https://github.com/settings/keys)
3. Нажать на кнопку `New SSH key`
   ![New ssh key](/images/new_ssh_key.png "new ssh key")
1. Дать удобное вам название, например <имя пользователя>_<операционная система>
2. В поле `Key` вставить содержимое файла `id_rsa.pub`
3. Нажать кнопку `Add SSH key`

> Теперь вы сможете взаимодействовать со своим GitHub аккаунтом по SSH - клонировать, пушить и т.д. без ввода пароля

### Регистрация в github организации

Необходимо заполнить форму:

<iframe src="https://docs.google.com/forms/d/e/1FAIpQLScw9RuGjC3jHKXNg0WoJBgX8E1XdpWnigUewY74kx4ExSjiQA/viewform?embedded=true" width="640" height="1012" frameborder="0" marginheight="0" marginwidth="0">Загрузка…</iframe>

После чего вам на почту привязанную к аккаунту придет письмо с приглашением, ссылка будет доступна в течение 7 дней:
![](/images/invite_to_repo.png "Доступ к репозиторию с домашними работами")

### Регистрация на портале образования

1. Зарегистрироваться на [https://edu.tinkoff.ru/](https://edu.tinkoff.ru/);
2. Присоединиться к [курсу](https://edu.tbank.ru/all-activities/courses/96347666-c744-4dfa-ac1b-b11dc2a03d23);
3. Когда вы создадите Pull Request на гитхабе, нужно сдать соответствующее ему задание в этом курсе - просто прикрепите в
   поле для ответа ссылку на ваш PR. Баллы за задание тоже будут там.
1. Перейдите на страницу нужной практики
   ![](/images/task_page.jpeg)
2. Вставьте в поле "Ответ" ссылку на ваш PR и отправьте работу
   ![](/images/pull_request_link.jpeg)

### Подготовка проекта

1. После регистрации для вас в одной из организаций будет создан репозиторий с названием
   `Name_Surname_login`

| Группа | Организация в github                |
|--------|-------------------------------------|
| КН-201 | https://github.com/filp-2026-kn-201 |
| КН-202 | https://github.com/filp-2026-kn-202 |
| КН-203 | https://github.com/filp-2026-kn-203 |
| Другая | https://github.com/filp-2026-other  |

2. В окне Intellij выбрать Get from VCS
   ![](/images/get_from_vcs.png "Get from vcs")

3. В поле ссылка вставить ссылку на ваш репозиторий:
   ![](/images/get_exercises_link.png "Получить ссылку на репозиторий")

    1. IDEA может написать, что не установлен GIT, тогда следует нажать кнопку `Скачать и установить`
4. Нажать кнопку `Clone`, желательно, чтобы итоговый путь до проекта не содержал русских символов и пробелов
    1. Скорее всего Intellij Idea высветит два предупреждения - `Project JDK not found` и `No scala SDK in module` (
       Возможно, для этого понадобится открыть какой-нибудь Scala файл)
       ![](images/jdk_not_found.png "JDK not found")
    2. Необходимо нажать на кнопки рядом и установить и то, и другое
    3. Java
        1. Нажать на кнопку Setup JDK
        2. Выбрать Download
        3. выбрать 21 версию Oracle OpenJDK 
           ![](/images/setup_java.png "Setup java")

5. Scala
    1. Нажать на кнопку Setup Scala SDK
    2. Нажать на кнопку Create
    3. Нажать на кнопку Download
    4. Выбрать версию 2.13.12
       ![](/images/setup_scala.png "Setup scala")

6. Далее необходимо настроить корректную сборку проекта
    1. Переходим в File > Settings
    2. Вбить в поиск sbt
    3. Выбрать меню Build, Execution, Deployment > Build Tools > sbt
    4. Поставить следующие настройки
       ![](/images/sbt_settings.png "SBT settings")
7. Запускаем импорт проекта - нажать на маленькую красную кнопку справа-сверху
   ![](images/reload_sbt_project.png "Reload sbt project")
8. Пока проект импортируется, можно переключить форматировщик
    1. Перейти в File > Settings
    2. Вбить в поиск `scalafmt`
    3. Выбрать меню Editor > Code Style > Scala
    4. Выбрать в качестве форматировщика `Scalafmt`

   ![](images/scalafmt.png "scalafmt")
