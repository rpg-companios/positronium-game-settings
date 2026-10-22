# Инструменты упаковки

`pack-setting.py` — собрать `.trpg` из папки кошелька.
`unpack-setting.py` — проверить и распаковать `.trpg` в отдельную папку.
`build-setting-runtime.mjs` — собрать CommonJS runtime-бандл, объявленный в манифесте.
`host-modules.json` — какие `engine:` модули отдаёт хост движка (обновляет публикация).

Сборка не требует checkout движка: кошелёк обращается к движку только через
`engine:<id>`, эти импорты остаются внешними и их отдаёт приложение.

```bash
npm install --prefix tools      # ставит esbuild в tools/node_modules
python3 tools/pack-setting.py fallout -o dist/fallout.trpg
python3 tools/unpack-setting.py dist/fallout.trpg --dest /tmp/check --force
```

Скрипты не запускают код сеттинга: они только проверяют манифест и укладывают файлы.
