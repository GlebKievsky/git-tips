# Проверить, что попадёт в коммит: `git diff --staged`

**Команда:** `git diff --staged`

## Когда пригодится

Ты правишь файлы, добавил их в индекс через `git add` и хочешь убедиться, что в коммит уйдёт именно то, что ты ожидаешь. `git diff --staged` показывает разницу между индексом и последним коммитом — то есть ровно те изменения, которые попадут в следующий коммит. Обычный `git diff` показывает только незастейдженные правки, поэтому после `git add` он молчит.

## Пример

```bash
$ git diff
diff --git a/notes.txt b/notes.txt
index e5c5c55..2a8b7c2 100644
--- a/notes.txt
+++ b/notes.txt
@@ -1,2 +1,2 @@
 line one
-line two
+line two fixed

$ git add notes.txt

$ git diff

$ git diff --staged
diff --git a/notes.txt b/notes.txt
index e5c5c55..2a8b7c2 100644
--- a/notes.txt
+++ b/notes.txt
@@ -1,2 +1,2 @@
 line one
-line two
+line two fixed
```

## Что важно знать

Команда смотрит только на индекс: если ты забыл выполнить `git add`, вывод будет пустым. Флаг `--staged` можно записать короче — `--cached`, результат тот же. Для быстрой сверки списка файлов удобен вариант `git diff --staged --stat`: он показывает, какие файлы затронуты и сколько в них изменённых строк.
