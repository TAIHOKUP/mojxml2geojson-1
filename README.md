# mojxml2geojson

## Requirement

- GDAL
  - https://gdal.org/download.html
- python 3.*
- pip 22.*

## Installing

### setup.py

```bash
pip install -e .
```

### From Github

```bash
pip install git+https://github.com/koswatana/mojxml2geojson.git
```

## Usege

### Single File

```bash
mojxml2geojson ./moj.xml
```

### Multiple files

```bash
cd [target directory]
ls -1 *.xml|xargs -I{} mojxml2geojson ./{}
```

**Parallel Processing**

```bash
ls -1 *.xml|xargs -P100 -I{} mojxml2geojson ./{}
```

### PyTest

```bash
python -m pytest -vv -p no:cacheprovide
```

### memo

- 任意座標の場合、ファイル名を標準出力して正常終了

```
./13101.xml : 任意座標系
```

- エラーが発生した場合、ファイル名とエラー内容が標準出力される

```
Error Source File: ./33208-2619-143.xml
Traceback (most recent call last):
  ...
AttributeError: 'str' object has no attribute 'keys'
```