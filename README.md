# Создание исполняемых файлов под Windows, MacOS, Linux простого Приложения с виджетами на фреймворке PyQt5

**💡 Все компиляции в один запускаемый модуль нужно делать на той ОС, где должно работать приложение**

## Создание запускаемого модуля под Windows [treesegm.exe]:
- **`pip install -r requirements.txt`**
- **`pyinstaller --onefile --windowed treesegm.py`**

## Создание запускаемого модуля под MacOS [treesegm.app]:
- **`pip install PyQt5`**
- **`pip install requests matplotlib numpy`**
- **`pip install -q pyinstaller`**
- **`pyinstaller --onefile --windowed --name treesegm.app treesegm.py`**

## Создание запускаемого модуля под Linux [treesegm]:
- **`pip install -r requirements.txt`**
- **`pyinstaller --onefile --windowed --add-data="servers.json:." treesegm.py`**

- Здесь main.py - это основной .py файл вашего приложения. --onefile создает один исполняемый файл, --windowed предотвращает появление консоли при запуске вашего приложения, а --add-data="servers.json:." включает файл servers.json в ваш проект.
- В результате создастся исполняемый файл без расширения в подкаталоге dist проекта. Этот файл можно запускать на Linux как обычное приложение.
- Разделитель в опции --add-data зависит от операционной системы. На Windows используется ;, в то время как на Linux и MacOS используется :.

<p>
<img src="https://github.com/terrainternship/rostelecom_tree_segmentation/blob/ba96f061b0a5d1cf954556b2ceb42c77bf44b48f/command/Dmitry_Panfilov/images/treesegm.jpg" width="90%">
</p>

---
