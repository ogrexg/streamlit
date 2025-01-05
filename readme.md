# Приложение представляет из себя редактор для файлов формата barfi

## Структура проекта
- app.py: Основной файл приложения, содержащий логику и интерфейс.
- req.txt: Файл с зависимостями, необходимыми для работы приложения.
- backups/: Директория, в которой будут храниться резервные копии схем.
- files/: Директория для хранения дополнительных файлов схем.
- schemas.barfi: Основной файл

## Установка

1. Склонировать репозиторий "git clone (ссылка на этот гитхаб репозиторий)"
2. Перейти в папку с проектом
3. Создать виртуальной окружение "python -m venv venv"
4. Установить зависимости "pip install -r req.txt"
5. Запустить веб приложение "streamlit run app.py"

# Barfi Schema Editor

## Описание

Barfi Schema Editor — это веб-приложение, разработанное с использованием библиотеки Streamlit, которое позволяет пользователям управлять схемами Barfi. Приложение предоставляет интерфейс для создания, удаления, импорта, экспорта и дублирования схем, а также для синхронизации схем из различных источников.

## Функциональность

### 1. Создание схемы

- **Описание**: Пользователи могут создавать новые схемы, вводя название и данные схемы в текстовые поля.
- **Как это работает**:
  - Пользователь вводит название схемы в текстовое поле.
  - Вводит данные схемы в текстовую область, где данные должны быть представлены в формате, понятном для приложения (например, в виде словаря).
  - При нажатии кнопки "Сохранить" приложение проверяет, существует ли уже схема с таким названием. Если нет, схема сохраняется в файл.
  - Если схема с таким названием уже существует, пользователю выводится уведомление.

### 2. Удаление схемы

- **Описание**: Позволяет пользователям удалять существующие схемы из системы.
- **Как это работает**:
  - Пользователь выбирает схему из выпадающего списка.
  - При нажатии кнопки "Удалить" приложение вызывает функцию, которая удаляет выбранную схему.
  - После успешного удаления пользователю выводится уведомление об успешном удалении.

### 3. Список схем

- **Описание**: Отображает все доступные схемы, которые были созданы и сохранены в системе.
- **Как это работает**:
  - Приложение загружает список схем из основного файла и отображает их в виде списка на экране.
  - Если схемы не найдены, пользователю выводится сообщение о том, что схемы не найдены.

### 4. Редактор схем

- **Описание**: Позволяет пользователям просматривать и редактировать схемы.
- **Как это работает**:
  - Пользователь выбирает схему из выпадающего списка.
  - Приложение отображает выбранную схему с использованием визуальных блоков.
  - Пользователь может вносить изменения в схему и видеть результат в реальном времени.

### 5. Синхронизация схем

- **Описание**: Синхронизирует схемы из основного файла и дополнительной директории.
- **Как это работает**:
  - Приложение загружает схемы из основного файла и дополнительной директории.
  - Если в дополнительной директории есть схемы, которые отсутствуют в основном файле, они добавляются.
  - Если схема идентична (имя и данные схемы совпадают), то схема сохранится без изменений.
  - Если схемы с такими же именами, но разными данными, создается новая схема с уникальным именем (например, добавляется суффикс "_copy").
  - Также происходит автоматическая синхронизация при запуске приложения.

### 6. Импорт схемы

- **Описание**: Позволяет загружать схемы из файлов с расширением `.barfi`.
- **Как это работает**:
  - Пользователь загружает файл схемы через элемент загрузки.
  - Приложение загружает схемы из файла и предлагает пользователю выбрать, какую схему импортировать.
  - Если схема с таким именем уже существует, пользователю выводится предупреждение.

### 7. Экспорт схемы

- **Описание**: Позволяет пользователям экспортировать схемы в отдельные файлы.
- **Как это работает**:
  - Пользователь выбирает схему из списка доступных схем.
  - При нажатии кнопки "Подготовить к экспорту" приложение создает файл с выбранной схемой.
  - Пользователь может скачать файл с расширением `.barfi`.

### 8. Дублирование схемы

- **Описание**: Позволяет пользователям дублировать существующие схемы с новым именем.
- **Как это работает**:
  - Пользователь выбирает схему из выпадающего списка.
  - Вводит новое имя для дубликата.
  - При нажатии кнопки "Дублировать" приложение создает копию схемы с новым именем.
  - Если схема с таким именем уже существует, пользователю выводится предупреждение.

### 9. Создание резервной копии

- **Описание**: Автоматически создает резервные копии схем каждые 15 минут.
- **Как это работает**:
  - Приложение проверяет, прошло ли 15 минут с последнего бэкапа.
  - Если прошло, создается резервная копия основного файла схем в папке `backups` с временной меткой в имени копии.

[![Посмотреть видео]](https://youtu.be/etZulc7WluA?si=9gpmlnSySLoPVxYQ)

