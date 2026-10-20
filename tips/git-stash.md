# Отложить незаконченные правки

**Команда:** `git stash`

## Когда пригодится

Ты правишь файл в одной ветке, а нужно срочно переключиться на другую. Коммитить недоделанное не хочется. `git stash` убирает правки в отдельное хранилище, и рабочая папка становится чистой. `git stash pop` возвращает правки обратно.

## Пример

```bash
$ git stash
Saved working directory and index state WIP on feature/timer: 8625bc2 init

$ git switch main
Switched to branch 'main'

$ git switch feature/timer
Switched to branch 'feature/timer'

$ git stash pop
On branch feature/timer
Changes not staged for commit:
	modified:   Program.cs
Dropped refs/stash@{0} (de215d555233bf0a4873fb3372e3792ba0420aca)
```

## Что важно знать

`git stash list` показывает все отложенные правки. `pop` возвращает последнюю и удаляет её из списка.

По умолчанию `git stash` не трогает новые файлы, которые Git ещё не отслеживает: они остаются в папке. Чтобы отложить и их, используй `git stash -u`.
