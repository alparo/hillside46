# Hillside46 ZMK Config

ZMK firmware keymap for Hillside46 split keyboard (nice_nano_v2 controller).

## Key files

- `config/hillside46.keymap` — главный файл: слои, поведения, макросы
- `config/combos.dtsi` — все комбо-клавиши (включается в keymap)
- `config/hillside46.conf` — настройки Kconfig (bluetooth, sleep, RGB и т.д.)
- `config/west.yml` — версия ZMK (сейчас pinned на v0.3.0)
- `build.yaml` — матрица сборки для GitHub Actions (hillside46_left + hillside46_right)

## Слои

| # | Название        | Описание                                 |
|---|-----------------|------------------------------------------|
| 0 | DEF             | QWERTY, homerow mods                     |
| 1 | NUM             | Цифры, символы, F-клавиши               |
| 2 | NAV             | Навигация, символы, медиа               |
| 3 | HK              | Hotkeys (Alt+N комбо, window management) |
| 4 | ADJ             | Bluetooth, system (NUM+NAV одновременно) |
| 5 | FZ              | FancyZones, управление окнами            |

ADJ активируется через conditional_layer при одновременном удержании NUM и NAV.

## Сборка

Через GitHub Actions — push в main триггерит сборку, артефакты (.uf2) скачиваются из workflow.

## Соглашения

- Документация ведётся прямо в комментариях в коде
- Каждый слой должен иметь ASCII-диаграмму раскладки в комментарии

## Git

- `origin` → форк пользователя: `https://github.com/alparo/hillside46.git`
- `upstream` → оригинал: `https://github.com/mmccoyd/zmk-config.git`
- Пушить только в `origin`

## Documentation

- we try to keep the comments in the `config/hillside46.keymap` updated
- when adding keymap diagrams use following letters for modifiers:
  G - Win/Gui/Meta
  A - Alt
  S - Shift
  C - Control
- always exactly in this order. So, for example:
  - for alt+win+h the diagram should have GA-h
  - for shift+ctrl+gui+alt+right it will be GASC-->
  - for alt+5: A-5
