# Claude Code БЕСПЛАТНО в 2026 — 3 способа без подписки

Команды и ссылки из ролика **«CLAUDE CODE БЕСПЛАТНО? 3 способа без подписки»** на YouTube-канале **КриптоДвиж**.
https://www.youtube.com/@DvizhGem


> Проверено: сентябрь 2026 года

## Коротко: какой способ выбрать

| Способ | Цена | Что используется | Сложность |
|---|---:|---|---|
| **OpenRouter Free** | $0 | бесплатные сторонние модели | просто |
| **Free Claude Code + NVIDIA** | $0 | модели через NVIDIA NIM | средне |
| **AnyModel** | по токенам, без подписки | Claude, GPT, Gemini и другие | просто/средне |

---

## 1. OpenRouter Free — полностью бесплатно

Подходит, если хочется просто запустить Claude Code без подписки и без оплаты.

**Важно:** `openrouter/free` не означает бесплатный Claude Sonnet / Opus. OpenRouter выбирает одну из доступных бесплатных сторонних моделей.

### Шаг 1. Создать ключ OpenRouter

Открыть:

https://openrouter.ai/

Зарегистрироваться → **Keys → Create Key**.

Скопировать API-ключ. Он выглядит примерно так:

```text
sk-or-v1-xxxxxxxx
```

Никому не отправляйте свой настоящий API-ключ и не добавляйте его в GitHub.

### Шаг 2. Установить Claude Code

Открыть **PowerShell**:

```powershell
irm https://claude.ai/install.ps1 | iex
```

После установки закрыть PowerShell и открыть заново.

### Шаг 3. Подключить OpenRouter

Вместо `ТВОЙ_КЛЮЧ` вставить свой ключ OpenRouter:

```powershell
$env:OPENROUTER_API_KEY="ТВОЙ_КЛЮЧ"
```

Подключаем OpenRouter к Claude Code:

```powershell
$env:ANTHROPIC_BASE_URL="https://openrouter.ai/api"
$env:ANTHROPIC_AUTH_TOKEN=$env:OPENROUTER_API_KEY
$env:ANTHROPIC_API_KEY=""
```

Направляем основные модели Claude Code в бесплатный роутер:

```powershell
$env:ANTHROPIC_DEFAULT_OPUS_MODEL="openrouter/free"
$env:ANTHROPIC_DEFAULT_SONNET_MODEL="openrouter/free"
$env:ANTHROPIC_DEFAULT_HAIKU_MODEL="openrouter/free"
$env:ANTHROPIC_DEFAULT_FABLE_MODEL="openrouter/free"
$env:CLAUDE_CODE_SUBAGENT_MODEL="openrouter/free"
```

### Шаг 4. Создать папку и запустить

```powershell
mkdir C:\claude-test
cd C:\claude-test
claude
```

Если Claude Code попросит доверять папке — подтверждаем.

Проверить подключение можно командой внутри Claude Code:

```text
/status
```

Если Claude Code пытается использовать старую авторизацию Anthropic:

```text
/logout
```

Затем закрыть Claude Code и снова выполнить:

```powershell
claude
```

### Тест из ролика

```text
Создай простую HTML-страницу с формой заметок, сохранением в localStorage и кнопкой удаления заметки. Создай необходимые файлы прямо в текущей папке.
```

На момент моего теста бесплатный аккаунт OpenRouter давал до **50 запросов в день**. Лимиты могут измениться.

Официальный гайд OpenRouter по Claude Code:

https://openrouter.ai/blog/tutorials/claude-code-openrouter/

---

## 2. Free Claude Code + NVIDIA NIM

Этот вариант тоже можно использовать без подписки, но настройка длиннее: между Claude Code и моделью работает локальный прокси **Free Claude Code (FCC)**.

Исходный проект:

https://github.com/Alishahryar1/free-claude-code

### Шаг 1. Установить Free Claude Code

Windows PowerShell:

```powershell
& ([scriptblock]::Create((irm "https://raw.githubusercontent.com/Alishahryar1/free-claude-code/main/scripts/install.ps1")))
```

Во время установки выбрать Claude Code.

### Шаг 2. Получить NVIDIA NIM API key

Открыть:

https://build.nvidia.com/settings/api-keys

Создать API-ключ NVIDIA.

> В моём тесте для регистрации NVIDIA понадобились зарубежный IP и подтверждение номера телефона. Условия регистрации зависят от региона и могут измениться.

### Шаг 3. Запустить FCC

На Windows можно открыть **Free Claude Code** через меню «Пуск».

Если используется CLI, запустить сервер:

```powershell
fcc-server
```

После запуска откроется локальная админка. По умолчанию:

```text
http://127.0.0.1:8082/admin
```

Вставить ключ в поле:

```text
NVIDIA_NIM_API_KEY
```

Нажать **Validate**, затем **Apply**.

### Шаг 4. Запустить Claude Code

Если сервер запущен через `fcc-server`, это окно PowerShell не закрывать.

Открыть **второе** окно PowerShell:

```powershell
fcc-claude
```

### Ошибка: proxy is not reachable

Если появляется:

```text
Free Claude Code proxy is not reachable at http://127.0.0.1:8082
```

значит локальный FCC-сервер не запущен или недоступен.

В первом окне:

```powershell
fcc-server
```

Во втором:

```powershell
fcc-claude
```

Можно проверить админку в браузере:

```text
http://127.0.0.1:8082/admin
```

---

## 3. AnyModel — Claude Code без ежемесячной подписки

Моя ссылка:

https://anymodel.org/?ref=CRYPTODV

AnyModel работает по предоплаченному балансу с оплатой по токенам, без обязательной ежемесячной подписки. Один API-ключ можно использовать с Claude, GPT, Gemini и другими доступными моделями.

### Бонусные токены

Регистрация по ссылке:

https://anymodel.org/?ref=CRYPTODV

даёт **+5 000 000 токенов дополнительно**.

После регистрации можно пройти верификацию через Telegram и получить ещё:

```text
+5 000 000 токенов
```

Итого на момент публикации гайда можно получить **до 10 000 000 бонусных токенов**:

- +5 млн — за регистрацию по ссылке выше;
- +5 млн — за верификацию через Telegram.

Условия и размер бонусов могут измениться, поэтому перед регистрацией проверьте актуальную информацию на сайте.

### Подключение Claude Code

Официальная инструкция:

https://anymodel.org/ru/use/claude-code

Endpoint:

```text
https://anymodel.org/v1
```

Для macOS/Linux официальный установщик выглядит так:

```bash
bash <(curl -fsSL "https://anymodel.org/i?tool=claude&model=claude-sonnet-4-6") <YOUR_API_KEY>
```

На Windows после входа в AnyModel откройте страницу инструкций и используйте сгенерированный вариант для **PowerShell** — в нём уже подставляется ваш API-ключ.


Чат AnyModel для вайбкодеров:

https://t.me/vibecoding_anymodel

---

## КриптоДвиж

Практические гайды по AI, крипте, зарубежным сервисам и оплате.

https://www.youtube.com/@DvizhGem

Telegram:

https://t.me/+Y7Hrt_9XkM1mZjZi
