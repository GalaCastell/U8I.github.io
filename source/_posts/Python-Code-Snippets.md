---
title: Python Code Snippets
date: 2020-10-21 11:00:05
tags:
---


# common usages

### init and store
--------

- authentication: session/token etc  
- request session
- global variables


### retry
--------
(mechanism)  

- request timeout  
- push notification  
- execution failure  


### fetch pages
---------

- iter with page  


### data converting  
---------  

```python

class Converter(object):

    direct_mapper = {
        ''
    }


    @classmethod
    def __call__(cls, data):
        return {

        }

```

####  time transforming  

> code snippets    


```python 

from datetime import datetime, timedelta
from pytz import timezone


class DTU(object):
    """Datetime Utilities"""

    @classmethod
    def from_str(cls, string, tformat="%Y-%m-%d %H:%M:%S"):
        return datetime.strptime(string, tformat)

    @classmethod
    def from_ts(cls, timestamp):
        return datetime.fromtimestamp(timestamp)

    @classmethod
    def as_tz(cls, dt, timezone=timezone('utc'), with_tz=False):
        """As Timezone"""
        pass

    @classmethod
    def to_ts(cls, dt):
        """To timestamp"""
        pass

    @classmethod
    def to_str(cls, tformat=None):
        """To string"""
        pass




```


### decorators  
----------

```python


from functools import wraps

# decorator without parameters
def decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return result
    return wrapper



# decorator with parameters
def decorator(*dec_args, **dec_kwargs):
    
    def decorate(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            result = func(*args, **kwargs)
            return result
        return wrapper

    return decorate


```


### compute signature  

```python  

def concate_data(data):
    pairs = [f"{k}={v}" for k, v in sorted(data.items()) if v]
    return '&'.join(pairs).encode('utf-8')


```







