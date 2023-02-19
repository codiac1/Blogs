# Building a web scraper using Python and BeautifulSoup

I’ll be going over how can we make a web scraper using Python and BeautifulSoup.

![](https://cdn-images-1.medium.com/max/800/1*Dd1xU8upH6wu7FRCFZH24w.jpeg)

Let's talk about **dependencies** first, We need to have **Python** installed on our device.

**To install Python, follow these steps: 🐍**

1.  Visit the Python official website ([https://www.python.org/](https://www.python.org/)) and click on the Downloads button.
2.  Download the appropriate installer for your operating system (Windows, Mac, or Linux).
3.  Run the installer and follow the instructions on the screen to complete the installation process.
4.  Verify the installation by opening a terminal or command prompt and typing the following command: `python3 --version`. This should display the version of Python that you have installed.

**To install BeautifulSoup, follow these steps: 🍲**

1.  We can do this by running the following command in your terminal/command prompt: `pip install beautifulsoup4`
2.  **Import necessary libraries:** To start building your web scraper, you need to import the required libraries such as`requests` and `beautifulsoup4`. You can import these libraries in your Python script using the following code:

      
    
        import requests
      `from bs4 import BeautifulSoup`

**Now that we have installed primary dependencies we will start building our web scraper :**

**1. Send an HTTP request:**

To extract data from a website, you need to send an HTTP request to the website’s server. You can use the `requests` library to send an HTTP request and get the response in the form of HTML. We can send a **GET** request to the URL of the website you want to scrape using the following code:

    response = requests.get(url)
    html_content = response.content

**2.** **Parse HTML content:**

Once you have the HTML content, you need to parse it to extract the data you want. BeautifulSoup provides a convenient way to parse the HTML content and extract specific data. We can create a BeautifulSoup object from the HTML content and specify the parser you want to use as follows:

    soup = BeautifulSoup(html_content, 'html.parser')


**3.** **Extract data:**

Once you have the BeautifulSoup object, you can use its methods and attributes to extract the data you want from the HTML content. For example, you can use the `find` method to find a specific tag in the HTML content or use the `find_all` method to find all instances of a specific tag. You can access the text content of a tag using the `text` attribute.

# Extract all instances of the `<a>`  

    links = soup.find_all('a')  

  
# Extract the text content of each `<a>` tag  

    for link in links:  
        print(link.text)

**4. Save data:**

After extracting the data, you can save it in any format you like, such as a CSV file or a JSON file. You can use the `csv` library to write data to a CSV file or the `json` library to write data to a JSON file.

# Write data to a CSV file  

    import csv  
      
    with open('data.csv', 'w', newline='') as file:  
        writer = csv.writer(file)  
        writer.writerow(['text'])  
        for link in links:  
            writer.writerow([link.text])

**5. Repeat the process: 🔁**

Depending on the amount of data you want to scrape, you may need to repeat the process of sending an HTTP request, parsing the HTML content, and extracting data multiple times. You can use a loop to automate the process and extract data from multiple pages of a website.

# Repeat the process for multiple pages  

    pages = [1, 2, 3, 4, 5]  
    for page in pages:  
        url = f'http://example.com/page/{page}'  
        response = requests.get(url)  
        html_content = response.content  
        soup = BeautifulSoup(html_content, 'html.parser')  
        links = soup.find_all('a')  
        with open('data.csv', 'a', newline='') as file:  
            writer = csv.writer(file)  
            for link in links:  
                writer.writerow([link.text])

**Note:** _In this code, the variable_ `_pages_` _contains a list of page numbers for a multi-page website. The loop iterates over each page and sends an HTTP request to the URL of each page, parses the HTML content, extracts the data, and appends the data to the CSV file._

-   **Final Step:** **How to run all of this?**

1.  Save the file with a .py extension, for example, `web_scraper.py`.
2.  Open the terminal or command prompt and navigate to the folder where the .py file is saved.
3.  Type the following command to run the code: `python web_scraper.py`
4.  Wait for the code to run and scrape the data from the website.
5.  Check the folder where the .py file is saved, and you should see the generated CSV file `data.csv`.

**That’s it! 🎉**

You have successfully executed the code for building a web scraper using Python and BeautifulSoup.

**Call for Action 🎯**

If you find the guide helpful, feel free to star the repo and follow me.
