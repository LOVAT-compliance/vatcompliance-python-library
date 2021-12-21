# Vatcompliance api python library

## Plugin install

The official documentation is located [here](https://developers.vatcompliance.co/omp-tax-rate-api/)

## Getting Started
```
pip install vatcompliance==1.0.0
```

## Package Dependencies
* [Requests](https://github.com/kennethreitz/requests) HTTP library for making RESTful requests to the Vatcompliance API.

Example Request
```
import vatcompliance

client = vatcompliance.Client(api_key='5bedbd829e7442f3a18589ca99fc15b0')
result = client.omp_feed(
    {
        "transaction_id": "ttt4565-85546",
        "transaction_datetime": "2020-01-09T08:27:22 +00:00",
        "transaction_sum": 158.04,
        "currency": "GBP",
        "arrival_country" : "GBR",
        "arrival_city" : "London",
        "arrival_address_line" : "Peckham Road",
        "transaction_status" : "Success",
        "good_code": "62160000",
        "merchant_establishment_country_id": "GBR",
        "vat_percent": 20.00,
        "vat": 28.73,
        "departure_country" : "AUS",
        "getParams": {
            "if_digital": True,
            "if_vat_calculate": True,
        }
    }
)
```

if you se in method POST ?if_digital={true/false}&if_vat_calculate={true/false} set the given parameter in the array as:
```
	"getParams": {
            "if_digital": True,
            "if_vat_calculate": True,
        }
```

## OMP Feed API methods

#### Definition

Omp feed
```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_feed()
```

Omp Tax Rate

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_tax_rate()
```

Omp Report Create

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_report_create()
```

Get Status
```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_status()
```

Get Report

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_get_report()
```

Omp Invoice

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.omp_invoice()
```

## Omp Merchant Api

Merchant feed

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.merchant_send()
```

Merchant Tax Rate

```
client = vatcompliance.Client(api_key='__APIKEY__')
client.merchant_tax_rate()
```

Merchant Vat Checker
```
client = vatcompliance.Client(api_key='__APIKEY__')
client.merchant_vat_checker()
```