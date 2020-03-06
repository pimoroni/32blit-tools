# 32blit Tools

[![Build Status](https://travis-ci.com/pimoroni/32blit-tools.svg?branch=master)](https://travis-ci.com/pimoroni/32blit-tools)
[![Coverage Status](https://coveralls.io/repos/github/pimoroni/32blit-tools/badge.svg?branch=master)](https://coveralls.io/github/pimoroni/32blit-tools?branch=master)
[![PyPi Package](https://img.shields.io/pypi/v/32blit.svg)](https://pypi.python.org/pypi/32blit)
[![Python Versions](https://img.shields.io/pypi/pyversions/32blit.svg)](https://pypi.python.org/pypi/32blit)

This tool is intended for use with the 32Blit console to prepare assets and upload games.

# WORK IN PROGRESS

You should install from source using:

```
git clone https://github.com/pimoroni/32blit-tools
cd src/
python3 setup.py develop
```

# Running

```
32blit --help
```

## Packing Image Assets

All image assets are handled by Pillow so most image formats will work, be careful with lossy formats since they may add unwanted colours to your palette and leave you with oversized assets.

By default images will be packed into bits depending on the palette size. A 16-colour palette would use 4-bits-per-pixel. Use `--raw` to output raw pixel data, suitable for loading directly into a `blit::Surface`.

Supported formats:

* 8bit PNG .png
* 24bit PNG .png

Options:

* `palette` - Image or palette file (Adobe .act, Pro Motion NG .pal, GIMP .gpl) containing the asset colour palette
* `transparent` - Transparent colour (if palette isn't an RGBA image), should be either hex (FFFFFF) or R,G,B (255,255,255)
* `raw` - Output raw pixel data, suitable for loading into a `blit::Surface`
* `raw_format` - Format for raw data, either RGB or RGBA
* `strict` - Only allow colours that are present in the palette image/file

## Packing Map Assets

Supported formats:

* Tiled .tmx - https://www.mapeditor.org/ (extremely alpha!)

## Packing Raw Assets

Supported formats:

* CSV .csv
* Binary .bin, .raw