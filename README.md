##  Описание репозитория
Сразу после создания нового проекта , находясь в папке инициализировать репозиторий командой *git init*
Сразу после этого рекомендуется создать файл ".gitignore", в котором прописать файлы которые не нужно отслеживать в git .  Для того чтобы сам файл *.gitignore* "не мозолил глаза" при вызове команды git status  его следует добавить в  файл *.gitignore*

Команда *git add . добавит все файлы в индекс отслеживания
Команда git commit -m "коментарий к комиту" зафиксирует изменения

На странице GitHub создай *new repository* с совпадающим именемБ склонируй его ssh (for example git@github.com:Svinetc/yandex_gt_practicing.git)

Затем в командной строке компьютера находясь в папке своего проекта введи команду *git remote add origin <git@github.com:Svinetc/yandex_gt_practicing.git>
это свяжет твой локальный реп с удаленным.
проверить можно командой *git remote -v*
Чтобы отправить изменения в первый раз , используй *git push -u origin master*
далее достаточно короткой *git push*

##Быстрый коммит *git commit -a "comment"*
собственно первые шаги проделаны.Ура!
