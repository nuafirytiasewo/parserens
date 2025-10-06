# Парсер из закрытого Телеграм-канала для Backend-приложения "Топ энергетиков"

## 🚀 О проекте

Добро пожаловать в репозиторий **"Топ энергетиков"** — инструмент для сбора и обработки данных из закрытого Telegram-канала. Приложение написано на **Python** с использованием **Telethon**.

## 🛠 Используемые технологии

[![Python](https://skillicons.dev/icons?i=py)](https://skillicons.dev)

## 📂 Структура проекта

```sh
energy-parser/
│
├── .env                # Переменные окружения
├── .gitignore          # Исключаемые файлы
├── README.md           # Документация
├── tables/
│   └── data.csv        # Итоговые обработанные данные
│
├── main.py             # Основной парсер (сбор данных из сообщений и преобразование в CSV)
├── localparser.py      # Обработчик данных для FastAPI
└── requirements.txt    # Список зависимостей
```

---

## ⚡ Установка и запуск

### 1️⃣ Подготовка окружения

#### 🔧 Создание и активация виртуального окружения
```bash
python -m venv venv
venv\Scripts\activate  # Windows
source venv/bin/activate  # Linux/macOS
```

#### 📌 Установка зависимостей
```bash
pip install -r requirements.txt
```

#### 📋 Настройка .env
Скопируйте `.env.sample`, переименуйте в `.env` и добавьте свои данные.

### 2️⃣ Запуск Backend

#### 🔍 Получение данных из Телеграм-канала
Выполните команду для сбора сообщений и сохранения их в `./tables/energy_drinks.csv`:
```bash
python main.py
```

#### 🔄 Преобразование данных
Приведение данных к удобному формату (`./tables/data.csv`):
```bash
python localparser.py
```

---

## 📌 Требования к данным из канала

Сообщения должны соответствовать следующему формату:
```
Название: Название
Оценка: 0/10
Описание: Описание
Дата: dd.MM.YYYY
```

✅ **Примеры сообщений:**
1. ![image](https://github.com/user-attachments/assets/5499c358-7c84-4ffb-8ea7-23d8805d35e7)
2. ![image](https://github.com/user-attachments/assets/e18f6916-e233-422f-9e78-9dcc73d0ce6f)
3. ![image](https://github.com/user-attachments/assets/2a4f509f-f7f8-4b81-a1d6-89cd6e59b988)

> ⚠️ **Ошибки парсинга:**
> - Если сообщение не распарсилось при получении данных — оно попадёт в `./tables/errors.csv`.
> - Если сообщение не удалось обработать — оно попадёт в `./tables/unparsed_errors.csv`.

---

## 🛠 Полезные команды

📌 **Просмотр установленных зависимостей**
```bash
pip list
```

💾 **Сохранение зависимостей**
```bash
pip freeze > requirements.txt
```

🗑 **Удаление всех зависимостей**
```bash
pip uninstall -y -r requirements.txt
```

---


