import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.service import  Service
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.action_chains import ActionChains

s=Service('C:\Test\chromedriver.exe')
driver = webdriver.Chrome(service=s)
action = ActionChains(driver)


#Авторизоватся в админке

driver.get('https://adminqa.neapro.site/login')
driver.maximize_window()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#admin_email").send_keys("moderat@neapro.ru")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#admin_password").send_keys("Aa123456")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "li#admin_submit_action > input[name='commit']").click()
time.sleep(5)

#Найти пользователя

driver.find_element(By.CSS_SELECTOR, "li#students > a").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "li#users > a").click()
time.sleep(3)
driver.get('https://adminqa.neapro.site/users/2169')
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_statement > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Отклонен")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_passport > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.DOWN)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Отклонен")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_contract > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Отклонен")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_consent > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Отклонен")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_diploma > .status_tag").click()
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Отклонен")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)

#Открыть сайт и авторизоватся

driver.get('https://qa.neapro.site/login')
driver.maximize_window()
driver.find_element(By.CSS_SELECTOR, ".fieldset:nth-child(1) input").send_keys("mr.malina.qa@gmail.com")
driver.find_element(By.CSS_SELECTOR, ".fieldset:nth-child(2) input").send_keys("123456789")
driver.find_element(By.CSS_SELECTOR, ".btn").click()
time.sleep(7)

#Открыть и заполнить паспорт


driver.find_element(By.CSS_SELECTOR, ".form:nth-child(2) .document-tile:nth-child(1) > .document-name") .click()
time.sleep(1)
driver.find_element(By.ID, "surname").clear()
time.sleep(1)
driver.find_element(By.ID, "surname").send_keys("Иванов")
time.sleep(1)
driver.find_element(By.ID, "name").clear()
time.sleep(1)
driver.find_element(By.ID, "name").send_keys("Иван")
time.sleep(1)
driver.find_element(By.ID, "patronymic").clear()
time.sleep(1)
driver.find_element(By.ID, "patronymic").send_keys("Иванович")
time.sleep(1)
driver.find_element(By.ID, "passportSeries").clear()
time.sleep(1)
driver.find_element(By.ID, "passportSeries").send_keys("4474")
time.sleep(1)
driver.find_element(By.ID, "passportNumber").clear()
time.sleep(1)
driver.find_element(By.ID, "passportNumber").send_keys("663315")
time.sleep(1)
driver.find_element(By.ID, "code").clear()
time.sleep(1)
driver.find_element(By.ID, "code").send_keys("246421")
time.sleep(1)
driver.find_element(By.ID, "cardId").clear()
time.sleep(1)
driver.find_element(By.ID, "cardId").send_keys("34612345678")
time.sleep(1)
driver.find_element(By.ID, "issued").clear()
time.sleep(1)
driver.find_element(By.ID, "issued").send_keys("Ольгой Михайловной")
time.sleep(1)
driver.find_element(By.ID, "phone").clear()
time.sleep(1)
driver.find_element(By.ID, "phone").send_keys("8005353535")



#Датапикер Рождение

driver.find_element(By.CSS_SELECTOR, "div#birthday  input[name='date']").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".mx-btn.mx-btn-current-year.mx-btn-text").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "tr:nth-of-type(3) > td:nth-of-type(2) > div").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "tr:nth-of-type(2) > td:nth-of-type(1) > div").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "td[title='1995-04-15'] > div").click()
time.sleep(1)

#Датапикер ддата выдачи

driver.find_element(By.CSS_SELECTOR, "div#dateOfIssue  input[name='date']").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".mx-btn.mx-btn-current-year.mx-btn-text").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "tr:nth-of-type(3) > td:nth-of-type(1) > div").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "tr:nth-of-type(3) > td:nth-of-type(1) > div").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "td[title='2014-07-09'] > div").click()
time.sleep(1)



#Адрес

time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".vue-dadata__input").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".vue-dadata__input").send_keys("\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b\b")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".vue-dadata__input").send_keys("г Санкт Петербург")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".vue-dadata__input").send_keys(Keys.DOWN)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".vue-dadata__input").send_keys(Keys.ENTER)
time.sleep(3)

# Добавить документы
driver.execute_script("window.scrollTo(0, 1300)")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".upload-widget img[alt='X']").click()
driver.find_element(By.CSS_SELECTOR, ".upload-widget > input").send_keys("C:\\1\\1.png")
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, ".btn.fill").click()
time.sleep(3)

#Прикрепить диплом


