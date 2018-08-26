# apigateway
PT Asuransi Heksa Insurance X Moringa API Gateway 



### Submit aplication Data

##### Features
  - Submit aplication to Moringa API

##### Endpoint
POST
```sh
http://heksaku.moringaku.com/my/heksaku.php
```
#### URL Params Required:
##### -Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |

##### -Body
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ProductName| | [text] | Y |150 | |
|ProductPackageName| |[text] | Y |150 | |
|Premium| |[number]| Y | | |
|SumInsured| |[number]| Y | | |
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
|TransactionDate| |[date] | Y | | format dd/MM/yyyy |
|PolicyHolder| |[jsonObject] | Y | | |
|| FullName |[text] | Y | 250 | |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | | |
|| KTPNo |[text] | Y | 16 | |
|| DOB |[date] | Y | | format dd/MM/yyyy|
|| Address |[text] | Y | 200 | |
|| Sex |[text] | Y | | e.x pria, wanita |
|| ProvinceName |[text] | Y | |  |
|| CityName |[text] | Y | | |
|Insured| |[jsonObject] | Y | | |
|| FullName |[text] | Y | 250 | |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | | |
|| KTPNo |[text] | Y | 16 | |
|| DOB |[date] | Y | | format dd/MM/yyyy|
|| Address |[text] | Y | 200 | |
|| Sex |[text] | Y | | e.x pria, wanita |
|| ProvinceName |[text] | Y | |  |
|| CityName |[text] | Y | | |
|Beneficiary| |[jsonObject] | Y | | |
|| FullName |[text] | Y | 50 | |
|| Relation |[text] | Y | |e.x  istri, suami, anak, ayah, ibu, kakak, adik, orang tua|
|| Bob |[date] | Y | | format dd/MM/yyyy|

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/my/heksaku.php",
    authorization: {
        "type" : "Basic Auth",
        "username": "5D89006A21776A45E050A8C04E0A33D8",
        "password":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    headers: {
        "Authorization": "5D89006A21776A45E050A8C04E0A33D8",
    }
    dataType: "json",
    type : "POST",
    data: { 
          "ProductName": "Heksa Proteksi Plus",
          "ProductPackageName": "Platinum",
          "premium": "1500000",
          "SumInsured":"65000000"
          "referenceCode": "PASPOLXX001",
          "ReferenceCode": "31/01/2017",
          "policyHolder": {
            "firstName": "Jhon",
            "lastName": "Dhoe",
            "email": "jhon.doe@gmail.com",
            "phone": "085667788990",
            "NIK": "0923384958674349",
            "dob": "02/07/1990",
            "address": "",
            "sex": "pria/wanita",
            "provinceID": "1",
            "cityID": "1"
          },
          "insured": {
            "firstName": "Jhon",
            "lastName": "Dhoe",
            "email": "jhon.doe@gmail.com",
            "phone": "085667788990",
            "NIK": "0923384958674349",
            "dob": "02/07/1990",
            "address": "",
            "sex": "pria/wanita",
            "provinceID": "1",
            "cityID": "1"
          },
          "beneficiary": {
            "fullName": "Mika Dhoe",
            "relation": "adik",
            "dobBen": "02/07/1993"
          }
    },
    success : function(response) {
      console.log(response);
    }
  });
```

##### Sample response:
success
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
    }
}
```

### Submit Payment Status

##### Features
  - Submit Payment Status
##### Endpoint
POST
```sh
http://heksaku.moringaku.com/my/heksaku2.php
```
#### URL Params Required:
##### -Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |

##### -Body
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
|status| |[text] | Y |500 | Berhasil, Gagal|


### Request Data Referral

##### Features
  - Request Data Referral
##### Endpoint
POST
```sh
http://heksaku.moringaku.com/my/heksaku3.php
```
#### URL Params Required:
##### -Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
