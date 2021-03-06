x14.12-xmobile-handwatch
========================

# Profiles

Все профили импортируются тапом на вкладке `Profiles - Import`.

### Google Keep

1. `Show_Keep_Notes` - при перехвате команды `googlekeep` запускает срипт и показывает на часах заголовки первых 20 заметок. На встряхивание посылает команду на показ следующих 20 заголовков.
2. `Show_Keep_Text` - показывает текст заметки при нажатии на зоголовок.
3. `Show_20_40notes` - показывает заголовки с 20 по 40. При нажатии откроет нужные вторым профилем, т.к. посылает уникальный `id` заметки.

**Примечание:** Для отображения заметок 40-60 профиль строится по аналогии. Могут быть проблемы с sqlite3 на Android 5.0

### Комп включен

Пример работы профиля из предыдущей статьи про EventGhost и AutoRemote. При загрузке или разблокировке компа (при условии подключения к интернету) на часах появится соответствующее уведомление.

### Найди телефон

При получении команды - выкручивает на максимум громкость медиа и запускает любимую песню/громкий звук. Необходимо выбрать у себя на устройстве в действии `Open File`.

### Нотификатор

1. `Notify_Text_Hangouts` - показывает уведомления из Hangouts простым текстом AutoPebble Text Screen. При нажатии на среднюю кнопку делает dismiss.
При необходимости можно добавить другие приложения и использовать rejex.(пример в профиле Pebble_Notif_Click)
2. `Pebble_Notif_Click` - Показывает уведомления с кнопками из Hangouts, Google Search (погоду и напоминания) и Gmail. Необходимо или отключить профиль выше или убрать/заменить Hangouts из данного.
3. `na(Notification Action)` - действие при нажатии на средней кнопки на тексте уведомления часов. То же самое, если нажать на уведомление на телефоне.
Обычно - открытие приложения.
4. `dn(Dismiss Notification)` - "смахивает" уведомление с телефона.

### Основной экран

При открытии приложения на часах - показывает AutoPebble List с разделами. При нажатии на пункт списка посылает соответствующие команды, которые перехватываются другими профилями.В заголовке показывает заряд аккумулятора телефона.

### Отключение блокировки экрана

Отключает блокировку экрана при наличии связи с часами.

### Отправить на часы с компа

Пример работы профиля из предыдущей статьи про EventGhost и AutoRemote. Если выделить текст и при нажатии правой кнопки выбрать соответствующий пункт, то через телефон часы покажут текст на экране AutoPebble Text Screen.
Тот же самый пройиль сработает и на текст из любого документа (в упомянутой статье показывается отправка текста из буфера обмена компа при нажатии клавиш `Ctrl+Alt+V`).

### Сбросить звонок и перезвонить или написать смс

1. `Missed_W.button` отслеживает нажатие кнопки отбой в приложении Pebble Dialer, после этого показывает выбор - перезвонить или написать смс.
2. `Перезвонить` - При получении команды call перезваниевает на последний номер.
3. `Ответ_Смс` - при получении команды msg показывает AutoPeble Quick Screen с 3мя вариантами ответов на выбор. При встряхивании показывает еще 3 варианта (настраивается отдельным профилем)
4. `Смс_За_Рулем` - пример отправки СМС с текстом "За рулем, перезвоню позже" при получении команды drive (средняя кнопка профиля 3)

**Примечание:** Остальные шаблоны настраиваются аналогично. "cl" в конце команд подразумевает clear - отдельный профиль, который закрывает текущее окно на часах, иначе будет висеть после нажатия. Не добавлен в каждый профиль, т.к. много где встречается и вынесен в отдельное действие.

### Управление звуком

При получении команды mute ставит на 0 громкость звнка, уведомлений, медиа. При получении команды unmute выставляет те же параметры на нужный уровень.

# Projects

Проекты импортируются через тап внизу на домике и Import, появляются на отдельной вкладке.

### Car_Geofence

Содержит 3 профиля:

1. Включение мониторинга геолокации при получении команды с часов.
2. Определение координат при запуске мониторинга и отправка координат на часы
3. Запуск навигации к определенным координатам при получении команды с часов

### GPM_Playlist

Содержит 4 профиля:

1. `Headphones` - Показ на часах списка плейлистов при подключении наушников
2. `GPM Playlisyts` - Запуск выбранного на часах плейлиста и запуск на часах приложения для контроля музыки
3. `Music` - показ на часах песен из выбранного заранее плейлиста при перехвате команды music. Команду необходимо настройить на одном из экранов. В примере плейлист в базе с названием BRADA'z music имеет id=5, поэтому жестко прописан в скрипте
4. `GPM Tracks` - запуск песен при нажатии на часах.

**Примечание:** Необходим плагин AutoShare. Возможны проблемы с работой sqlite3 на Android 5.0
