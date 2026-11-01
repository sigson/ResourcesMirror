# ResourcesMirror — ветка godot4

Зеркало пресета DotTanks: графические пресеты, манифест v3 (`preset.lst`). Чанки — pck формата
GDPC v3 для Godot 4.7, сырые файлы для сервера и клиента в `raw/`.

Источник: `DotTanks4ProplibStorage`, полная перегенерация:

    python3 DotTanks4ProplibStorage/tools/resource-mirror/mirror_gen.py \
        --project DotTanks4ProplibStorage --out ResourcesMirror \
        --preset DotTanks4ProplibStorage/preset.yml --prune --verify

Адрес зеркала клиенту выдаёт сервер (`server/presets`, ключ `dottanks.mirrors`), подлинность
проверяется по `dottanks.manifestSha256` — sha256 файла `preset.lst`. Новая версия зеркала: новый
хеш в конфиге, и зеркало заливается раньше сервера.
