# Decorator 裝飾器用法
[教學網址](<https://www.maxlist.xyz/2020/12/07/python-decorator/>)

## 裝飾器基本用法
``` python

import time
from functools import wraps


def timer(sec:int=1):
    '''
    計算函式執行時間
    sec  : 等待時間, 裝飾器的參數
    func : 被裝飾的函式
    args : 被裝飾函式的參數
    ---
    from functools import wraps
    @wraps(func) # 取得原函式的的名稱 而不是warp

    '''
    def decorator(func):
        @wraps(func) # 取得原函式的的名稱 而不是warp
        def wrap(*args):
            t_start = time.time()
            time.sleep(sec)
            res = func(args)
            t_end = time.time()
            t_count = t_end - t_start
            print('[花費時間]', t_count)
            return res
        return wrap
    return decorator
@timer()
def foo(*args):
    return sum(*args)

r = foo(1,2,3,4,5)
print(r)
```

## 使用Class 寫裝飾器

> Class decorator
```python
import time
from functools import wraps
 
class Timer:
    def __init__(self, time_sleep):
        print('[__init__]')
        print('[time_sleep]:', time_sleep)
 
        self.time_sleep = time_sleep
 
    def __call__(self, func):
        @wraps(func)
        def wrap(*args, **kargs):
            t_start = time.time()
            time.sleep(self.time_sleep)
            value = func(*args, **kargs)
            t_end = time.time()
            t_count = t_end - t_start
            print('[共花費時間]', t_count)
            return value
 
        return wrap
 
 
@Timer(time_sleep=3)
def dosomethingClass(a, b):
    print('do some thing')
    print('a + b = ', a + b)

```
## @property 用法
[@property 用法](<https://www.maxlist.xyz/2019/12/25/python-property/>)

