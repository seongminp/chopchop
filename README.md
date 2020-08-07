# chopchop
🌳 Log 뿌시기. Make Logs Digestible

... And, while we're at it, thread safe!

(Coming Soon<sup>TM</sup>)

## Installation

```shell
pip install chopchop
```

*Optional but recommended:*

1. Choose a log collection directory.

2. Set `CHOPCHOP` environment variable to that directory.

## Usage

```
from chopchop import log_this

@log_this(at='/absolute_path_to_log_dir', for=1)
def some_function():
    pass  
```

Or, if you've set the environment variable `CHOPCHOP`, simply write:
```
from chopchop import log_this

@log_this(for=1)
def some_function():
    pass  
```
## Thread safety
By default, `chopchop` creates a different log file for each job.


