<div align="center">

<img src="./image/banner.png" alt="rime-shushu-dict banner" width="100%" />

# rime-shushu-dict

**A Chinese dictionary for the [RIME Input Method](https://rime.im/) covering Chinese metaphysics & Western mysticism**

Including I-Ching, BaZi, Ziwei, Qimen, Feng Shui, Taoism, Western Astrology, Tarot, Alchemy, Kabbalah and more.

[简体中文](./README.md) · [English](./README.en.md)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![RIME](https://img.shields.io/badge/RIME-Input%20Method-1f6feb.svg)](https://rime.im/)
[![Entries](https://img.shields.io/badge/entries-960%2B-blue.svg)](./shushu_mysticism.dict.yaml)
[![Categories](https://img.shields.io/badge/categories-16-9cf.svg)](#contents)
[![Stars](https://img.shields.io/github/stars/misakaikato/rime-shushu-dict?style=social)](https://github.com/misakaikato/rime-shushu-dict/stargazers)
[![Issues](https://img.shields.io/github/issues/misakaikato/rime-shushu-dict.svg)](https://github.com/misakaikato/rime-shushu-dict/issues)
[![Last Commit](https://img.shields.io/github/last-commit/misakaikato/rime-shushu-dict.svg)](https://github.com/misakaikato/rime-shushu-dict/commits/main)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)

</div>

---

## Features

- **Comprehensive coverage**: 960+ entries across 16 categories, spanning both Eastern and Western mystical systems.
- **Easy integration**: Standard Rime dictionary format (`*.dict.yaml`); use it standalone or merge into your existing dictionary.
- **Schema-agnostic**: Encoded in Hanyu Pinyin, compatible with most pinyin-based schemas including [rime-ice](https://github.com/iDvel/rime-ice), [Flypy](https://github.com/rime/rime-double-pinyin), [Mingyue Pinyin](https://github.com/rime/rime-pinyin-simp), etc.
- **Variant readings & fault tolerance**: Alternative encodings provided for polyphonic characters (e.g. 卜筮 `bu shi` / `bo shi`), rare characters (巽, 艮, 噬嗑, 贲, 睽, 蹇, 夬, 姤), and translated terms (阿卡纳 / 阿尔克那, 卡巴拉 / 喀巴拉) to minimize candidate misses.

## Contents

| Category | Sample Entries |
|----------|----------------|
| General | 术数, 玄学, 命理, 阴阳五行, 河图, 洛书, 太极, 四象 |
| I-Ching & Bagua | 周易, 十翼, 卦象, 爻辞, 先后天八卦, names of the 64 hexagrams |
| Heavenly Stems & Earthly Branches | 十天干, 十二地支, 六十甲子, 刑冲合害破 |
| Nayin (Sound Elements) | 海中金, 炉中火, 大林木, and the full 60-Nayin set |
| BaZi (Four Pillars) | 四柱, 十神, 大运, 流年, 用神, 格局, 神煞 |
| Shensha (Auspicious / Inauspicious Stars) | 天乙贵人, 文昌, 桃花, 华盖, 驿马, 空亡 |
| Liuyao, Meihua & Divination | 京房易, 纳甲, 世应, 用神, 梅花易数, divination terminology |
| Qimen Dunjia | 三奇六仪, 九星八门, 值符值使, 阳遁阴遁 |
| Ziwei Doushu | 14 main stars, 12 palaces, 四化, 三方四正 |
| Feng Shui | 形峦理气, 三元九运, 玄空飞星, 二十四山, 罗盘 |
| Date Selection & Almanac | 黄道吉日, 建除十二神, 二十八宿值日, 宜忌 |
| Stars, Taoism & Folk Deities | 二十八宿, 三清四御, 八仙, 文昌帝君, 土地公 |
| Western Astrology | 12 zodiac signs, 10 planets, 12 houses, aspects, natal chart terms |
| Tarot | Major Arcana, Minor Arcana, four elements, court cards, Rider-Waite |
| Western Mysticism, Alchemy & Kabbalah | Tree of Life, 10 Sephirot, four worlds, philosopher's stone, Rosicrucian |
| Variant Readings & Tolerance | 卜筮, 噬嗑, 觜宿, 阿卡纳, 卡巴拉, etc. |

## Installation

### Option 1: As a standalone dictionary

1. Place `shushu_mysticism.dict.yaml` into your Rime user directory:

	- macOS: `~/Library/Rime/`
	- Windows: `%APPDATA%\Rime\`
	- Linux: `~/.config/ibus/rime/` or `~/.config/fcitx/rime/`

2. Mount the dictionary in your custom schema file (e.g. `rime_ice.custom.yaml` or `luna_pinyin.custom.yaml`):

	```yaml
	patch:
	  "translator/dictionary": rime_ice
	  "translator/prism": rime_ice
	  "schema/dependencies":
	    - shushu_mysticism
	```

	Or simply append it to the `import_tables` of your main dictionary (e.g. `rime_ice.dict.yaml`):

	```yaml
	import_tables:
	  - shushu_mysticism
	```

3. Redeploy (use the "Redeploy" menu item or run `rime_deployer --build`).

### Option 2: Merge into an existing dictionary

Copy the entries below the `---` / `...` markers in `shushu_mysticism.dict.yaml` directly into the corresponding section of your custom dictionary, then redeploy.

## Weight Reference

The third column (weight) reflects approximate usage frequency and specialization, ranging from 7000 to 10000:

- `10000` tier: core high-frequency terms (e.g. 术数, 五行, 八卦, 易经)
- `9000` tier: commonly used technical terms
- `8000` tier: advanced or domain-specific vocabulary
- `7000` tier: rare or school-specific jargon

Feel free to adjust weights based on your own usage habits.

## Contributing

🎉 **Contributions of any kind are welcome!** Whether you're a metaphysics enthusiast, a Rime user, or a passing developer — you're invited to help improve this dictionary:

### What you can do

- 🔤 **Add entries**: missing terms, school-specific vocabulary, regional variants
- 🐛 **Fix errors**: pinyin, character forms, weights, category misplacement
- 🔁 **Add tolerance**: polyphones, traditional/simplified pairs, common misreadings, translated names
- 📚 **Improve docs**: usage instructions, install steps, schema integration tips
- 🌐 **Translate**: English README and other language versions

### Workflow

1. Fork this repo → create your branch: `git checkout -b feat/add-xxx`
2. Append entries in the existing format (mind the category section):
	```
	word<TAB>pinyin (lowercase, space-separated)<TAB>weight (integer)
	```
3. Commit: `git commit -m "feat: add xxx entries"`
4. Push: `git push origin feat/add-xxx`
5. Open a [Pull Request](https://github.com/misakaikato/rime-shushu-dict/pulls)

### Guidelines

- Keep entries **professional and accurate** — avoid internet slang or invented terms
- Pinyin should follow the *Modern Chinese Dictionary* / *Mandarin Pronunciation Standard*; place variant readings in the "Variant Readings & Tolerance" category
- Weights only need to be **reasonable within the tier**; precise comparison isn't required
- For large-scale changes, please **open an Issue first** to discuss

You can also report issues, share feedback, or propose ideas via [Issues](https://github.com/misakaikato/rime-shushu-dict/issues) ✨

## Acknowledgements

- [Rime Input Method Engine](https://github.com/rime/librime)
- [rime-ice](https://github.com/iDvel/rime-ice) and other excellent open-source schemas

## License

Released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please retain attribution when using or redistributing.

---

<div align="center">

If this dictionary helps you, consider giving it a ⭐ Star — it's the best encouragement for the author!

</div>
