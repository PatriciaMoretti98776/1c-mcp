# Awesome 1C MCP Servers

[![Check Links](https://github.com/Untru/1c-mcp/actions/workflows/links.yml/badge.svg)](https://github.com/Untru/1c-mcp/actions/workflows/links.yml)
[![Update Top](https://github.com/Untru/1c-mcp/actions/workflows/update-top.yml/badge.svg)](https://github.com/Untru/1c-mcp/actions/workflows/update-top.yml)

Каталог MCP-серверов, плагинов и наборов skills, которые подключают AI-ассистентов (Claude Code, Codex, Cursor, VS Code Copilot и др.) к 1С:Предприятие.

**Зачем это всё.** Сама по себе нейросеть про вашу 1С ничего не знает: не видит метаданные, путает методы платформы, не может запустить тест. [MCP](https://modelcontextprotocol.io) — стандартный «разъём», через который агенту дают инструменты: прочитать структуру конфигурации, найти процедуру, заглянуть в справку, выполнить запрос к базе, прогнать проверку. Skills — готовые инструкции, как этими инструментами пользоваться в типовых задачах 1С. Здесь собрано то, что для этого уже есть.

> **Что нового** — в [последнем релизе](https://github.com/Untru/1c-mcp/releases/latest) и [CHANGELOG.md](CHANGELOG.md).
> Нашли проект, которого тут нет? [Откройте issue](https://github.com/Untru/1c-mcp/issues/new?template=new-server.yml) или PR — см. [CONTRIBUTING.md](CONTRIBUTING.md).

## Содержание

- [Топ по звёздам](#топ-по-звёздам)
- [С чего начать](#с-чего-начать)
- [Каталог](#каталог)
  - [IDE-интеграции](#ide-интеграции)
  - [Живая база и фреймворки](#живая-база-и-фреймворки)
  - [Метаданные и анализ кода](#метаданные-и-анализ-кода)
  - [Справка платформы](#справка-платформы)
  - [Проверка кода и тестирование](#проверка-кода-и-тестирование)
  - [UI-тестирование и агент в интерфейсе](#ui-тестирование-и-агент-в-интерфейсе)
  - [1С:Напарник](#1снапарник)
  - [Учётные системы и данные](#учётные-системы-и-данные)
  - [Инфраструктура и DevOps](#инфраструктура-и-devops)
  - [1C:Element](#1celement)
  - [Плагины, правила и skills](#плагины-правила-и-skills)
  - [Коммерческие продукты](#коммерческие-продукты)
- [Типовые связки](#типовые-связки)

## Топ по звёздам

Open-source проекты каталога по числу звёзд на GitHub. Таблица пересобирается автоматически каждый понедельник ([workflow](.github/workflows/update-top.yml), [скрипт](scripts/update_top.py)).

<!-- TOP:START -->
| # | Проект | ⭐ | Что это | Раздел | Последний коммит |
|--:|--------|--:|---------|--------|------------------|
| 1 | [cc-1c-skills](https://github.com/Nikolay-Shirokov/cc-1c-skills) | 682 | Самый популярный набор skills для 1С: полный цикл разработки для Claude Code, Cursor и Codex | [Плагины, правила и skills](#плагины-правила-и-skills) | 2026-10-11 |
| 2 | [1c_mcp](https://github.com/vladimir-kharin/1c_mcp) | 536 | Фреймворк, чтобы сделать MCP-сервер из самой базы 1С | [Живая база и фреймворки](#живая-база-и-фреймворки) | 2026-10-05 |
| 3 | [ai_rules_1c](https://github.com/comol/ai_rules_1c) | 483 | Правила, субагенты и skills для AI-разработки на 1С — для любого агента | [Плагины, правила и skills](#плагины-правила-и-skills) | 2026-10-07 |
| 4 | [1c-mcp-toolkit](https://github.com/ROCTUP/1c-mcp-toolkit) | 305 | Живая база для агента за пять минут — просто открыть обработку | [Живая база и фреймворки](#живая-база-и-фреймворки) | 2026-10-11 |
| 5 | [EDT-MCP](https://github.com/DitriXNew/EDT-MCP) | 297 | Плагин, который открывает AI-агенту рабочее пространство 1C:EDT | [IDE-интеграции](#ide-интеграции) | 2026-10-12 |
| 6 | [mcp-1c](https://github.com/feenlace/mcp-1c) | 242 | Один Go-бинарник, который даёт агенту и живую базу, и поиск по коду | [Метаданные и анализ кода](#метаданные-и-анализ-кода) | 2026-10-02 |
| 7 | [Unica](https://github.com/IngvarConsulting/unica) | 225 | Плагин для Claude Code и Codex: skills плюс собственный MCP runtime для 1С | [Плагины, правила и skills](#плагины-правила-и-skills) | 2026-10-12 |
| 8 | [rlm-tools-bsl](https://github.com/Dach-Coin/rlm-tools-bsl) | 208 | Анализ огромных конфигураций (ERP, УХ) без RAG и без траты токенов на чтение файлов | [Метаданные и анализ кода](#метаданные-и-анализ-кода) | 2026-10-08 |
| 9 | [mcp-bsl-platform-context](https://github.com/alkoleft/mcp-bsl-platform-context) | 199 | Синтакс-помощник для AI — чтобы агент перестал выдумывать методы платформы | [Справка платформы](#справка-платформы) | 2026-03-10 |
| 10 | [mcp-1c-v1](https://github.com/fserg/mcp-1c-v1) | 167 | RAG по структуре конфигурации: «найди, где хранится X» на естественном языке | [Метаданные и анализ кода](#метаданные-и-анализ-кода) | 2025-08-04 |
| 11 | [CodePilot1C](https://github.com/ondysss/codepilot1c-edt) | 156 | AI-ассистент, встроенный прямо в EDT: чат, агентный режим и MCP Host | [IDE-интеграции](#ide-интеграции) | 2026-10-03 |
| 12 | [code-index-mcp](https://github.com/Regsorm/code-index-mcp) | 141 | Быстрый индекс кода для агента: один бинарник, SQLite, ответ за миллисекунды | [Метаданные и анализ кода](#метаданные-и-анализ-кода) | 2026-10-08 |
| 13 | [mcp-onec-test-runner](https://github.com/alkoleft/mcp-onec-test-runner) | 117 | METR — агент сам запускает YaXUnit-тесты, сборку и синтакс-контроль | [Проверка кода и тестирование](#проверка-кода-и-тестирование) | 2026-03-22 |
| 14 | [1c-mcp-metacode](https://github.com/ROCTUP/1c-mcp-metacode) | 108 | Конфигурация в виде графа в Neo4j: объекты, модули, процедуры и связи между ними | [Метаданные и анализ кода](#метаданные-и-анализ-кода) | 2026-08-19 |
| 15 | [bsl-analyzer](https://github.com/itrous/bsl-analyzer) | 108 | Быстрый анализатор BSL на Rust: линтер, LSP и MCP в одном бинарнике | [Проверка кода и тестирование](#проверка-кода-и-тестирование) | 2026-10-12 |
<!-- TOP:END -->

## С чего начать

| Задача | Смотрите |
|--------|----------|
| Работать из 1C:EDT | [EDT-MCP](#edt-mcp), [edt-bridge](#edt-bridge), [CodePilot1C](#codepilot1c) |
| Работать из VS Code / Cursor | [1C: Platform Tools MCP](#1c-platform-tools-mcp), [плагины и skills](#плагины-правила-и-skills) |
| Быстро подключить живую базу | [mcp-1c](#mcp-1c), [1c-mcp-toolkit](#1c-mcp-toolkit) |
| Написать свой MCP-сервер внутри 1С | [1c_mcp](#1c_mcp), [http1c](#http1c) |
| Разобраться в большой конфигурации | [rlm-tools-bsl](#rlm-tools-bsl), [code-index-mcp](#code-index-mcp), [1c-mcp-metacode](#1c-mcp-metacode) |
| Справка по платформе и BSL | [mcp-bsl-platform-context](#mcp-bsl-platform-context), [onec-help-mcp](#onec-help-mcp) |
| Проверять код и гонять тесты | [bsl-analyzer](#bsl-analyzer), [mcp-onec-test-runner](#mcp-onec-test-runner), [v8-runner](#v8-runner) |
| Дать агенту прокликать интерфейс 1С | [1C Testpilot](#1c-testpilot) |
| Работать с данными учёта | [aprovodka](#aprovodka), [mcp-rsv-data](#mcp-rsv-data), [ARQA](#коммерческие-продукты) |
| Готовые skills для Claude Code / Codex / Cursor | [cc-1c-skills](#cc-1c-skills), [Unica](#unica), [ai_rules_1c](#ai_rules_1c), [claude-code-skills-1c](#claude-code-skills-1c) |

## Каталог

Строка под названием: стек · транспорт MCP · требования · статус.
Статусы: ✅ стабилен и развивается · 🚧 бета, API может меняться · 🔬 эксперимент · 📦 не поддерживается.

### IDE-интеграции

#### [EDT-MCP](https://github.com/DitriXNew/EDT-MCP)

**Плагин, который открывает AI-агенту рабочее пространство 1C:EDT.**
Агент видит проект так же, как вы в IDE: ходит по метаданным и модулям, строит иерархию вызовов, получает подсказки Content Assist, проверяет текст запроса (включая режим СКД), снимает скриншоты форм, обновляет базу и запускает отладку. Главный выбор, если вы живёте в EDT и хотите, чтобы агент опирался на её понимание кода, а не на grep по файлам.

С версии 2.18 умеет ещё и создать EDT-проект из `.cf`/`.cfe`/`.epf`/`.erf` и выгрузить конфигурацию обратно в `.cf`/`.cfe`.

Java · HTTP, SSE · EDT 2025.2+ · ✅ ![stars](https://img.shields.io/github/stars/DitriXNew/EDT-MCP?style=flat&label=%E2%AD%90)

#### [edt-bridge](https://github.com/keyfire/edt-bridge)

**Живая семантическая модель EDT для агента — не только чтение, но и запись.**
Агент спрашивает не файлы, а запущенную IDE: реальные ошибки валидации EDT, типы метаданных, перекрёстные ссылки, проверку запроса по метаданным проекта, синтакс-помощник. Плюс инструменты записи и рефакторинга, работа с ИБ и отладчик. Запись защищена токеном и сначала возвращает план. Автор — тот же, что у elemctl и xbsl.

Java · HTTP (localhost) · EDT · 🚧 ![stars](https://img.shields.io/github/stars/keyfire/edt-bridge?style=flat&label=%E2%AD%90)

#### [AI-EDT](https://github.com/Desko77/ai-edt)

**MCP-сервер внутри EDT, который отвечает на вопросы «что от чего зависит».**
Какие формы, роли и подсистемы используют справочник, на какой объект указывает ссылка — всё через семантическую модель EDT, а не поиском по XML. Есть валидация и живая отладка. Работает в паре с [claude-code-skills-1c](#claude-code-skills-1c) того же автора. EDT 2026.1–2026.2.

Java · HTTP · EDT 2026.1+ · 🚧 ![stars](https://img.shields.io/github/stars/Desko77/ai-edt?style=flat&label=%E2%AD%90)

#### [1C_EDT_MCP_PUBLIC](https://github.com/fedukhin-sys/1C_EDT_MCP_PUBLIC)

**Плагин EDT со 106 MCP-инструментами — самый широкий охват IDE.**
Workspace, модули, метаданные, формы, СКД, информационные базы (включая синхронизацию `.dt`/`.cfe`), журнал регистрации, отладка, запуск клиента и xUnitFor1C. Внимание: у репозитория нет лицензии, для коммерческого использования уточняйте у автора.

Java · HTTP, SSE · EDT 2023.x–2026.x · 🚧 ![stars](https://img.shields.io/github/stars/fedukhin-sys/1C_EDT_MCP_PUBLIC?style=flat&label=%E2%AD%90)

#### [CodePilot1C](https://github.com/ondysss/codepilot1c-edt)

**AI-ассистент, встроенный прямо в EDT: чат, агентный режим и MCP Host.**
Не сервер для внешнего агента, а сам агент внутри IDE. Работает с BSL AST, формами и метаданными, умеет запускать QA-команды и подключать сторонние MCP-серверы. Можно подставить свою модель. Удобен тем, кто не хочет выходить из EDT в терминал.

Java · MCP Host · EDT, JDK 17 · ✅ ![stars](https://img.shields.io/github/stars/ondysss/codepilot1c-edt?style=flat&label=%E2%AD%90)

#### [1C: Platform Tools MCP](https://github.com/yellow-hammer/mcp-1c-platform-tools)

**MCP-обёртка над VS Code-расширением [1C: Platform Tools](https://marketplace.visualstudio.com/items?itemName=yellow-hammer.1c-platform-tools).**
Всё, что расширение умеет делать с проектом 1С (сборка, выгрузка, запуск и т. п.), становится доступным агенту в Cursor, VS Code или любом MCP-клиенте. С версии 0.3 — ещё и запросы к данным базы через OData. Для тех, кто ведёт 1С-проекты в VS Code, а не в EDT.

TypeScript · stdio · VS Code/Cursor + расширение · ✅ ![stars](https://img.shields.io/github/stars/yellow-hammer/mcp-1c-platform-tools?style=flat&label=%E2%AD%90)

#### [BslEdit](https://github.com/alonehobo/BslEdit)

**Лёгкий редактор BSL и «глаза» для агента без запуска 1С.**
Standalone-редактор на Monaco, просмотр форм и макетов так, как они выглядят в Конфигураторе, отчёты проверок кода и MCP-инструменты, чтобы агент мог «увидеть» форму. Ставится одной командой PowerShell и сам подключается к Claude Code, Codex и Cursor.

JavaScript · MCP · Windows · ✅ ![stars](https://img.shields.io/github/stars/alonehobo/BslEdit?style=flat&label=%E2%AD%90)

### Живая база и фреймворки

#### [1c_mcp](https://github.com/vladimir-kharin/1c_mcp)

**Фреймворк, чтобы сделать MCP-сервер из самой базы 1С.**
Ставите расширение `MCP_Сервер.cfe` — вся механика протокола уже внутри. Вам остаётся на BSL описать свои инструменты (`ДобавитьИнструменты()` / `ВыполнитьИнструмент()`), и агент сможет вызывать вашу бизнес-логику. Поддерживает resources и prompts, подключается напрямую по HTTP, через Python-прокси (stdio + OAuth2) или в Docker. Самый популярный проект каталога.

BSL, Python · HTTP, stdio · 8.3+ · ✅ ![stars](https://img.shields.io/github/stars/vladimir-kharin/1c_mcp?style=flat&label=%E2%AD%90)

#### [1c-mcp-toolkit](https://github.com/ROCTUP/1c-mcp-toolkit)

**Живая база для агента за пять минут — просто открыть обработку.**
HTTP-сервер поднимается прямо внутри `.epf`: не нужно менять конфигурацию, публиковать базу на веб-сервере или возиться с COM. Агент выполняет запросы и код, читает метаданные, журнал регистрации и объекты по ссылке. Есть REST API для агентов без MCP, анонимизация чувствительных данных и готовые skills. Хороший вариант «подключиться к клиентской базе и посмотреть».

BSL, Python · HTTP · 8.2.13+ · ✅ ![stars](https://img.shields.io/github/stars/ROCTUP/1c-mcp-toolkit?style=flat&label=%E2%AD%90)

#### [http1c](https://mcpmarket.com/server/http1c)

**Нативная компонента + шаблон обработки для публикации бизнес-логики 1С как MCP-сервера.**
Транспорт вынесен в DLL, поэтому из 1С можно динамически регистрировать tools, resources и prompts с bearer-авторизацией, проверкой origin, rate limiting и пагинацией. Для тех, кому нужен полноценный протокол, а не минимальная обёртка.

BSL, C++ · HTTP, SSE · ✅

#### [ИИкона (1c-ai-connector)](https://github.com/andromanpro/1c-ai-connector)

**ИИ-платформа внутри 1С, которая ставится расширением.**
Не только MCP-сервер для внешних агентов, но и агентская петля с function calling к пяти+ провайдерам (OpenAI, Anthropic, Google, DeepSeek, GigaChat, Yandex), RAG по базе знаний на Qdrant, мониторинг ошибок с ИИ-диагнозом и алертами в Telegram, генератор диаграмм. Подходит, когда AI нужен пользователям самой 1С, а не только разработчику.

BSL · HTTP · 8.3.24+, БСП 3.1.10+ · ✅ ![stars](https://img.shields.io/github/stars/andromanpro/1c-ai-connector?style=flat&label=%E2%AD%90)

#### [onec-client-mcp-devkit](https://github.com/1c-neurofish/onec-client-mcp-devkit)

**MCP-сервер, который живёт прямо в клиенте 1С:Предприятие.**
Расширение поднимает сервер в клиентском контуре через внешнюю компоненту WebTransport: агенту доступны tools, resources и prompts от имени открытого сеанса пользователя. На нём, например, строят «ИИ-оператора», который работает в интерфейсе вместо человека. Стабильного релиза пока нет.

BSL · WebTransport · 🚧 ![stars](https://img.shields.io/github/stars/1c-neurofish/onec-client-mcp-devkit?style=flat&label=%E2%AD%90)

#### [v8-session-manager](https://github.com/1c-neurofish/v8-session-manager)

**Собирает инструменты нескольких открытых клиентов 1С в один MCP endpoint.**
Клиенты 1С подключаются по WebSocket и публикуют свои tools (например, через [onec-client-mcp-devkit](#onec-client-mcp-devkit)), а агент видит их единым списком с префиксами по сессиям. Нужен, когда агент должен работать с несколькими базами или сеансами одновременно.

Rust · HTTP · 🚧 ![stars](https://img.shields.io/github/stars/1c-neurofish/v8-session-manager?style=flat&label=%E2%AD%90)

### Метаданные и анализ кода

#### [mcp-1c](https://github.com/feenlace/mcp-1c)

**Один Go-бинарник, который даёт агенту и живую базу, и поиск по коду.**
Подключается к HTTP-сервису 1С (расширение ставит сам): метаданные, формы, запросы с параметрами, журнал регистрации. Если рядом лежит выгрузка конфигурации — ищет по BSL (BM25, regex, точное совпадение). Без Python, Docker и прочего рантайма — скачал и запустил.

Go · stdio · 8.3+ · ✅ ![stars](https://img.shields.io/github/stars/feenlace/mcp-1c?style=flat&label=%E2%AD%90)

#### [rlm-tools-bsl](https://github.com/Dach-Coin/rlm-tools-bsl)

**Анализ огромных конфигураций (ERP, УХ) без RAG и без траты токенов на чтение файлов.**
Вместо того чтобы агент сам читал тысячи модулей, он пишет короткие скрипты в песочнице с 60+ хелперами поверх SQLite-индекса методов и графа вызовов. Понимает CF, EDT, CFE, MDO и кириллицу. Хорош для вопросов «как устроен этот механизм» и «где это вызывается».

Python · HTTP, stdio · платформа не нужна · ✅ ![stars](https://img.shields.io/github/stars/Dach-Coin/rlm-tools-bsl?style=flat&label=%E2%AD%90)

#### [code-index-mcp](https://github.com/Regsorm/code-index-mcp)

**Быстрый индекс кода для агента: один бинарник, SQLite, ответ за миллисекунды.**
Разбирает выгрузки Конфигуратора и EDT (конфигурация на 88 тыс. файлов индексируется минут за шесть) и даёт 32 инструмента: 20 универсальных на tree-sitter для 14 языков и 12 специально под 1С/BSL. Ставится одной командой, без Python и Docker. Хорош, когда агенту нужно быстро найти «где объявлено» и «кто вызывает» в большой конфигурации.

Rust · stdio · платформа не нужна · ✅ ![stars](https://img.shields.io/github/stars/Regsorm/code-index-mcp?style=flat&label=%E2%AD%90)

#### [gyrfalcon](https://github.com/aleksandrgradoboev-svg/gyrfalcon)

**Детерминированный индекс конфигурации: код, метаданные и граф вызовов в одном бинарнике.**
Конфигурацию на 18 000+ модулей индексирует примерно за минуту, дальше обновляется по изменённым файлам и сам отмечает, если ответ устарел. Каждая связь в графе вызовов помечена, насколько уверенно она распознана, поэтому «не смогли разрешить» отличается от «разрешать нечего». Знает 27 видов метаданных (реквизиты с типами, права ролей, подписки, регламентные задания, движения регистров, XDTO), перехваты расширений с местом вставки и офлайн-семантический поиск по именам. Один сервер держит несколько конфигураций.

Rust · stdio · XML-выгрузка, Windows x64 · 🚧 ![stars](https://img.shields.io/github/stars/aleksandrgradoboev-svg/gyrfalcon?style=flat&label=%E2%AD%90)

#### [bsl-atlas](https://github.com/Arman-Kudaibergenov/bsl-atlas)

**Индекс и поиск по исходникам 1С: процедуры, метаданные, связи и граф вызовов.**
Работает с XML/BSL-выгрузкой конфигурации или расширения. Режим `fast` — структурный поиск через SQLite/FTS без внешних embedding API, полный режим добавляет векторный поиск. Переиндексация после новой выгрузки.

Python · MCP · Docker · ✅ ![stars](https://img.shields.io/github/stars/Arman-Kudaibergenov/bsl-atlas?style=flat&label=%E2%AD%90)

#### [1c-mcp-metacode](https://github.com/ROCTUP/1c-mcp-metacode)

**Конфигурация в виде графа в Neo4j: объекты, модули, процедуры и связи между ними.**
Грузит метаданные прямо из XML-выгрузки (можно по расписанию), учитывает расширения, строит граф вызовов, делает семантический поиск по BSL и AI-саммари объектов. С версии 2.0 — 22 типизированных инструмента и веб-консоль со встроенным агентом. Для тех, кому нужен «гугл по конфигурации» для всей команды.

Python · stdio · Neo4j · ✅ ![stars](https://img.shields.io/github/stars/ROCTUP/1c-mcp-metacode?style=flat&label=%E2%AD%90)

#### [bsl-graph](https://github.com/alkoleft/bsl-graph)

**Граф знаний конфигурации в NebulaGraph с интерактивной визуализацией.**
Разбирает выгрузку Конфигуратора или EDT и позволяет и человеку (веб-интерфейс на Sigma.js), и агенту (MCP) исследовать связи между объектами. Не обновлялся с осени 2025.

Kotlin · MCP, REST · JDK 17, NebulaGraph · 🚧 ![stars](https://img.shields.io/github/stars/alkoleft/bsl-graph?style=flat&label=%E2%AD%90)

#### [mcp-1c-v1](https://github.com/FSerg/mcp-1c-v1)

**RAG по структуре конфигурации: «найди, где хранится X» на естественном языке.**
Обработка выгружает структуру, Docker Compose поднимает Qdrant, эмбеддинги, загрузчик и MCP-сервер. Один из первых проектов в нише, давно не обновлялся.

TypeScript · HTTP · Docker · 🚧 ![stars](https://img.shields.io/github/stars/FSerg/mcp-1c-v1?style=flat&label=%E2%AD%90)

#### [1C_MCP_metadata](https://github.com/artesk/1C_MCP_metadata)

**Метаданные конфигурации через расширение с HTTP-сервисом и PowerShell-мостом.**
Структура, поиск по имени/синониму и проверка текста запроса. Минималистичный вариант без Python и Docker. Не обновлялся с 2025 года.

BSL, PowerShell · stdio · 8.3+ · 🚧 ![stars](https://img.shields.io/github/stars/artesk/1C_MCP_metadata?style=flat&label=%E2%AD%90)

#### [1c-templates-mcp](https://yellowmcp.com/servers/1c-templates-mcp)

**Библиотека из 2200+ шаблонов BSL-кода с семантическим поиском.**
Агент ищет готовую заготовку («отправка почты», «запись в регистр») вместо того чтобы сочинять с нуля. Шаблоны можно редактировать в веб-интерфейсе.

Python · SSE · Docker, ChromaDB · ✅

### Справка платформы

#### [mcp-bsl-platform-context](https://github.com/alkoleft/mcp-bsl-platform-context)

**Синтакс-помощник для AI — чтобы агент перестал выдумывать методы платформы.**
Нечёткий поиск по типам, методам, свойствам и конструкторам, данные берутся из у