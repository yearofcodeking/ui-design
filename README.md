# ui-design — дизайн интерфейсов для Claude Code

> Напиши Claude «сделай лендинг для барбершопа» или «обнови дашборд» — и он подберёт стиль, палитру, шрифты и правила UX под твой проект, а не нарисует очередной шаблон.

Внутри база для подбора: **84 стиля, 161 палитра, 73 шрифтовые пары, 99 правил UX, 25 типов графиков, 161 тип продукта** и подсказки под 16 стеков (React, Next.js, Vue, Nuxt, Svelte, Angular, Astro, Laravel, SwiftUI, Jetpack Compose, React Native, Flutter, Three.js, Tailwind, shadcn/ui, HTML/CSS).
Лицензия MIT, пользоваться и дорабатывать можно свободно.

## Установка

Две команды в терминале, потом перезапусти Claude Code:

```bash
claude plugin marketplace add yearofcodeking/ui-design
```

```bash
claude plugin install ui-design@ui-design
```

Обновление: `claude plugin marketplace update ui-design`. Удаление: `claude plugin uninstall ui-design@ui-design`.

## Что нужно заранее

Python 3 (`python --version`): на нём работает поиск по базе стилей и палитр. Для работы со shadcn/ui и Tailwind ещё Node.js 18+.

| Что | Поставить (Windows / macOS / Linux) |
|---|---|
| Python 3 | `winget install Python.Python.3.12` / `brew install python3` / `sudo apt install python3` |
| Node.js 18+ (по желанию) | `winget install OpenJS.NodeJS.LTS` / `brew install node` / [nodejs.org](https://nodejs.org) |
| Ключ Gemini (по желанию) | aistudio.google.com/apikey, переменная `GEMINI_API_KEY`. Нужен только для генерации логотипов, иконок и мокапов фирменного стиля в скилле `design` |

## Что внутри

Семь скиллов, Claude выбирает нужный по твоему запросу:

| Скилл | Для чего |
|---|---|
| `ui-design` | Главный: подбор стиля, палитры, шрифтов и правил UX, проверка готового интерфейса. Лендинги, дашборды, приложения, магазины |
| `design-system` | Токены (цвета, отступы, шрифты), спецификации компонентов, слайды по системе |
| `ui-styling` | Компоненты на shadcn/ui и Tailwind CSS, тёмная тема, адаптивные раскладки |
| `brand` | Голос бренда, фирменный стиль, брендбук, проверка единообразия |
| `design` | Логотипы, фирменный стиль, иконки, соцсети-картинки, презентации |
| `slides` | Стратегические HTML-презентации с графиками |
| `banner-design` | Баннеры для соцсетей, рекламы и сайтов |

## Как пользоваться

Проси своими словами:

- «сделай лендинг для студии маникюра, спокойный и дорогой»
- «подбери палитру и шрифты для финтех-приложения»
- «проверь мой дашборд по UX: что тут не так»
- «собери дизайн-систему для моего проекта и сохрани её в файл»
- «сделай баннер для YouTube-канала»

Прямые вызовы: `/ui-design:ui-design`, `/ui-design:design-system`, `/ui-design:brand` и так далее.

## Как устроено

```
ui-design/
├─ .claude-plugin/marketplace.json            каталог (чтобы ставилось одной командой)
└─ plugins/ui-design/skills/
   ├─ ui-design/        SKILL.md, data/ (таблицы стилей, палитр, шрифтов, UX), scripts/ (поиск по базе)
   ├─ design-system/    токены, компоненты, слайды
   ├─ ui-styling/       shadcn/ui, Tailwind, шрифты для картинок
   ├─ brand/            голос и стиль бренда
   ├─ design/           логотипы, иконки, соцсети
   ├─ slides/           HTML-презентации
   └─ banner-design/    баннеры
```

## Лицензия

MIT, файл `LICENSE`. Шрифты в `skills/ui-styling/canvas-fonts/` идут под своей лицензией SIL OFL, тексты лежат рядом с шрифтами.
Репозиторий — доработанная копия открытого проекта под MIT, поэтому в `LICENSE` сохранено уведомление об исходном авторе: это требование лицензии.
