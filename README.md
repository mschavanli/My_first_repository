# Crypto Price Checker 🚀
# Author: Samira

import requests

def get_crypto_price(coin="bitcoin"):
    url = f"https://api.coingecko.com/api/v3/simple/price?ids={coin}&vs_currencies=usd"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        price = data[coin]["usd"]
        print(f"The current price of {coin} is ${price}")
    else:
        print("Error fetching data!")

if __name__ == "__main__":
    coin_name = input("Enter a cryptocurrency (e.g., bitcoin, ethereum): ").lower()
    get_crypto_price(coin_name)
