# Dailystudy
## May2 
> Setup for eclipse and installed it with the install software itself

## May3  
![image](https://github.com/user-attachments/assets/8e8d2daa-8971-4176-94e9-901fbaf08e8c)

Done All the setup for orange HRM

## May5

Understood very much about config.properties file and created a baseclass.

config.properties

Why needed: All critical settings in one place for easy maintenance, avoid hardcoding values,Easy mainatianance,reusability,update settings without modifying the code
Flexibility we can switch between environments
- Configuration file stores key-value pairs
Examples of properties stored:
- Browser type,URL,Waits

Baseclass

backbone of framework.contains common setup and teardown logic shared across all testcases.

Setup contains initialize webdriver,browser,wait statements,maximize browser,launching url in browser

Teardown contains browser close,quit.

Why needed: Avoid duplicate setup/teardown code in each test class.Makes framework easier to maintain and scale.

Acts as a base for all Testclasses.

What I did?

Created a ```config.properties``` file and added details like url,waits units,browser name.
Then in ```Baseclass.java``` file setup and teardown are added.
Then in ```dummyclass.java``` just tested with an assert statement for title.
