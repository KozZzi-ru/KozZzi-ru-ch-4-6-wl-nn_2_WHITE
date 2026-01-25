# ch-4-6-wl-nn

4-6 wireless zmk
7
KozZzi adopted

версия прошивки с плавным скролом 
переделана под МК1, навален мой кеймаппинг

## Изменения в бранче keymap-drawer-integration

### Добавлена автогенерация SVG-схемы клавиатуры

Теперь при каждом коммите автоматически генерируется визуальная схема раскладки клавиатуры с помощью [keymap-drawer](https://github.com/caksoylar/keymap-drawer).

#### Добавленные файлы:

1. **`.github/workflows/draw_keymaps.yaml`**
   - Reusable workflow для автоматической генерации SVG-схем клавиатуры
   - Запускается после сборки прошивки
   - Парсит `config/charybdis.keymap` и генерирует SVG+YAML

2. **`keymap-drawer/config.yaml`**
   - Конфигурация внешнего вида генерируемой SVG-схемы
   - Настройки размеров, отступов, маппинг клавиш
   - Поддержка темной/светлой темы (auto)

3. **`keymap-drawer/charybdis.yaml`**
   - Базовое описание раскладки для Charybdis 4x6
   - Можно редактировать вручную для точной настройки визуализации

#### Измененные файлы:

- **`.github/workflows/main.yml`**
  - Добавлен джоб `keymap_images`
  - Запускается после сборки прошивки
  - Вызывает `draw_keymaps.yaml` workflow

### Результат

После каждого коммита в папке `keymap-drawer/` автоматически обновляются:
- **`charybdis.svg`** - визуальная схема раскладки
- **`charybdis.yaml`** - YAML-описание раскладки

Схему можно просматривать напрямую в GitHub или добавить в README:

```markdown
![Keymap](keymap-drawer/charybdis.svg)
```

### Кредиты

Интеграция основана на [keymap-drawer](https://github.com/caksoylar/keymap-drawer) by [@caksoylar](https://github.com/caksoylar)
