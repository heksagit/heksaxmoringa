# apigateway
PT Asuransi Heksa Insurance X Moringa API Gateway 



### Product Inquiry

##### Features
  - Submit aplication and generate policy

##### Endpoint
POST
```sh
/rest/v1/productinquiry
```
#### URL Params Required:
##### -Header
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|token| [text] | Y | | |
|clienId|[text] | Y | | |

##### -Body
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|productID| | [number] | Y | | |
|productPackageId| |[number] | Y | | |
|premium| |[number]| Y | | |
|referenceCode| |[text] | Y | 20 | |
|transactionDate| |[date] | Y | | format dd/MM/yyyy |
|voucherCode| |[text] | N | 20 | |
|policyHolder| |[jsonObject] | Y | | |
|| firstName |[text] | Y | 50 | |
|| lastName |[text] | N | 50 | |
|| email |[text] | Y | 50 | |
|| phone |[text] | Y | | |
|| NIK |[text] | Y | 16 | |
|| dob |[date] | Y | | format dd/MM/yyyy|
|| address |[text] | Y | 200 | |
|| sex |[text] | Y | | e.x pria, wanita |
|| provinceId |[text] | Y | |  |
|| cityId |[text] | Y | | |
|insured| |[jsonObject] | Y | | |
|| firstName |[text] | Y | 50 | |
|| lastName |[text] | N | 50 | |
|| email |[text] | Y | | 50 |
|| phone |[text] | Y | | |
|| NIK |[text] | Y | 16 | |
|| dob |[date] | Y | | format dd/MM/yyyy|
|| address |[text] | Y | 200 | |
|| sex |[text] | Y | | e.x pria, wanita |
|| provinceId |[text] | Y | |  |
|| cityId |[text] | Y | | |
|beneficiary| |[jsonObject] | Y | | |
|| fullName |[text] | Y | 50 | |
|| relation |[text] | Y | |e.x  istri, suami, anak, ayah, ibu, kakak, adik, orang tua|
|| dob |[date] | Y | | format dd/MM/yyyy|

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "/rest/v1/productinquiry",
    headers: {
        "token": "5D89006A21776A45E050A8C04E0A33D8",
        "clienId":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    dataType: "json",
    type : "POST",
    data: { 
          "productID": "1",
          "productPackageID": "1",
          "premium": "7500",
          "referenceCode": "PASPOLXX001",
          "transactionDate": "31/01/2017",
          "voucherCode": "ULTAH2ASJ",
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
        "linkPolicy": "https://klikasuransiku.com/downloadDirectPolicy?transIdMerchant=2017122803041&uid=5D89006A21776A45E050A8C04E0A33D8&pid=e3d46ec4-277e-4eaf-addb-04d9c604ba3d",
        "referenceCode": "PASPOLXX001",
        "policyNo": "171950000017"
    }
}
```

### Check Blacklist
##### Endpoint
POST
```sh
/rest/v1/cekblacklist
```

#### URL Params Required:
##### -Header
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|token| [text] | Y | | |
|clienId|[text] | Y | | 
##### -Body
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|name| [text] | Y | 50 | format dd/MM/yyyy |
|dob|[text] | Y | | format dd/MM/yyyy |

#### Sample Call
```sh
$.ajax({
    url: "/rest/v1/cekblacklist",
    dataType: "json",
    type : "POST",
    data: {  
        "name": "SUYATNO",
        "dob": "29/10/1964"
    },
    success : function(response) {
      console.log(response);
    }
  });
```

#### Sample Response
| Params | Data Type |
|--|--|
|name| [text] |
|dob|[text] | format dd/MM/yyyy
|hasil|[integer] 0 = untuk user tidak termasuk blacklist, 1 = jika user adalah user blacklist dan transaksi tidak boleh di lanjutkan

```sh
{
    "name": "SUYATNO",
    "dob": "29/10/1964",
    "hasil": 1
}
```

### Get List of Provinces

##### Features
  - get all Province

##### Endpoint
GET
```sh
/rest/v1/getProvince
```

#### URL Params Required:
##### -Header
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|token| [text] | Y | | |
|clienId|[text] | Y | |

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "/rest/v1/getProvince",
    headers: {
        "token": "5D89006A21776A45E050A8C04E0A33D8",
        "clienId":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    dataType: "json",
    type : "GET",
    success : function(response) {
      console.log(response);
    }
  });
```

##### Sample response:
success
```sh
{
    "provinceList": [
        {
            "provinceName": "-",
            "provinceId": "0"
        },
        {
            "provinceName": "BALI",
            "provinceId": "14"
        },
        {
            "provinceName": "BANGKA BELITUNG",
            "provinceId": "34"
        },
        {
            "provinceName": "BANTEN",
            "provinceId": "33"
        },
        {
            "provinceName": "BENGKULU",
            "provinceId": "8"
        },
        {
            "provinceName": "DAERAH ISTIMEWA YOGYAKARTA",
            "provinceId": "12"
        },
        {
            "provinceName": "DKI JAKARTA",
            "provinceId": "9"
        },
        {
            "provinceName": "TIMOR TIMUR",
            "provinceId": "27"
        }
    ]
}
```

### Get List City by Province

##### Features
  - get all City by Province

##### Endpoint
GET
```sh
/rest/v1/getCity/{province id}
```

#### URL Params Required:
##### -Header
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|token| [text] | Y | | |
|clienId|[text] | Y | |

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "/rest/v1/getCity/10",
    headers: {
        "token": "5D89006A21776A45E050A8C04E0A33D8",
        "clienId":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    dataType: "json",
    type : "GET",
    success : function(response) {
      console.log(response);
    }
  });
```

##### Sample response:
success
```sh
{
    "cityList": [
        {
            "provinceId": "10",
            "cityId": "299",
            "cityName": "BANDUNG"
        },
        {
            "provinceId": "10",
            "cityId": "692",
            "cityName": "BANDUNG BARAT"
        },
        {
            "provinceId": "10",
            "cityId": "6",
            "cityName": "BEKASI"
        },
        {
            "provinceId": "10",
            "cityId": "8",
            "cityName": "BOGOR"
        },
        {
            "provinceId": "10",
            "cityId": "303",
            "cityName": "CIAMIS"
        }
    ]
}
```
