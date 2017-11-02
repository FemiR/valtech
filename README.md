# valtech
QA Automation Challenge
# Using C#

using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using System;

namespace ConsoleApplication1
{
    class Program
    {
        private static object assert;
        private static Action contactUsArea;
        private static IWebElement newsSection;
        private static Action servicesPageLink;
        private static Action workPageLink;

        static void Main(string[] args)
        {
            IWebDriver driver = new ChromeDriver();

            driver.Navigate().GoToUrl("http://www.valtech.com");

            newsSection = driver.FindElement(By.XPath("//div[2]/div[3]/div[1]/header/h2"));
            Get.text("LATEST NEWS");

            newsSection = driver.FindElement(By.XPath("//div/ul/li[1]/a/span"));


            servicesPageLink = driver.FindElement(By.XPath("//div/ul/li[3]/a/span")).Click;


            workPageLink = driver.FindElement(By.XPath("//div/ul/li[2]/a/span")).Click;


            contactUsArea = driver.FindElement(By.XPath("//div/div[2]/p[2]")).Click;
