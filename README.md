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
|SPAJNo| |[text] | Y | 20 | |
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
        "type": "Basic Auth",
        "username": "5D89006A21776A45E050A8C04E0A33D8",
        "password":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    headers: {
        "Authorization": "5D89006A21776A45E050A8C04E0A33D8",
    }
    dataType: "json",
    type : "POST",
    data: {
            "ProductName":"Asuransi Heksa Proteksi Plus",
            "ProductPackageName":"Silver",
            "Premium":1500000.0,
            "SumInsured":84000000.0,
            "SPAJNo":"NCB013",
            "ReferenceCode":"Ref01",
            "TransactionCode":"031312313",
            "TransactionDate":"",
            "PolicyHolder":
              {
                "FullName":"Jhone Doe",
                "Email":"jhone@outlook.com",
                "Phone":"085623421112",
                "KTPNo":"asdasd",
                "DOB":"01/08/1990",
                "Address":"asdasd",
                "Sex":"L",
                "ProvinceName":"Jawa Barat",
                "CityName":"Cirebon"
              },
            "Insured":
              {
                "FullName":"Jhone Doe",
                "Email":"jhone@outlook.com",
                "Phone":"085623421112",
                "KTPNo":"asdasd",
                "DOB":"01/08/1990",
                "Address":"asdasd",
                "Sex":"L",
                "ProvinceName":"Jawa Barat",
                "CityName":"Cirebon"
              },
            "Beneficiary":
            {
             "FullName":"penerima1",
             "Relation":"Anak",
             "Bob":"02/07/2017"
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
|SPAJNo| |[text] | Y | 20 | |
|status| |[text] | Y |500 | Berhasil, Gagal|

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/my/heksaku2.php",
    authorization: {
        "type": "Basic Auth",
        "username": "5D89006A21776A45E050A8C04E0A33D8",
        "password":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    headers: {
        "Authorization": "5D89006A21776A45E050A8C04E0A33D8",
    }
    dataType: "json",
    type : "POST",
    data: {
            "ReferenceCode":"Ref001",
            "TransactionCode":"Trx002",
            "SPAJNo":"NCB001",
            "status": "Success",
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


##### -Body
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/my/heksaku2.php",
    authorization: {
        "type": "Basic Auth",
        "username": "5D89006A21776A45E050A8C04E0A33D8",
        "password":"56c217cd-0bea-4f64-8ae2-2db0a71fea35"
    }
    headers: {
        "Authorization": "5D89006A21776A45E050A8C04E0A33D8",
    }
    dataType: "json",
    type : "POST",
    data: {
            "ReferenceCode":"Ref001",
            "TransactionCode":"Trx002",
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
      "FullName":"Jhone Djo",
      "Phone":"082342423423423"
      "Email":""082424342"
      
    }
}
```
