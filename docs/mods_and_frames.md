# Modules And Frameworks

## Logging
Logging module is a standard library used by both the beginners and enterprise level coders.
To import the module:
``` py 
import logging
```
There are 5 standard levels indicating the severity of events.
* DEBUG
``` py 
logging.debug("This is a debug message")
```
* INFO
``` py 
logging.info("This is a info message")
```
* WARNING
``` py
logging.warning("This is a warning message") 
```
* ERROR
``` py 
logging.error("This is a error message")
```
* CRITICAL
``` py 
logging.critical("This is a critical message")
```
### **BASIC CONFIGURATION**
Basic configuration is a method that is used to configure the logging. The parameters are :
* *level*    ~ The **root** logger set the severity level
* *filename* ~ Name of the file
* *filemode* ~ The file is opened with the specified mode , default is *append* mode
* *format*   ~ Format of the log message
### Examples

1. To log date and time info :
``` py linenums = "1"
# logging configuration
logging.basicConfig(level = logging.INFO , format = '%(asctime)s - %(message)s')
# logging
logging.info("User logged in")
```
Output :
```2023-08-14 14:41:11,200 - User logged in```

2. To change the format of the date we use `datefmt` attribute :
``` py linenums = "1"
logging.basicConfig(level = logging.INFO,format = '%(asctime)s - %(message)s', datefmt = "%d-%b-%y %H:%M:%S")
logging.info("User logged out")
```
Output :
```14-Aug-23 14:42:24 - User logged out```