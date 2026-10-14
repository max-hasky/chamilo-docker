# chamilo-docker

[English](#english) | [Русский](#русский)

---

## English

**chamilo-docker** is a project that allows you to easily and quickly run the **Chamilo LMS** inside Docker containers. The build is optimized to work on various platforms, including single-board computers like the **Orange Pi 3**.

### Features

*   Quick launch of Chamilo LMS with a single command.
*   Complete isolation of the application, database, and dependencies.
*   **ARM64 architecture support**, ensuring stable operation on **Orange Pi 3** and similar microcomputers.
*   Simple configuration via environment variables.

### Prerequisites

Before you begin, ensure you have the following installed:
*   [Docker](https://docker.com)
*   [Docker Compose](https://docker.com)

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/max-hasky/chamilo-docker
   cd chamilo-docker
   ```

2. **Run the containers:**
   ```bash
   docker compose up -d
   ```

After the containers start, Chamilo will be available in your browser at `http://localhost:8080` (or the port specified in your `.env` file).

### Usage on Orange Pi 3

The project is fully compatible with Ubuntu/Debian running on the **Orange Pi 3**. Docker will automatically pull or build the image for the `linux/arm64` architecture.

If you are building the image manually on your Orange Pi, use the following command:
```bash
docker compose build
```

### Container Management

*   **Stop:** `docker compose down`
*   **View logs:** `docker compose logs -f`
*   **Restart:** `docker compose restart`

---

## Русский

**chamilo-docker** — это проект, который позволяет легко и быстро запускать **Chamilo LMS** в Docker-контейнерах. Сборка оптимизирована для работы на различных платформах, включая одноплатные компьютеры вроде **Orange Pi 3**.

### Особенности

*   Быстрый запуск Chamilo LMS одной командой.
*   Полная изоляция приложения, базы данных и их зависимостей.
*   **Поддержка архитектуры ARM64**, что гарантирует стабильную работу на **Orange Pi 3** и аналогичных микрокомпьютерах.
*   Простая настройка через переменные окружения.

### Требования

Перед началом работы убедитесь, что у вас установлены:
*   [Docker](https://docker.com)
*   [Docker Compose](https://docker.com)

### Быстрый старт

1. **Клонируйте репозиторий:**
   ```bash
   git clone https://github.com/max-hasky/chamilo-docker
   cd chamilo-docker
   ```

2. **Запустите контейнеры:**
   ```bash
   docker compose up -d
   ```

После запуска контейнеров Chamilo станет доступен в браузере по адресу `http://localhost:8080` (или порту, который вы укажете в `.env`).

### Использование на Orange Pi 3

Проект полностью совместим с Ubuntu/Debian, запущенными на **Orange Pi 3**. Docker автоматически подтянет или соберет образ под архитектуру `linux/arm64`. 

Если вы собираете образ вручную на Orange Pi, используйте команду:
```bash
docker compose build
```

### Управление контейнерами

*   **Остановка:** `docker compose down`
*   **Просмотр логов:** `docker compose logs -f`
*   **Перезапуск:** `docker compose restart`
