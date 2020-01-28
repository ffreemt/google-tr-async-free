# google-tr-async-free ![Python3637 package](https://github.com/ffreemt/google-tr-async-free/workflows/Python%203637%20package/badge.svg)[![PyPI version](https://badge.fury.io/py/google-tr-async-free.svg)](https://badge.fury.io/py/google-tr-async-free)

Google translate for free -- based on httpx with proxy support. Let's hope it lasts.

### Installation

```pip install google-tr-async-free```

or

* Install (pip or whatever) necessary requirements, e.g. ```
pip install httpx js2py loguru``` or ```
pip install -r requirements.txt```
* Drop the file google_tr.py in any folder in your PYTHONPATH (check with import sys; print(sys.path)
* or clone the repo (e.g., ```git clone https://github.com/ffreemt/google-tr-async-free.git``` or download https://github.com/ffreemt/google-tr-async-free/archive/master.zip and unzip) and change to the google-tr-free folder and do a ```
python setup.py develop```

### Usage

```
import asyncio
loop = asyncio.new_event_loop()
asyncio.set_event_loop(loop)
arun = lambda x: loop.run_until_complete(x)

from google_tr_async import google_tr_async

_ = [google_tr_async('hello world'),
  google_tr_async('hello world', to_lang='de'),
  google_tr_async('hello world', to_lang='fr'),
  google_tr_async('hello world', to_lang='ja')]
res = arun(asyncio.gather(*_))

print(res[0])  # ->'你好，世界'
print(res[1])  # ->'Hallo Welt'
print(res[2])  # ->'Bonjour le monde'
print(res[3])  # ->'こんにちは世界'
```

### Acknowledgments

* Thanks to everyone whose code was used
