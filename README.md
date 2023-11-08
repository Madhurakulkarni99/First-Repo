package Webdriver;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class CAWAssignment {

	public static void main(String[] args) {
		// Open the browser
		System.setProperty("WebDriver.chrome.driver","C://Users//sdemj//Downloads//chromedriver-win64.zip//chromedriver.exe");
	    WebDriver driver=new ChromeDriver();
	    driver.get("https://testpages.herokuapp.com/styled/tag/dynamic-table.html");
	    driver.findElement(By.xpath("//div[@id=\"tablehere\"]/following-sibling::details/summary")).click();
	    Object Array=new Object();
	    Array=[{"name" : "Bob", "age" : 20, "gender": "male"}, {"name": "George", "age" : 42, "gender": "male"}, {"name":
	    		"Sara", "age" : 42, "gender": "female"}, {"name": "Conor", "age" : 40, "gender": "male"}, {"name":
	    		"Jennifer", "age" : 42, "gender": "female"}];
	    
	    
	    driver.findElement(By.xpath("//textarea[@id=\"jsondata\"]")).sendKeys("Array");
	    

	    
	    
	    driver.findElement(By.xpath("//button[@id=\"refreshtable\"]")).click();	}
