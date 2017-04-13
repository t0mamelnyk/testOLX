
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class OLXTest {

    WebDriver driver;

    @Before public void setup() {
        System.setProperty("webdriver.chrome.driver", "seleniumDrivers/chromedriver.exe");
        driver = new ChromeDriver();
    }

    @Test public void testNewAd() {
        login("userName", "password");
        driver.get("https://www.olx.ua");

        // add new ad
    }

    void login(String userName, String password) {
        // TODO check if already logged in
        driver.get("https://www.olx.ua");
        driver.findElement(By.id("topLoginLink")).click();
        driver.findElement(By.id("userEmail")).sendKeys(userName);
        driver.findElement(By.id("userPass")).sendKeys(password);
        driver.findElement(By.id("se_userLogin")).click();
    }
}
