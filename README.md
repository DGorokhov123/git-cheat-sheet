# Шпаргалка по GIT

## Настройка и просмотр конфигурации
```
git config --global user.name "Kot Kompot"               // Настройка данных пользователя
git config --global user.email kotkompot@yandex.ru
git config --list                                        // Просмотр конфигурации
```
```
ssh-keygen -t ed25519 -C "kotkompot@yandex.ru"           // Генерируем SSH-ключи
ssh-keygen -t rsa -b 4096 -C "kotkompot@yandex.ru"       // запасной алгоритм
```
## Начало работы с проектом
```
git init            // Инициализация папки как репозитория
git clone           // Клонировать удаленный репозиторий в пустую локальную папку
                    // Чтобы разгитить папку достаточно удалить подкаталог .git
README.md           // файл с описанием проекта
```
```
                    // Cвязать удаленный и локальный репозитории
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git

git remote -v       // Проверка привязки
```
## Подготовка файлов к коммиту
```
git status                   // проверить состояние
```

```mermaid
graph LR;
untracked -- "git add" --> staged;
staged -- "git commit" --> tracked;
tracked -- "writing code" --> modified;
modified -- "git add" --> staged;
staged -- "writing code" --> modified;
```

```
            СТАТУСЫ ФАЙЛОВ
tracked                      // отслеживается, не изменялся с последнего коммита
untracked                    // не отслеживается
staged                       // файл добавлен и подготовлен к коммиту
modified                     // файл изменен с последнего добавления
staged + modified            // файл добавлен, а потом изменен (staged неизмененная версия)
```
```
git add readme.txt           // добавить конкретный файл
git add .                    // добавить все в текущей папке
git add --all                // добавить все файлы в репозитории
```
## Коммиты и загрузки
```
git commit -m 'Commit description'         // закоммитить с комментом
git push -u origin master                  // Первая загрузка проекта в удаленный репозиторий
git push                                   // Любая последующая загрузка
```
```
                     ПРАВИЛА КОММЕНТОВ
feat:                                      // новая фича
fix:                                       // исправление ошибки
BREAKING CHANGE:                           // нарушается обратная совместимость!!!
LGS-239:                                   // тикет в джире
something with #123                        // тикет в гите
docs: style: refactor: perf: test:         // прочие
```
конвенциональные коммиты выглядят вот так:
```
<type>[optional scope]: <description>

[optional body]

[optional footer]
```
## Лог коммита: что внутри?
```
git log               // посмотреть лог коммитов
git log --oneline     // сжатый вид (строка на коммит)
```
```
HEAD                  // последний коммит (можно использовать в коммандах вместо хеша)
Hashcode              // уникальный идентификатор коммита
Author + Date         // автор и дата
Description           // Сообщение к коммиту
```
## Исправить сделанный коммит
```
git commit --amend --no-edit              // добавить изменения в последний коммит
```
