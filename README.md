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

job_id = 'some_job_id' # Can also be an integer.

@log_this(at='/absolute_path_to_log_dir', for=job_id)
def some_function():
    pass  
```

Or, if you've set the environment variable `CHOPCHOP`, simply write:
```python
from chopchop import log_this

job_id = 'some_job_id'

@log_this(for=some_job_id)
def some_function():
    pass  
```
## Thread safety
By default, `chopchop` creates a different log file for each job.


