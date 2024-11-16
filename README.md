# Git Памятка

## Настройка Git

```sh
git config --global user.name "Ваше Имя"
git config --global user.email "ваш.email@example.com"
```

## Основные команды

### Инициализация репозитория

```sh
git init
```

### Клонирование репозитория

```sh
git clone <url>
```

### Статус репозитория

```sh
git status
```

### Добавление изменений в индекс (staging area)

```sh
git add <файл/директория>
git add .
```

### Создание коммита

```sh
git commit -m "Сообщение коммита"
```

### Просмотр истории коммитов

```sh
git log
```

### Просмотр истории коммитов с графом

```sh
git log --graph --oneline --all
```

## Работа с ветками

### Создание новой ветки и переключение на нее

```sh
git checkout -b <branch-name>
```

### Переключение между ветками

```sh
git checkout <branch-name>
```

### Слияние веток

```sh
git merge <branch-name>
```

### Удаление локальной ветки

```sh
git branch -d <branch-name>
```

### Принудительное удаление локальной ветки

```sh
git branch -D <branch-name>
```

### Переименование локальной ветки, на которой находитесь

```sh
git branch -m branch-name
```

### Переименование локальной ветки, если вы на другой ветке

```sh
git branch -m old-name new-name
```

### Переименование удаленной ветки (удалите удаленную ветку old-name и добавьте локальную ветку new-name)

```sh
git push origin :old-name new-name
```

### Просмотр всех веток

```sh
git branch
```

## Работа с удаленными репозиториями

### Добавление удаленного репозитория

```sh
git remote add origin <url>
```

### Отправка изменений в удаленный репозиторий

```sh
git push origin <branch-name>
```

### Получение изменений из удаленного репозитория

```sh
git pull
```

### Клонирование удаленной ветки

```sh
git fetch origin
git checkout -b <branch-name> origin/<branch-name>
```

## Откат изменений

### Сброс изменений в рабочей директории

```sh
git checkout -- <файл>
```

### Сброс изменений в индексе

```sh
git reset HEAD <файл>
```

### Отмена последнего коммита (изменения сохранятся в рабочей директории)

```sh
git reset --soft HEAD^1
```

### Отмена последнего коммита (изменения будут потеряны)

```sh
git reset --hard HEAD^1
```

### Удаление коммита из истории

```sh
git rebase -i HEAD~<количество коммитов>
```

## Слияние и разрешение конфликтов

### Продолжение слияния после разрешения конфликтов

```sh
git add <файл>
git commit
```

### Прерывание слияния

```sh
git merge --abort
```

## Стеш (временное сохранение изменений)

### Сохранение изменений в стеш

```sh
git stash
```

### Восстановление изменений из стеша

```sh
git stash pop
```

### Просмотр сохраненных стешей

```sh
git stash list
```

### Удаление всех стешей

```sh
git stash clear
```

## Теги

### Создание тега

```sh
git tag <tag-name>
```

### Просмотр тегов

```sh
git tag
```

### Отправка тегов в удаленный репозиторий

```sh
git push origin --tags
```

## Aliases

### Создание alias

```sh
git config --global alias.<alias-name> '<git-command>'
```

### Примеры alias

#### Alias для создания новой ветки и переключения на неё

```sh
git config --global alias.newbr 'checkout -b'
# Использование: git newbr <branch-name>
```

#### Alias для переименования локальной ветки

```sh
git config --global alias.rename-br '!f() { git branch -m \"$1\"; }; f'
# Использование: git rename-br <new-branch-name>
```

#### Alias для переименования удаленной ветки

```sh
git config --global alias.rename-remotebr '!f() { git branch -m \"$1\" \"$2\" && git push origin --delete \"$1\" && git push origin -u \"$2\"; }; f'
# Использование: git rename-remotebr <new-branch-name> - если находитесь на текущей ветке
# Использование: git rename-remotebr <old-branch-name> <new-branch-name>

```

#### Alias для удаления локальной ветки

```sh
git config --global alias.del-br 'branch -d'
# Использование: git del-br <branch-name>
```

#### Alias для принудительного удаления локальной ветки

```sh
git config --global alias.f-del-br 'branch -D'
# Использование: git f-del-br <branch-name>
```

#### Alias для отмены последнего коммита (изменения сохранятся в рабочей директории)

```sh
git config --global alias.soft-undo 'reset --soft HEAD^1'
# Использование: git soft-undo
```

#### Alias для отмены последнего коммита (изменения будут потеряны)

```sh
git config --global alias.hard-undo 'reset --hard HEAD^1'
# Использование: git hard-undo
```
