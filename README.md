# Шпаргалка по GIT

## Настройка и просмотр конфигурации
```
// Настройка данных пользователя
git config --global user.name "Kot Kompot"
git config --global user.email kotkompot@yandex.ru
```
```
// Просмотр конфигурации
git config --list
```
```
// Генерируем SSH-ключи с разными алгоритмами шифрования
ssh-keygen -t ed25519 -C "kotkompot@yandex.ru"
ssh-keygen -t rsa -b 4096 -C "kotkompot@yandex.ru"
```
## Начало работы с проектом
```
// Инициализация папки как репозитория
git init
// Чтобы разгитить папку достаточно удалить подкаталог .git
// README.md - файл с описанием проекта
```
```
// Привязать удаленный и локальный репозитории
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
// Проверка привязки
git remote -v
```
```
// Клонировать удаленный репозиторий в пустую локальную папку
git clone
```
## Подготовка файлов к коммиту
```
// проверить состояние
git status
```
```
// добавить конкретный файл
git add readme.txt
// добавить все в текущей папке
git add .
// добавить все файлы в репозитории
git add --all
```
## Коммиты и загрузки
```
// закоммитить с комментом
git commit -m 'Commit description'
// посмотреть лог коммитов
git log
```
```
// Первая загрузка проекта в удаленный репозиторий
git push -u origin master
// Любая последующая загрузка
git push
```
