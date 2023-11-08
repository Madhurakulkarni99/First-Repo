package Webdriver;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import com.google.gson.Gson;


import io.opentelemetry.sdk.metrics.data.Data;

public class CAWAssignment {

	public static void main(String[] args) {
		// Open the browser
		System.setProperty("WebDriver.chrome.driver","C://Users//sdemj//Downloads//chromedriver-win64.zip//chromedriver.exe");
	    WebDriver driver=new ChromeDriver();
	    driver.get("https://testpages.herokuapp.com/styled/tag/dynamic-table.html");
	    driver.findElement(By.xpath("//div[@id=\"tablehere\"]/following-sibling::details/summary")).click();
	    
        // Find the input text box element by its ID (or any other appropriate selector).
        WebElement textBox = driver.findElement(By.xpath("//textarea[@id=\"jsondata\"]"));

        // Insert the JSON data into the input text box.
        String jsonData = "[{\"name\": \"Bob\", \"age\": 20, \"gender\": \"male\"}, {\"name\": \"George\", \"age\": 42, \"gender\": \"male\"}, {\"name\": \"Sara\", \"age\": 42, \"gender\": \"female\"}, {\"name\": \"Conor\", \"age\": 40, \"gender\": \"male\"}, {\"name\": \"Jennifer\", \"age\": 42, \"gender\": \"female\"}]";
        textBox.sendKeys(jsonData);

        
	    driver.findElement(By.xpath("//textarea[@id=\"jsondata\"]")).sendKeys("data");
	    
        driver.findElement(By.xpath("//button[@id=\"refreshtable\"]")).click();	
	    
	
	  WebElement table = driver.findElement(By.id("dynamictable"));

    // Extract the data from the UI table.
        tableData = table.getText();

    // Define the expected data in the JSON format.
       jsonData = "[{\"name\": \"Bob\", \"age\": 20, \"gender\": \"male\"}, {\"name\": \"George\", \"age\": 42, \"gender\": \"male\"}, {\"name\": \"Sara\", \"age\": 42, \"gender\": \"female\"}, {\"name\": \"Conor\", \"age\": 40, \"gender\": \"male\"}, {\"name\": \"Jennifer\", \"age\": 42, \"gender\": \"female\"}]";

    // Compare the data from the UI table with the expected data.
       if (tableData.equals(jsonData)) {
    	   
       System.out.println("Data in the UI table matches the expected data.");
    } 
       else
       {
        System.out.println("Data in the UI table does not match the expected data.");
    }

    // Close the WebDriver.
     driver.quit();

}
}
