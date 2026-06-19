# Image_Scraping
# Google Image Scraper using Selenium

A Python-based web scraping project that automatically searches images on Google Images and downloads them using **Selenium WebDriver** and **Requests**.

This project automates the browser, searches for a given keyword, scrolls through Google Images, extracts image URLs, and downloads images into a local folder.

---

## 🚀 Features

* Automates Google Image search using Selenium
* Supports custom search queries
* Automatically scrolls to load more images
* Extracts image URLs dynamically
* Downloads images using Python Requests
* Creates a folder automatically for storing images
* Uses ChromeDriver Manager for easy driver setup

---

## 🛠️ Technologies Used

* Python
* Selenium
* Requests
* Chrome WebDriver
* Webdriver Manager

---

## 📂 Project Structure

```
Google-Image-Scraper/
│
├── image/
│   ├── Virat kohli_0.jpg
│   ├── Virat kohli_1.jpg
│   └── ...
│
├── scraper.py
│
└── README.md
```

---

## ⚙️ Installation

### 1. Clone Repository

```bash
https://github.com/ProPranavgupta/Image_Scraping.git
```

### 2. Install Required Libraries

```bash
pip install selenium requests webdriver-manager
```

---

## ▶️ How to Run

Run the Python file:

```bash
python scraper.py
```

The program will:

1. Open Google Images
2. Search for the given query
3. Scroll and load images
4. Download images into the `image` folder

---

## 🔧 Configuration

You can change the search keyword:

```python
query = "Virat kohli"
```

Example:

```python
query = "Artificial Intelligence"
```

You can also change the download folder:

```python
save_folder = "image"
```

---

## 🧠 How It Works

### 1. Browser Automation

Selenium opens Chrome using WebDriver:

```python
driver = webdriver.Chrome(
    service=services,
    options=options
)
```

---

### 2. Google Image Search

The script opens Google Images and enters the search query:

```python
search_box.send_keys(query)
search_box.send_keys(Keys.RETURN)
```

---

### 3. Image Loading

Google Images loads images dynamically. The script scrolls down multiple times:

```python
for _ in range(6):
    driver.execute_script(
        "window.scrollTo(0, document.body.scrollHeight);"
    )
```

This forces Google Images to load more images.

---

### 4. Extract Image URLs

The scraper finds all image elements:

```python
images = driver.find_elements(
    By.CSS_SELECTOR,
    "img[src^='http']"
)
```

Then it extracts the image source URL.

---

### 5. Download Images

Requests downloads the images:

```python
response = requests.get(src)
```

The images are saved locally:

```
image/
   Virat kohli_0.jpg
   Virat kohli_1.jpg

```

## 📌 Future Improvements

* Add duplicate image detection
* Add image quality filtering
* Add support for multiple search queries
---

## 👨‍💻 Author

Pranav Gupta

---

## ⭐ If you like this project

Give it a star ⭐ and feel free to improve it.

Selenium Image Scraping Project
