````md
# geosite-playstation.srs (RU / EN)

## RU

### Что это
`geosite-playstation.srs` — бинарный rule-set в формате **sing-box `.srs`** со списком доменов PlayStation/PSN. Предназначен для **Podkop на OpenWrt** (Podkop использует sing-box).

Файл сгенерирован из `geosite.dat` проекта **Runetfreedom**.

### Как использовать в Podkop (OpenWrt)
1) LuCI → **Podkop → Sections (Секции)**
2) Создай секцию (например `PSN`) или выбери существующую
3) Найди поле **Remote Domains Lists**
4) Вставь эту ссылку:

https://raw.githubusercontent.com/CaliostRa/geosite-playstation.srs/main/geosite-playstation.srs

5) Подними секцию `PSN` **выше** более общих секций (например “всё в прокси/всё direct”), чтобы правило применялось раньше.

### Как это было сгенерировано
- Источник geodata: `runetfreedom/russia-v2ray-rules-dat` (`geosite.dat`)
- Конвертер: `runetfreedom/geodat2srs`

Пример сборки (WSL/Ubuntu):
```bash
curl -L -o geosite.dat https://raw.githubusercontent.com/runetfreedom/russia-v2ray-rules-dat/release/geosite.dat
git clone https://github.com/runetfreedom/geodat2srs.git
cd geodat2srs && go build -o geodat2srs && cd ..
mkdir -p rules
./geodat2srs/geodat2srs geosite -i geosite.dat -o rules --prefix "geosite-"
# результат: rules/geosite-playstation.srs
````

### Примечания

* В репозитории хранится **сгенерированный артефакт** для удобства.
* Лицензии и состав доменных списков регулируются upstream-проектами; см. репозитории Runetfreedom и их источники geodata.

---

## EN

### What is this

`geosite-playstation.srs` is a **sing-box `.srs`** binary rule-set containing PlayStation/PSN-related domains. Intended for **Podkop on OpenWrt** (Podkop uses sing-box internally).

This file is generated from **Runetfreedom** `geosite.dat`.

### How to use in Podkop (OpenWrt)

1. LuCI → **Podkop → Sections**
2. Create a section (e.g. `PSN`) or select an existing one
3. Find **Remote Domains Lists**
4. Paste this URL:

[https://raw.githubusercontent.com/CaliostRa/geosite-playstation.srs/main/geosite-playstation.srs](https://raw.githubusercontent.com/CaliostRa/geosite-playstation.srs/main/geosite-playstation.srs)

5. Place the `PSN` section **above** broader catch-all sections (e.g. “proxy all” / “direct all”) so it matches first.

### How it was generated

* Geodata source: `runetfreedom/russia-v2ray-rules-dat` (`geosite.dat`)
* Converter: `runetfreedom/geodat2srs`

Build example (WSL/Ubuntu):

```bash
curl -L -o geosite.dat https://raw.githubusercontent.com/runetfreedom/russia-v2ray-rules-dat/release/geosite.dat
git clone https://github.com/runetfreedom/geodat2srs.git
cd geodat2srs && go build -o geodat2srs && cd ..
mkdir -p rules
./geodat2srs/geodat2srs geosite -i geosite.dat -o rules --prefix "geosite-"
# output: rules/geosite-playstation.srs
```

### Notes

* This repository contains a **generated artifact** for convenience.
* Domain lists and licensing are governed by upstream projects; refer to the upstream repositories and their geodata sources.

```
::contentReference[oaicite:0]{index=0}
```
