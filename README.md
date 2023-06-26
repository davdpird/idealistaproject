# idealistaproject
idealista project
import requests
from bs4 import BeautifulSoup

# Send a GET request to the webpage
url = "https://www.idealista.com/venta-viviendas/madrid-madrid/con-precio-hasta_500000,de-dos-dormitorios,de-tres-dormitorios,de-cuatro-cinco-habitaciones-o-mas/"

headers = {
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.190 Safari/537.36"
}

response = requests.get(url, headers=headers)

# Parse the HTML content
soup = BeautifulSoup(response.content, 'html.parser')

# Find the elements containing the property listings
listings = soup.find_all("div", class_="item-info-container")

# Extract the desired data from each listing
for listing in listings:
    title = listing.find("a", class_="item-link").text.strip()
    price = listing.find("span", class_="item-price").text.strip()
    details = listing.find("span", class_="item-detail").text.strip()
    
    print("Title:", title)
    print("Price:", price)
    print("Details:", details)
    print("-----------------------")






Regenerate response
