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

## May7

Did a Refactoring by having separate methods for each loadfile,configure browser,launch browser,used static waits as LockSupport.parknanos then called those methods in a separate mathod.
Then configured testng.xml file with suite name,test name,class name.
so far used @beforesuite (loadconfig() from properties), @beforemethod and @aftermethod.

Then created 2 dummyclass and ran it in testng it got failed because baseclass has prop as protected.Debugged it the prop was showing null. so declared that static so this prop got shared.
```protected static Properties prop;```

## May12

Got to know about ```ActionDriver class``` setup and created reusable methods in it 

Overview: Designed to handle common browser interactions. We write action related methods in a single class.
click(),enterValue() like that. These are encapsulated when we call in other classes because we don't know the implementation details.
We can reuse all this in page classes as part of POM. Used By by locators for performance pov as it will locate the elements in runtime not like webelement which stores the element and locate it later on.

What i did? getter and setter method in Baseclass.for get and set the webdriver.
Then declared variables in ```ActionDriver class``` driver and wait.Initialized it by creating a constructor.

Added all action methods with try catch block surrounding it.

## May13

Implemented POM- Loginpage and Homepage class
created By class and have the locators in the private variable.
Then what and all i want to add in Login like sendkeys,clicking submit for those i called the actionmethods which i mentioned in actiondriver.
Both in login page and homepage we need to initialize actionDriver.
Each web page (or component) is represented by a Java class.

## May14

Created loginpageTest and homepageTest and ran those and got the flow from ```testclass > pageclass > actiondrive > baseclass```

## May15

SingletonSet - using this we had reduced number of actiondriver instance getting created.Previously it was created twice.Now to 1.
We had got to know this by debugging it.
Singleton mainly refers only one instance of class is getting instantiated and used globally.
```if (driver == null)```
```if(actionDriver == null)```
## May 16
Logging is a way to record information about application execution.Its an Industry standard logging library for java.Log4j2 is the latest.Had added the log4j2 package and its api package from maven in the pom.xml
Helps in debugging,monitoring and trouble shooting.
Then in baseclass added this as static final ```public static final Logger logger = LoggerManager.getLogger(BaseClass.class);```
and this in Action driver ```public static final Logger logger=BaseClass.logger;```
