# python-tutorial-book

## What is Python ??
* プログラム言語
* 1991年にオランダ人によって開発されたインタプリタ型言語
* シンプル、書きやすい、読みやすい

## 食欲をそそってみようか
* シンプルだが豊富な標準モジュール
* C言語での拡張が可能

## Pythonインタープリタの使い方

* インタプリタの起動
python
```
Python 3.8.5 (default, Sep  4 2020, 02:22:02) 
[Clang 10.0.0 ] :: Anaconda, Inc. on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 
>>> x = 10
>>> y = 11
>>> if x == y:
...     print(True)
... else:
...     print(False)
... 
False
```

* インタプリタの終了
```
Ctrl + D
or
quit()
```

* ソースコードエンコーディング
```
# -*- coding: encoding -*-
```

## 気楽な入門編

* / と //
```
>>> 17 / 3  # 常にfloatを返す
5.666666666666667
>>> 17 // 3  # 切り下げ除算
5
>>> 
```

* raw文字列(特殊文字の)無視
```
>>> print('C:\some\name')
C:\some
ame
>>> print(r'C:\some\name')
C:\some\name
>>> 
```

* 文字列の繰り返し
```
>>> print(3 * 'kb')
kbkbkb
>>> 
```

* スライス(スライスの数字は文字と文字の間を表している)
```
>>> s = 'keisukebanchi'
>>> print(s[0])
k
>>> print(s[-1])
i
>>> print(s[1:3])
ei
>>> print(s[:3])
kei
>>> print(s[3:])
sukebanchi
>>> 
>>> print(s[100])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
>>> print(s[:100])
keisukebanchi
>>> s[0] = 'k'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>> 
```

## 制御構造ツール

* if
```
if a == b:
    XXX
elif c == d:
    XXX
else:
    XXX
```

* range
```
>>> for i in range(10):
...     print(i)
... 
0
1
2
3
4
5
6
7
8
9
>>> 
>>> l = list(range(10))
>>> l
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> 
>>> l = [i for i in range(5)]
>>> l
[0, 1, 2, 3, 4]
>>> 
>>> l = [i for i in range(1, 10, 3)]  # 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
>>> l
[1, 4, 7]
>>> 
```

* 特殊引数
```
def func(pos1, pos2, /, pos_or_kwd, *, kwd1, kwd2):
```

* lambda
```
f = lambda x: x * 2
```

* docstring
```
def func():
    """Do nothing, but document it.
    
    No, really, it doesn't do anything.
    """
```

## データ構造

* モジュール
```
import module
from module import func
import module as name
```

```
if __name__ == '__main__':
    main()
```

## モジュール

* コンパイル済ファイル
```
__pycache__/
```

* dir
```
dir(module)
```

* __init__.pyと__all__
```
__init__.py -> パッケージファイル
__all__ -> import * でインポートしたいもののリスト
```

## 入出力

* format
```
print(f'XXX {YYY}')
print('XXX {}'.format(YYY))
```

* open
```
f = open('sample.txt', 'r')
f.read()
f.read(size)
f.readline()
f.close()
```

* with open
```
with open('sample.txt', 'r') as f:
    f.read()
```

* json
```
import json
json.dumps([1,2,3])
```

## エラーと例外

* try
```
try:
    XXX
except Exception as e:
    XXX
else:
    XXX
finally:
    XXXX
```

## クラス

* scope
```
local
nonlocal
global
```

* class
```
class Person():

    kind = 'Japann'

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def introduction(self):
        print(self.name, self.age)
```

* extend
```
class Child(Person):
```

* アンダースコア
```
class Person():

    def __init__(self, name, age):
        self.name = name
        self._name = name
        self.__name = name
```

## 標準ライブラリめぐり

* standard modules
```
import os
import shutil
import glob
import sys
import re
import math
import random
import statistics
from urllib.request import urlopen
import smtplib
from datetime import date
import zlib, gzip, bz2, lzma, zipfile, tarfile
from timeit import Timer
import doctest
import unittest
import json
import sqlite3
```

## 標準ライブラリめぐり - PartⅡ

* standard modules
```
import pprint
import textwrap
import locale
import struct
import threading
import logging
from array import array
from collections import deque
from decimal import *
```

## 仮想環境とパッケージ

* venv
```
python -m venv sample-env
source sample-env/bin/activate
```

* pip
```
python -m pip install package
python -m pip install package==2.0
python -m pip install --upgrade package
python -m pip install -r requirements.txt
python -m pip search package
python -m pip uninstall package
python -m pip freeze > requirements.txt
python -m pip show package
python -m pip list
```

## 次はなに？

* Python Standard Library
* PyPI
* Python Cookbook

## 対話環境での入力行編集とヒストリ置換

* bpython
* IPython

## 浮動小数点(float)の演算:その問題と限界

* float
コンピュータが2進数で動くため、10進数小数点を正確に表現できない問題
```
>>> 0.1+0.1+0.1 == 0.3
False
>>> 
```

## 補足

* help
```
help(module)
```