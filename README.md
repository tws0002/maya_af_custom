## Custom Afanasy Submitter for Maya

Скрипт для разделения просчета сцены на 2 этапа:

1. Локальная генерация .ass файлов
2. Удалённый рендер через kick

## Установка

На компьютере ползователей уже должна быть установлена Maya и mtoa, на ферме должен быть установлен mtoa.

#### Клиент

1. Скопировать пакет `maya_af_custom` на сервер в общедоступную директорию

2. Отредактировать файл `main_env.sh` указав правильные пути

3. Сделать файл `start_maya.sh` исполняемым

4. Запускать Maya с помощью файла `start_maya.sh`

#### Ферма

1. Скопировать файл `cgru/setup_farm.sh` в корень установленного CGRU

2. Изменить путь к файлу `main_env.sh`

## Отправка на рендер

Для рендера стандартным способом в сабмитере нажмите *Submit Default*. В этом случае на ферме создастся задача
с двумя блоками: генерация .ass и рендер через kick

Для отправки на удалённую ферму нажмите *Remote Render*, при этом произойдет локальная генерация .ass файлов
и в папке рядрм с этими файлами будет создан файл `render.sh`. После синхронизации .ass достаточно запустить этот файл
чтобы создалась задача на удалённой ферме.