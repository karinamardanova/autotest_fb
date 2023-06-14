import unittest
from selenium import webdriver

class FacebookLoginTest(unittest.TestCase):

    def setUp(self):
        self.driver = webdriver.Chrome()  # Используем Chrome WebDriver, можно заменить на другой

    def test_successful_login(self):
        self.driver.get('https://www.facebook.com/')  # Открываем страницу Facebook
        self.driver.find_element_by_id('email').send_keys('your_email')  # Вводим ваш email в поле ввода
        self.driver.find_element_by_id('pass').send_keys('your_password')  # Вводим ваш пароль в поле ввода
        self.driver.find_element_by_name('login').click()  # Кликаем на кнопку "Войти"
        self.driver.implicitly_wait(10)  # Ждем 10 секунд, чтобы страница загрузилась

        # Проверяем статус авторизации
        if 'home' in self.driver.current_url:
            status = 'Успешно'
        else:
            status = 'Не успешно'

        self.assertEqual(status, 'Успешно')  # Проверяем, что статус авторизации равен "Успешно"

    def tearDown(self):
        self.driver.quit()  # Закрываем браузер после выполнения каждого теста

if __name__ == '__main__':
    unittest.main()
