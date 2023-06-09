# This chapter is about to learn logging

## Reason:
- In commercial software product it is crucial
- Bug detecting and tracing back (instead of print)
- Helps to detect incorrect behavior (hacking for example)
- Diagnosing code


## Basic essentials:

```Python
import logging

def main() -> None:
  logging.basicConfig(level=logging.#level#)

  logging.debug()
  logging.info()
  logging.warning()
  logging.error()
  logging.critical()
```
<a id="python-logging-levels"></a>
This are the 5 levels of messaging.
- Debug: Detailed information, typically of interest only when diagnosing problems.
- Info: Confirmation that things are working as expected.
- Warning: An indication that something unexpected happened.
- Error: Due to a more serious problem, the software has not been able to perform some function.
- Critical: A serious error, indicating that the program itself may be unable to continue running.

<br/>
By choosing the level in the ***level=logging.#level#*** we get all the messages from that level and below.
<br/>

BasicConfig has other arguments as well like:
- format: The format of the message. ("%(asctime)s:%(levelname)s:%(message)s")
- datefmt: The format of the date. ("%Y-%m-%d %H:%M:%S")
- filename: The name of the file where the logs will be saved. (It adds to the existing log file.)


```Python
import logging

def main() -> None:
  logging.basicConfig(
    level=logging.#level#,
    format="%(asctime)s:%(levelname)s:%(message)s",
    datefmt="%Y-%m-%d %H:%M:%S",
    filename="logs.log"
  )

  ...
```

For more complex applications we want more control how logging happens. <br/>
Using logging surface: easier way to visualize and search the logs. <br/>
For overall understanding and for other team members. <br/>

```__name__``` : It can has different name for different part of the application. <br/>
(e.g. frontend, backend) <br/>

```handler``` : We can have multiple handlers. <br/>
(e.g. console, file, email, database) <br/>

One of the logging services are ***StreamHandler***, ***SysLogHandler***. <br/>
Code example:

```Python
import logging
from logging import SysLogHandler

PAPERTRAIL_HOST = "logs.papertrailapp.com"
PAPERTRAIL_PORT = *****


def main() -> None:
  logger = logging.getLogger(__name__)
  logger.setLevel(level=logging.#level#)

  handler = SysLogHandler(address=(PAPERTRAIL_HOST, PAPERTRAIL_PORT))
  logger.addHandler(handler)

  logger.critical("Hello from Ponti!")
```

Make sure to have a grasp on where the logs are stored and how is it stored. <br/>
The law of log data how long can it saved and should be deleted. <br/>


## Resources:
- [Python Logging: How to Write Logs Like a Pro!](https://www.youtube.com/watch?v=pxuXaaT1u3k)




# Projects where I used this:
- [Computer image processing assignment](https://github.com/Ponti1999/Computer_image_processing/tree/main/Semester_Assignment)
-
