# Представление конфиденциальных данных в агрегированном виде с использованием векторного формата SVG, языков R и Rust 
## СПО (свободное программное обеспечение)
Приложение является СПО.

## Функции
- Создание API интерфейса для языка R в сети Интернет
- Генерация графической информации из R в формате SVG
- Представление графической информации в браузере

## Требуемое программное обеспечение (ПО)
Приложение использует ПО с открытым исходным кодом для правильной работы:
- [R](https://www.r-project.org) - для статистических исследований
- [Rust](https://www.rust-lang.org) - для написания приложений
- [Actix Web](https://actix.rs) -  Web framework для Rust
- [JavaScript](https://www.ecma-international.org/publications-and-standards/standards/ecma-262) - для написания frontend- и backend-частей сайта
- [Node.js](https://nodejs.org) - для использования npm
- [npm](https://www.npmjs.com) - менеджер пакетов npm для Node.js


Приложение также имеет открытый исходный код на Github

## Установка
Установка на Linux (Fedora) происходит с правами администратора.
Ввыполнить команды для установки openssl:

\# dnf install openssl

\# dnf install pkg-config perl-FindBin openssl-devel

Для запуска проекта необходимо установить Rust.

Установка Rust:

\# dnf install rust cargo

Для правильной установки зависимостей необходимо отредактировать файл Cargo.toml:

[dependencies]

actix-web = "4"

serde = { version = "1.0", features = ["derive"] }

openssl-sys = "0.9.92"

openssl = "0.10.57"

reqwest = "0.9.24"

base64 = "0.21.3"

Текст программы на Rust содержится в файле **src/main.rs**.

Создать в директории проекта поддиректорию **public**.

В ней создать поддиректорию **html**.

Файл **plot.html**  (стартовая страница сервера) располагается  в подкаталоге **public/html** и предназначен для визуализации.

Установка R под Fedora выполняется стандартно:

\# dnf install R

Установка графической среды разработки RStudio:

\# dnf install rstudio-desktop

\# dnf install rstudio-server

Установка в RStudio необходимых для дальнейшей работы пакетов

\> install.packages("plumber")

\> install.packages("ggplot2")

\> install.packages("png")

Загрузка файла **plot.R**

В кносоли RStudio запустить команду:

\> r <- plumb("/home/… /plot.R")

Если команда выдает ошибку, то попробуйте загрузить plumber вручную

\> library(plumber)

Если это не поможет, то установите в Fedora пакеты

\# dnf install libcurl-devel

\# dnf install libsodium

\# dnf install libsodium-devel

и попробуйте снова выполнить

\> r <- plumb("/home/… /plot.R")

Загрузится файл **plot.R**

Запустите сервер R с использованием порта 8000.

\> r$run(port=8000)

Установим Node.js выполнив команду

\# dnf install nodejs

Установим менеджер пакетов npm, если предыдущая команда его не установила

\# dnf install npm

Установим менеджер процессов pm2:

\# npm install pm2 -g

## Использование
Запуск R осуществляется из поддиректории **R** при помощи файла **R/start.sh** командой

\$ ./start.sh

Запуск Rust осуществляется из директории проекта при помощи команды

\$ cargo run

Откройте браузер. Введите адрес localhost:8080. Нажмите кнопку "Пуск".

На экране будут представлены данные, полученные из R.

## Лицензия
MIT
