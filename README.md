# chopchop
🌳 Log 뿌시기. Make Logs Digestible (... and, while we're at it, thread safe!)

(Coming Soon<sup>TM</sup>)

## Installation

```shell
pip install chopchop
```

*Optional but recommended:*

1. Choose a log collection directory.

2. Set `CHOPCHOP` environment variable to that directory.

## Usage

```python
from chopchop import log_this

@log_this()
def some_function():
    pass  
```

Or send your log as a Telegram message.

```python
from chopchop import log_this
from chopchop.destinations import Telegram

telegram = Telegram(chat_id='<YOUR_BOT_CHAT_ID>`, token='<YOUR_BOT_TOKEN>')

@log_this(at=telegram)
def some_function():
    pass  
```

If you want to, you can also specify your log output as an absolute path.
We do recommend keeping a manageable log directory by setting the `CHOPCHOP` environment variable.
If neither the `CHOPCHOP` environment variable nor a log destination is specified, log files will be crated at the current working directory.

```python
from chopchop import log_this

@log_this(at='/absolute_path_to_log_dir')
def some_function():
    pass  
```

## Job Control

Sometimes, you want to group your logs. 

```python
from chopchop import log_this

job_id = 'some_job_id' # Can also be an integer.

@log_this(for=job_id)
def some_function():
    pass
```
Logs with the same `job_id` will be logged under the same (possibly newly_created) folder. 
To omit the folder generation step, pass `flat=True` to `log_this`.

## Thread safety
By default, `chopchop` creates a different log file for each job.


