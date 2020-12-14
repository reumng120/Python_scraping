# Learning how to book a meeting on Zoom with Python Selenium.

This sample practices the selenium API by booking a meeting on Zoom. Don't do any illegal things.

## Setup selenium and use the chromedriver. 
Check your chrome browser version and download the driver [here](https://chromedriver.chromium.org/downloads).
```
driver = webdriver.Chrome(options=options, executable_path=r'%s' % a_path)
driver.set_window_size(1920, 1080)
```

## Input account and password.
```
WebDriverWait(self.driver,20).until(EC.element_to_be_clickable((By.ID, "login_id"))).click()
WebDriverWait(self.driver,20).until(EC.element_to_be_clickable((By.ID, "login_id"))).send_keys(account)

WebDriverWait(self.driver,20).until(EC.element_to_be_clickable((By.ID, "login_pwd"))).click()
WebDriverWait(self.driver,20).until(EC.element_to_be_clickable((By.ID, "login_pwd"))).send_keys(password)
```

## Submit to login
```
WebDriverWait(self.driver,20).until(EC.element_to_be_clickable((By.XPATH, "//button[@type='submit']"))).click()
```

## Book a meeting
```
# Click the button of '會議'
WebDriverWait(self.driver,60).until(EC.element_to_be_clickable((By.XPATH, "(//a[contains(text(),'會議')])[2]"))).click()

# Book a new meeting
WebDriverWait(self.driver,90).until(EC.element_to_be_clickable((By.XPATH, "//a[contains(text(),'安排新會議')]"))).click()

# Input your meething topic
WebDriverWait(self.driver,90).until(EC.element_to_be_clickable((By.XPATH, "//input[@name='topic']"))).click()
WebDriverWait(self.driver,90).until(EC.element_to_be_clickable((By.XPATH, "//input[@name='topic']"))).send_keys(meeting_topic)
```

```
## Submit the booking
WebDriverWait(self.driver,90).until(EC.element_to_be_clickable((By.XPATH, "//button[@type='submit']"))).click()
```


