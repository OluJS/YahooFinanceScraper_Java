# Yahoo Finance Scraper (for Java)

Before investing in a company, it's always good to take a look at the fundamentals and ensure that the company is not in trouble.
This can easily become a tedious task especially when reviewing multiple establishments. 
This program helps to gather the fundamentals of companies by scraping the necessary web elements and printing them in the console.

![Java CI with Maven](https://github.com/0lu99/YahooFinanceScraper_Java/workflows/Java%20CI%20with%20Maven/badge.svg?branch=master)


## Table of Contents
- [Getting Started](#Getting-Started)
    * [Prerequisites](#Prerequisites)
    * [Cloning](#Cloning)
- [Built with](#Built-with)
- [How to use](#How-to-use)
- [Classes](#Classes)
   * [Page Object Model](#Page-Object-Model)
   * [Step definitions](#Step-definitions)
   * [Test runner](#Test-runner)


## Getting Started
These instructions will get you a copy of this project up and running on your local machine for development and testing purposes

### Prerequisites
- Java SE
- Java SDK
- Eclipse

### Cloning
Option 1: Through terminal / cmd
```
git clone https://github.com/0lu99/YahooFinanceScraper_Java.git
```

Option 2: Through Eclipse IDE

![eclipseGitHubImportImage](https://eclipsesource.com/wp-content/uploads/2012/12/12.png)

## Built with
- [Maven](https://maven.apache.org/) - Build automation tool
- [Cucumber](https://cucumber.io/docs/cucumber/) - To help assist BDD through its language parser, Gherkin
- [Selenium](https://www.selenium.dev/) - Collection of tools to automate web browser actions

## Classes
### Page Object Model
Page object model is a common design pattern when writing automation scripts that's used to create an object repository for elements on a web page. It is used to store these web elements as variables as well as creating methods that will peform actions using those elements. The main advantages of using this pattern is that is helps to reduce duplication and increaes reusability by making use of the same web element in different classes and it also helps test maintainance. If each web page throughout the test journey has their own page object model, it'll be easier to keep track of where everything is.

For this project I make use of 2 POM classes, one for the page where the user will search for the stock and the second for the page the user will get the stock info from.

To support Page Object Model Page Facotry, an extension to Page Object is used to help initialise the web element variables like so:
```java
@FindBy (xpath = "//li[7]//a[1]//span[1]")
@CacheLookup
WebElement financialsTab;
```
> The POM classes can be found at _YahooFinanceScraper_Java/src/test/java/pageObjects/_



## How to use
This project makes use of Scenario Outline - a Gherkin reference - which will iterate through the same process until it has taken each row in the Examples section beneath it into account.
In order to search for the individual stocks of your choice, all you need to do is edit/add stocks to the examples table within the feature file:

![featureFileGif](http://g.recordit.co/e8IdTXAeho.gif)

The console we then return a specified list of fundamentals for Coca-Cola (KO), Pepsi (PEP), Nikola (NKLA) and Paypal (PYPL):

![consoleOutputGif](http://g.recordit.co/R5EYQS8tZp.gif)
