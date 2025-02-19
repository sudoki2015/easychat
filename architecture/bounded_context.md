```mermaid
graph TD
    style A fill:#f9f,stroke:#333,stroke-width:4px
    style B fill:#ccf,stroke:#333,stroke-width:4px
    style C fill:#cfc,stroke:#333,stroke-width:4px
    style D fill:#fcc,stroke:#333,stroke-width:4px
    style E fill:#fcf,stroke:#333,stroke-width:4px
    style F fill:#cff,stroke:#333,stroke-width:4px
    style G fill:#ccf,stroke:#333,stroke-width:4px
    style H fill:#fff,stroke:#333,stroke-width:4px
    style I fill:#fcd,stroke:#333,stroke-width:4px

    subgraph "Пользователь"
        direction TB
        A1[Пользователь]
    end

    subgraph "Веб и мобильный браузер"
        direction TB
        B1[Веб-браузер]
        B2[Мобильный браузер]
    end

    subgraph "Система"
        direction TB
        C1[Компонент регистрации]
        C2[Компонент аутентификации]
        C3[Сервис чатов]
        C4[Сервис сообщений]
        C5[Сервис уведомлений]
        C6[Сервис шифрования]
        C7[Сервис синхронизации]
        C8[Сервис базы данных]
        C9[Сервис отправки электронных писем]  %% Новый компонент
    end

    A1 -->|Запрос на регистрацию| C1
    A1 -->|Запрос на авторизацию| C2
    C1 -->|Создание пользователя| C8
    C2 -->|Проверка данных пользователя| C8
    C1 -->|Отправка подтверждения на email| C9  %% Новый путь
    C9 -->|Отправка письма с подтверждением регистрации| A1
    C3 -->|Создание чатов| C8
    C3 -->|Управление участниками| C8
    C3 -->|Поиск чатов| C8
    C4 -->|Отправка сообщений| C8
    C5 -->|Уведомления о новых сообщениях| C4
    C6 -->|Шифрование сообщений| C4
    C7 -->|Синхронизация сообщений| C4
    C8 -->|Хранение данных пользователей| A1
    C8 -->|Хранение данных чатов| C3
    C8 -->|Хранение сообщений| C4

```