# Практическая работа № 5. Система учёта книг в библиотеке

Учебный проект на Python: REST API для каталога книг, авторов, читателей и выдач, а также панель статистики.

## Запуск (Windows)
1. Установите Python 3.11 или новее.
2. Распакуйте архив и откройте терминал в папке проекта.
3. Выполните:
```powershell
py -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python manage.py makemigrations library
python manage.py migrate
python manage.py seed_demo
python manage.py runserver
```
4. API: http://127.0.0.1:8000/api/ ; админ-панель: http://127.0.0.1:8000/admin/
5. В отдельном терминале активируйте окружение и запустите `streamlit run dashboard/app.py`. Панель: http://localhost:8501.

## Запуск (Linux/macOS)
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python manage.py makemigrations library
python manage.py migrate
python manage.py seed_demo
python manage.py runserver
```
В отдельном терминале: `streamlit run dashboard/app.py`.

## Функции
- Добавление, просмотр, изменение и удаление книг, авторов и читателей.
- Поиск книг по названию, автору, ISBN и жанру.
- Оформление выдачи книги и регистрация возврата.
- Проверка наличия доступных экземпляров.
- Отчёт по количеству книг, читателей, активных и просроченных выдач.
- Демонстрационные данные для проверки.

## Основные маршруты API
| Метод | Маршрут | Назначение |
|---|---|---|
| GET/POST | `/api/books/` | Список / добавление книг |
| GET/PATCH/DELETE | `/api/books/{id}/` | Просмотр / изменение / удаление книги |
| GET/POST | `/api/authors/` | Список / добавление авторов |
| GET/POST | `/api/readers/` | Список / регистрация читателей |
| GET/POST | `/api/loans/` | Список / оформление выдач |
| POST | `/api/loans/{id}/return_book/` | Возврат книги |
| GET | `/api/reports/summary/` | Сводная статистика |
| GET | `/api/health/` | Проверка API |

Проект предназначен для учебной демонстрации. Для реального внедрения следует настроить аутентификацию, права доступа и резервное копирование.
