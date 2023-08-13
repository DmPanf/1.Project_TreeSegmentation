# FastAPI_TreeSegmentation_Project
Создание .exe файла

## 📚 Документация на FastAPI:
####  📚 1 FastAPI. Документация на Yandex Cloud (порт 8001):
- **🔸[Yandex 8001/DOCS](http://158.160.69.94:8001/docs)**
- **🔹[Yandex 8001/REDOC](http://158.160.69.94:8001/redoc)**

#### 📚 2 FastAPI. Документация на резервном VPS  (порт 8001 с тестовой обработкой изображений):
- **🔸[VPS 8001/DOCS](http://api-serv.tu:8001/docs)**
- **🔹[VPS 8001/REDOC](http://api-serv.tu:8001/redoc)**

## 📡 Примеры клиентов FastAPI [CLI, Google Colab, Bot, Desktop PyQt5, Kivy, React, web-client, Flask ..]:

![image](https://github.com/terrainternship/rostelecom_tree_segmentation/assets/99917230/55a69900-5e0f-45a3-a70f-b01a94e1c2f8)


- **https://github.com/terrainternship/rostelecom_tree_segmentation/tree/dev/command/Dmitry_Panfilov**

#### 💎 Пример Telegram-бота [@m_y_t_e_l_e_g_r_a_m_bot]: 
- **🌐  https://t.me/m_y_t_e_l_e_g_r_a_m_bot**

#### 📱 Android-client (React PWA):
- **🌐 http://api-serv.ru:3000/** + **Добавить ярлык** на смартфоне

#### 📡 Web-client (HTML+JS):
- **🌐 http://api-serv.ru:8080/**

#### Резервный FastAPI + Telegram Bot [@aFa_st_API_Bot]:
- **🌐 http://api-serv.ru:8001/docs**
- **🌐  https://t.me/aFa_st_API_Bot**


#### 📡 Прочие способы подключения к FastAPI:
- командная строка Linux **`curl -X 'POST' -F 'image=@img01.jpg' 'http://apiserv.ru:8001/process_image' -o 'res01.jpg'`**
- Клиентское приложение на **PyQt5** (для работы на Desktop и с возможностью компиляции в виде .exe файла под Windows)
- Клиентское приложение на **Kivy** (с возможностью создания модуля .apk под Android)
- Web-приложение на **React** (с возможностью создания модуля PWA или .apk для работы на Android)
- Google Colab

<code>
import requests
url = "http://apiserv.ru:8001/process_image"
files = {"image": ("img03.jpg", open("img03.jpg", "rb"), "image/jpeg")}
response = requests.post(url, files=files)
with open("result.jpg", "wb") as f:
    f.write(response.content)
</code>

---
### Пример клиента на PyQt5

![image](https://github.com/terrainternship/rostelecom_tree_segmentation/assets/99917230/8f420fbe-bd9b-4160-8efa-450ce1337675)
[Image = https://raw.githubusercontent.com/terrainternship/rostelecom_tree_segmentation/dev/command/Dmitry_Panfilov/images/pyqt5-1.jpg]

---
### Пример клиентов на Kivy и React

<p>
<img src="https://raw.githubusercontent.com/terrainternship/rostelecom_tree_segmentation/dev/command/Dmitry_Panfilov/images/kivy1.jpg" width="47%">
<img src="https://raw.githubusercontent.com/terrainternship/rostelecom_tree_segmentation/dev/command/Dmitry_Panfilov/images/react1.jpg" width="43%">
</p>

---
## Подключение Telegram Bot к серверу с FastAPI (на примере пилотной обработки изображений)

- **[✅ Пример "заглушки" в Google Colab](https://colab.research.google.com/drive/1zECS_lvI9jAnQ90c4bysX1fnpwhWHiVo?usp=sharing)**
- **[✅ Локальная копия файла Jupyter Notebook](https://github.com/terrainternship/rostelecom_tree_segmentation/blob/dev/command/Dmitry_Panfilov/0step.image_pilot_process.ipynb)**

---

## 💠 Краткое описание FastAPI при использовании трех видов клиентов (web-приложение, Android-приложение и Telegram-Bot):
![scheme_01.jpg](https://raw.githubusercontent.com/terrainternship/rostelecom_tree_segmentation/main/command/Dmitry_Panfilov/images/scheme_01.jpg)

- **FastAPI** - фреймворк для разработки веб-приложений на Python, который позволяет быстро и легко создавать API. 
- FastAPI использует асинхронное программирование и автоматическую генерацию документации API.
- Необходиом настроить сервер, на котором будет запущен **FastAPI**, чтобы он был доступен для всех трех клиентов. В нашем случае имеет смысл создавать отдельные функции для обработки разных типов клиентов.
- Здесь **FastAPI** используется для создания двух **POST-маршрутов** - один для получения изображения и возврата предсказаний для него, а другой для получения изображения через **web-client**, **Android-приложение** или **бот Telegram** и возврата предсказаний в чат/приложение.
- Также необходимо обратить внимание на то, что **запросы и ответы должны быть структурированы таким образом, чтобы их можно было обрабатывать каждым клиентом**. 
- Важно проверять соответствие типов данных и форматов запросов и ответов между клиентом и сервером. В случае с **Telegram-Bot**, необходимо убедиться, что запросы и ответы отправляются и получаются с использованием правильных **API-методов и структур данных**.
- В случае с **Android-приложением**, необходимо убедиться в правильности работы сетевых запросов и ответов, а также в том, что используется безопасное соединение. Как вариант, можно использовать простое в использовании и настройке клиентское приложение VPN WireGuard.
- При установке через **Docker** нужны отдельные файлы **Dockerfile** для самого приложения **FastAPI** и серверной части **Telegram-бота**, т.к. у них разные требования и конфигурации.

---
## 🔬 Заметки для тестирования FastAPI:
#### Web-приложение:
- Корректность обработки запросов и отправки ответов, включая проверку кодов состояния HTTP.
- Корректность работы пользовательского интерфейса и взаимодействия с API.
- Проверка безопасности приложения, включая корректность валидации пользовательского ввода и предотвращение возможных атак(?).

#### Android-приложение:
- Корректность обработки запросов и отправки ответов, включая проверку кодов состояния HTTP.
- Корректность работы интерфейса и взаимодействия с API.
- Проверка безопасности приложения, включая корректность обработки пользовательского ввода и предотвращение возможных атак, таких как внедрение нежелательного программного кода (Malware) или захват пользовательских данных.

#### Telegram-Bot:
- Корректность обработки запросов и отправки ответов, включая проверку кодов состояния HTTP.
- Проверка корректности работы Telegram-Bot, включая получение и обработку сообщений, отправку ответов и другие команды Telegram-Bot API.
- Проверка безопасности приложения, включая корректность обработки пользовательского ввода и предотвращение возможных атак, таких как внедрение нежелательного программного кода или получение несанкционированного доступа к данным пользователей.

---
## ⚖️ Неактуальные пока вопросы по REST API Model:
1. **Базовая конфигурация Сервера, БД, оборудования Телеком:**
- характеристики сервера примерные (есть ли CUDO, объем RAM..)?
- все на одном сервере?
- наличие белого IP-адреса для Интернет?
- требования к клиентам по аутентификации?
2. **Требования к клиентам:**
- единый интерфейс или API?
- все приложения асинхронны или нужно управлять очередью?
- перечень запросов фиксирован или может меняться?
3. **Общие вопросы:**
- будет ли обновляться модель НС и как часто? В каком виде передаем финальный набор файлов?
- количество одновременных запросов на сервер?
- скорость каналов связи и лимиты на передаваемые объемы информации?
- требования к оформлению решения, кода, документации (формат, язык, и т.д.)?
