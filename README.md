# Github-topics-web-scraping-
![archi web scraping](https://github.com/user-attachments/assets/57d0f679-beea-4cdb-a502-3e4c8e9f9e09)

Web scraping is a powerful technique for programmatically extracting and analyzing data from websites. It's commonly used for building datasets to support research, data analysis, or educational purposes. In this project, we’ll build a web scraper from scratch using Python and its ecosystem of libraries.

---

## 📌 Project Overview

In this project, we will scrape GitHub’s [Topics page](https://github.com/topics) to collect information about trending repositories categorized by topic. Our objective is to gather details about the top 25 repositories for each topic and save this information in structured CSV files.

### 🧠 Concepts Introduced

- What is web scraping?  
- Overview of GitHub Topics  
- Problem statement and goal of this project  
- Tools and libraries used:
  - Python  
  - `requests` (for downloading HTML)  
  - `BeautifulSoup` (for parsing HTML)  
  - `pandas` (for data manipulation and storage)  

---

## 🧭 Project Workflow

### Step 1: Scrape the GitHub Topics Page

We'll start by scraping the main GitHub topics page to extract:

- Topic title  
- Topic page URL  
- Topic description  

### Step 2: Scrape Top Repositories per Topic

For each topic page, we’ll collect information about the top 25 repositories:

- Repository name  
- Owner's username  
- Number of stars  
- Repository URL  

The final output will be a CSV file per topic with the following structure:

```csv
Repo Name,Username,Stars,Repo URL
three.js,mrdoob,69700,https://github.com/mrdoob/three.js
libgdx,libgdx,18300,https://github.com/libgdx/libgdx
```

---

## 🔧 Step-by-Step Guide

### 1️⃣ Scraping GitHub Topics

**Goal:** Extract all topics listed on the [GitHub Topics](https://github.com/topics) page.

**Steps:**

* Use the `requests` library to download the HTML content of the topics page.
* Use `BeautifulSoup` to parse the page.
* For each topic card, extract:

  * Topic title  
  * Topic URL  
  * Topic description  
* Store the results in a pandas DataFrame.

### 2️⃣ Extracting Repositories from Topic Pages

**Goal:** For each topic, visit its page and collect data on the top 25 repositories.

**Steps:**

* Use the topic URLs collected earlier.
* For each topic page:

  * Download the HTML with `requests`.
  * Parse the page using `BeautifulSoup`.
  * Extract details for each of the top repositories:

    * Repository name  
    * Owner’s username  
    * Number of stars (convert from shorthand like 12k to 12000)  
    * Repository URL  
* Store this data in a list of dictionaries or directly into a DataFrame.

### 3️⃣ Saving Data to CSV Files

**Goal:** Save each topic’s repository data into its own CSV file.

**Steps:**

* Use `pandas` to convert the list of repositories into a DataFrame.
* Save the DataFrame to a `.csv` file using the topic title as the filename:

  ```python
  df.to_csv(f"data/{topic_title}.csv", index=False)
  ```
* Create a directory called `data/` (if it doesn’t exist) to store your files.

---

## 📂 Output Structure

After running the script, you’ll get a `data/` folder with one CSV file per topic:

```
data/
    ├── 3D.csv
    ├── Ajax.csv
    ├── Algorithm.csv
    ├── Amazon Web Services.csv
    ├── Amp.csv
    ├── Android.csv
    ├── Angular.csv
    ├── Ansible.csv
    ├── API.csv
    ├── Arduino.csv
    ├── ASP.NET.csv
    ├── Awesome Lists.csv
    ├── Azure.csv
    ├── Babel.csv
    ├── Bash.csv
    ├── Bitcoin.csv
    ├── Bootstrap.csv
    ├── Bot.csv
    ├── C++.csv
    ├── C.csv
    ├── Chrome extension.csv
    ├── Chrome.csv
    ├── Clojure.csv
    ├── Code quality.csv
    ├── Code review.csv
    ├── Command-line interface.csv
    ├── Compiler.csv
    ├── Continuous integration.csv
    ├── Cryptocurrency.csv
    └── Crystal.csv

```

Each CSV will contain:

* Repository Name  
* Owner Username  
* Star Count  
* Repository URL  

---

## 💡 Example CSV Output

```csv
Repo Name,Username,Stars,Repo URL
three.js,mrdoob,69700,https://github.com/mrdoob/three.js
libgdx,libgdx,18300,https://github.com/libgdx/libgdx
...
```

---

## 📄 Final Notes

* All code is written in a Jupyter notebook for easy demonstration and documentation.
* The final version includes scraping of the GitHub Topics page, repository details per topic, and saving top repositories into CSV files.
* This project is a great practice for web scraping, HTML parsing, and basic data wrangling using Python.

---

## 🚀 Technologies Used

* Python 3.x  
* `requests`  
* `BeautifulSoup`  
* `pandas`  
* Jupyter Notebook  

---

## 📘 License

This project is licensed under the MIT License. Feel free to use, modify, and share it as needed.

---

⭐ **If you find this project helpful, feel free to give it a star!**