driver.find_element(By.CSS_SELECTOR, "div:nth-of-type(2) > .body.documents-tiles > div:nth-of-type(2) > .document-status").click()
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, ".upload-widget img[alt='X']").click()
driver.find_element(By.CSS_SELECTOR, ".upload-widget > input").send_keys("C:\\1\\1.png")
driver.execute_script("window.scrollTo(0, 1300)")
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, ".btn.fill").click()
time.sleep(3)

#Прикрепить Договор
driver.find_element(By.CSS_SELECTOR, "div:nth-of-type(3) > .body.documents-tiles > div:nth-of-type(1)").click()
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, ".upload-widget img[alt='X']").click()
driver.find_element(By.CSS_SELECTOR, ".upload-widget > input").send_keys("C:\\1\\1.png")
driver.execute_script("window.scrollTo(0, 1300)")
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, ".btn.fill").click()
time.sleep(3)

#Прикрепить Заявление

driver.find_element(By.CSS_SELECTOR, "div:nth-of-type(3) > .body.documents-tiles > div:nth-of-type(2)").click()
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".upload-widget img[alt='X']").click()
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".upload-widget > input").send_keys("C:\\1\\1.png")
driver.execute_script("window.scrollTo(0, 1300)")
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".btn.fill").click()
time.sleep(2)

#Прикрепить Согласие

driver.find_element(By.CSS_SELECTOR, ".body.documents-tiles > div:nth-of-type(3)").click()
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".upload-widget img[alt='X']").click()
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".upload-widget > input").send_keys("C:\\1\\1.png")
driver.execute_script("window.scrollTo(0, 1300)")
time.sleep(2)
driver.find_element(By.CSS_SELECTOR, ".btn.fill").click()

#Авторизоватся в админке
driver.get('https://adminqa.neapro.site/login')
time.sleep(5)

#Принять документы
driver.find_element(By.CSS_SELECTOR, "li#students > a").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "li#users > a").click()
time.sleep(3)
driver.get('https://adminqa.neapro.site/users/2169')
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_statement > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Принят")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_passport > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.DOWN)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Принят")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_contract > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Принят")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_consent > .status_tag").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Принят")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".documents_diploma > .status_tag").click()
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys("Принят")
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".select2-search__field").send_keys(Keys.ENTER)

#Открыть личный кабинет

driver.get('https://qa.neapro.site')
time.sleep(5)

#Открыть боковое меню
driver.find_element(By.CSS_SELECTOR, ".avatar.icon > img[alt='avatar']").click()
time.sleep(3)

# Изменить номер
driver.find_element(By.CSS_SELECTOR, "[href='\/cabinet\/security'] .icon").click()
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, "div:nth-of-type(1) > .icon > .name").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input[name='phone']").clear()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input[name='phone']").send_keys(8563836478)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "form > .btn.fill").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "img[alt='X']").click()
time.sleep(1)

# Изменить пароль

driver.find_element(By.CSS_SELECTOR, "img[alt='block']").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#oldPassword").send_keys(123456789)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#newPassword").send_keys(1234567890)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#confirmPassword").send_keys(1234567890)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "form > .btn.fill").click()
time.sleep(5)
driver.find_element(By.CSS_SELECTOR, "input#oldPassword").clear()
time.sleep(1)

#Выйти из профиля
driver.find_element(By.CSS_SELECTOR, ".avatar.icon > img[alt='avatar']").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, ".logout_name").click()
time.sleep(3)

#Войти в профиль

driver.find_element(By.CSS_SELECTOR, ".fieldset:nth-child(1) input").send_keys("mr.malina.qa@gmail.com")
driver.find_element(By.CSS_SELECTOR, ".fieldset:nth-child(2) input").send_keys("1234567890")
driver.find_element(By.CSS_SELECTOR, ".btn").click()
time.sleep(5)

#Снова поменять пароль

driver.find_element(By.CSS_SELECTOR, ".avatar.icon > img[alt='avatar']").click()
time.sleep(3)

driver.find_element(By.CSS_SELECTOR, ".links > li:nth-of-type(2) > a").click()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "img[alt='block']").click()
time.sleep(3)
driver.find_element(By.CSS_SELECTOR, "input#oldPassword").send_keys(1234567890)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#newPassword").clear()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#newPassword").send_keys(123456789)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#confirmPassword").clear()
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "input#confirmPassword").send_keys(123456789)
time.sleep(1)
driver.find_element(By.CSS_SELECTOR, "form > .btn.fill").click()
time.sleep(1)

#Открыть сертефикаты

driver.find_element(By.CSS_SELECTOR, "li:nth-of-type(4) > a > .icon").click()
