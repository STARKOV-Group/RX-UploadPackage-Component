# Выгрузка пакета в корпоративное облако NextCloud (RX UploadPackage Component)

#### Описание:

Выгрузка собранного пакета в корпоративное облако NextCloud с помощью [утилиты](https://git.starkovgrp.ru/gubarev/NextCloudConnector.git).

##### Логика:

Если значение переменной [DeployMode](https://github.com/STARKOV-Group/RX-DeployDTPackage-Component#deploymode) не равно "upload", то этап пропускается

Из параметров CloudUserName и CloudUserPassword извлекаются логин и пароль пользователя корпоративного облака, под которым будет загружен пакет, расположенный по адресу [PackageProjectPath](https://github.com/STARKOV-Group/Completed-RXDTDeploy-Component#packageprojectpath)

C помощью [утилиты](https://git.starkovgrp.ru/gubarev/NextCloudConnector.git) этот пакет загружается в папку по адресу UploadFolder/{текущая дата в формате ГГГГ-ММ-ДД} или, если он не указан, то в папку по адресу CI\_CD/\$[CI\_PROJECT\_NAMESPACE](https://docs.gitlab.com/ci/variables/predefined_variables/#:~:text=project%2D1.-,CI_PROJECT_NAMESPACE,-Pre%2Dpipeline)/\$[CI\_COMMIT\_BRANCH](https://docs.gitlab.com/ci/variables/predefined_variables/#:~:text=running%20a%20pipeline.-,CI_COMMIT_BRANCH,-Pre%2Dpipeline)/{текущая дата в формате ГГГГ-ММ-ДД}

#### Переменные:

##### Пользовательские настройки

##### CloudUserName

**Описание:** Логин пользователя под которым будет происходить загрузка на облако  
**Обязательность:** Да  
**Пример:** Amongus

##### CloudUserPassword

**Описание:** Пароль пользователя под которым будет происходить загрузка на облако  
**Обязательность:** Да  
**Пример:** 1Qwerty

##### UploadFolder

**Описание:** Путь до кастомной папки в облаке  
**Обязательность:** Нет  
**Пример:** CICD/Alrosa/custom
