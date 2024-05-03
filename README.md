###
Описание репозитория

Сразу после создания нового проекта , находясь в папке инициализировать репозиторий командой *git init*
Сразу после этого рекомендуется создать файл ".gitignore", в котором прописать файлы которые не нужно отслеживать в git .  Для того чтобы сам файл *.gitignore* "не мозолил глаза" при вызове команды git status  его следует добавить в  файл *.gitignore*

```bash
Команда *git add . добавит все файлы в индекс отслеживания
Команда git commit -m "коментарий к комиту" зафиксирует изменения
```


На странице GitHub создай *new repository* с совпадающим именемБ склонируй его ssh (for example git@github.com:Svinetc/yandex_gt_practicing.git)

Затем в командной строке компьютера находясь в папке своего проекта введи команду *git remote add origin <git@github.com:Svinetc/yandex_gt_practicing.git>
это свяжет твой локальный реп с удаленным.
проверить можно командой *git remote -v*
Чтобы отправить изменения в первый раз , используй *git push -u origin master*
далее достаточно короткой *git push*


собственно первые шаги проделаны.Ура!
---------
###
Исследуем *log*
---------
Получить сокращённый лог можно с помощью команды git log с флагом --oneline (англ. «одной строкой»). В терминале появятся только первые несколько символов хеша каждого коммита и их комментарии.


```bash
git log --oneline
```
В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

###
 **Файл `HEAD`
 ----------


Файл `HEAD` (англ. «голова», «головной») — один из служебных файлов папки `.git`. Он указывает на коммит, который сделан последним (то есть на самый новый).
Командой
```bash
cd .git
```
перейди в папку .git
Командой
```bash
cat HEAD
```
получи вывод ref: refs/heads/master
это ссылка на последний (HEAD) сделанный коммит.
Командой
```bash
cat refs/heads/master
```
получи вывод хэша этого (HEAD) коммита

### Типичный жизненный цикл файла в Git




### Статусы `untracked`/`tracked`, `staged` и `modified`

Одна из ключевых задач Git — отслеживать изменения файлов в репозитории. Для этого каждый файл помечается каким-либо статусом. Рассмотрим основные.
- **`untracked`** (англ. «неотслеживаемый»)
    Мы говорили, что новые файлы в Git-репозитории помечаются как `untracked`, то есть неотслеживаемые. Git «видит», что такой файл существует, но не следит за изменениями в нём. У `untracked`-файла нет предыдущих версий, зафиксированных в коммитах или через команду `git add`.
- **`staged`** (англ. «подготовленный»)

    После выполнения команды `git add` файл попадает в **staging area** (от англ. _stage_ — «сцена», «этап [процесса]» и _area_ — «область»), то есть в список файлов, которые войдут в коммит. В этот момент файл находится в состоянии `staged`.

    В одном из предыдущих уроков мы сравнили коммит с фотографией. Можно развить эту аналогию и сказать, что команда `git add` добавляет персонажей (текущее содержимое файла или нескольких файлов) на **сцену** (англ. _stage_) для общей фотографии, а `git commit` делает снимок всей сцены целиком.
- **`tracked`** (англ. «отслеживаемый»)
    Состояние `tracked` — это противоположность `untracked`. Оно довольно широкое по смыслу: в него попадают файлы, которые уже были зафиксированы с помощью `git commit`, а также файлы, которые были добавлены в staging area командой `git add`. То есть все файлы, в которых Git так или иначе отслеживает изменения.
- **`modified`** (англ. «изменённый»)
    Состояние `modified` означает, что Git сравнил содержимое файла с последней сохранённой версией и нашёл отличия. Например, файл был закоммичен и после этого изменён.
