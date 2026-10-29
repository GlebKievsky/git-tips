# Восстановление стёртых коммитов и веток
**Команда:** `git reflog`

## Когда пригодится
Ты сделал `git reset --hard HEAD~2`. Вместе с ненужным коммитом из цепочки пропал и ещё 1 правильный.

## Пример
```bash
$ git reflog -n 5
78363f6 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: reset: moving to HEAD@{1}
0d91d45 HEAD@{1}: reset: moving to 0d91d45
78363f6 (HEAD -> main, origin/main, origin/HEAD) HEAD@{2}: pull: Fast-forward
0d91d45 HEAD@{3}: checkout: moving from feature/timer to main
5609db4 (origin/feature/timer) HEAD@{4}: commit: Use total seconds for quiz time
```

## Что важно знать
`git reflog` хранит записи только локально и в течение 90 дней.
- Записи старше 90 дней стираются;
- Удалишь локальный репозиторий - потеряешь reflog навсегда.

`git --no-pager reflog` выводит длинный список без деления на страницы.

`git reflog -n` выводит n недавние шагов.