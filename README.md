# CoinsBill Python bindings 


This is a python library for interacting with the [CoinsBill API](hhttps://www.coinsbill.com/developers).

### Example Usage

```python
from coinsbill import CoinsBill
access_token = 'a9esthaVUjOuvzTCSTXsJUCK0lCMCk'
api = CoinsBill(access_token)

# Create New Invoice
response = api.invoice.create( 
    email="bill@dow.com",
    currency="USD",
    country="US",
    billing_first_name="Sam",
    items=[{
            "name": "fruits", 
            "quantity": 10, 
            "unit_price": 2
            }, 
            {
            "name": "coffee", 
            "quantity": "4", 
            "unit_price": 3 
            }] 
    )

assert response.status_code == 201  # Successfull Create Invoice 
response.json()   # Load the body's JSON data.

# Get all Invoices
response = api.invoice.get()
assert response.status_code == 200  # Make sure we got back a successful response.

# Get Invoice by ID
response = api.invoice.get('8G98A')
assert response.status_code == 200  # Make sure we got back a successful response.



   

```

Note:  You can find the app tokens and an authenticated bearer token on Dashboard at the [CoinsBill Dashboard](https://www.coinsbill.com/dashboard).

### Installation 

This package is called ``coinsbill`` on PyPI. Install using::

    $ pip install --upgrade  coinsbill


