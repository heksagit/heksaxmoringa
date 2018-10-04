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
|| NPWP |[text] | Y | | |
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
|Bank| |[jsonObject] | Y | | |
|| BankName |[text] | Y | | |
|| BankBranch |[text] | Y | | |
|| BankAccountName |[text] | Y | | |
|| BankAccountNo |[text] | Y | | |

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
                "CityName":"Cirebon",
                "NPWP":"023324234234234234"
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
            },
            "Bank":
            {
             "BankName":"Mandiri",
             "BankBranch":"kuningan",
             "BankAccountName":"jhon doe",
             "BankAccountNo":"034234234234234"
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
### Get Daily Moringa Data By Date

##### Features
  - Get All Transaction in 1 day

##### Endpoint
POST
```sh
https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByDate?date=<dd/MM/yyyy>
```
#### URL Params Required:
##### -Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |

##### -Result 
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|StatusCode|| [text] | Y |4 | 00 = success, 50 = error |
|StatusMessage|| [text] | Y |100 | API Status success, error |
|Value| |[jsonObject] | Y | | | 
||ProductName| | [text] | Y |150 | |
||ProductPackageName| |[text] | Y |150 | |
||Premium| |[number]| Y | | |
||SumInsured| |[number]| Y | | |
||SPAJNo| |[text] | Y | 20 | |
||ReferenceCode| |[text] | Y | 20 | |
||TransactionCode| |[text] | Y | 20 | |
||TransactionDate| |[date] | Y | | format dd/MM/yyyy |
||PolicyHolder| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 250 | |
||| Email |[text] | Y | 50 | |
||| Phone |[text] | Y | | |
||| KTPNo |[text] | Y | 16 | |
||| DOB |[date] | Y | | format dd/MM/yyyy|
||| Address |[text] | Y | 200 | |
||| Sex |[text] | Y | | e.x pria, wanita |
||| ProvinceName |[text] | Y | |  |
||| CityName |[text] | Y | | |
||| NPWP |[text] | Y | | |
||Insured| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 250 | |
||| Email |[text] | Y | 50 | |
||| Phone |[text] | Y | | |
||| KTPNo |[text] | Y | 16 | |
||| DOB |[date] | Y | | format dd/MM/yyyy|
||| Address |[text] | Y | 200 | |
||| Sex |[text] | Y | | e.x pria, wanita |
||| ProvinceName |[text] | Y | |  |
||| CityName |[text] | Y | | |
||Beneficiary| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 50 | |
||| Relation |[text] | Y | |e.x  istri, suami, anak, ayah, ibu, kakak, adik, orang tua|
||| Bob |[date] | Y | | format dd/MM/yyyy|
||Bank| |[jsonObject] | Y | | |
||| BankName |[text] | Y | | |
||| BankBranch |[text] | Y | | |
||| BankAccountName |[text] | Y | | |
||| BankAccountNo |[text] | Y | | |

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByDate?date=03/10/2018",
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
    success : function(response) {
      console.log(response);
    }
  });
```

success
```sh
{
    "StatusCode": "00",
    "StatusMessage": "Success",
    "Value": {
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "Premium": 1500000,
                "SumInsured": 65000000,
                "ReferenceCode": "moringaku",
                "SPAJNo": "NCB000001071",
                "TransactionCode": "testtingID1245",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PolicyHolder": {
                    "FullName": "Test DOKU",
                    "Email": "test@gmail.com",
                    "Phone": "0215150555",
                    "KTPNo": "3201257300498888",
                    "DOB": "01/10/1987",
                    "Address": "Jl. Kebon Jeruk",
                    "Sex": "P",
                    "ProvinceName": "DKI Jakarta",
                    "CityName": "Kota Jakarta Barat",
                    "NPWP": "01020304050607"
                },
                "Insured": {
                    "FullName": "Test DOKU",
                    "Email": "test@gmail.com",
                    "Phone": "0215150555",
                    "KTPNo": "3201257300498888",
                    "DOB": "01/10/1987",
                    "Address": "Jl. Kebon Jeruk",
                    "Sex": "P",
                    "ProvinceName": "DKI Jakarta",
                    "CityName": "Kota Jakarta Barat"
                },
                "Beneficiary": null,
                "Bank": {
                    "BankName": "BCA",
                    "BankBranch": "Jakarta",
                    "BankAccountName": "Test",
                    "BankAccountNo": "123456789"
                }
            },
            {
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "Premium": 1500000,
                "SumInsured": 85000000,
                "ReferenceCode": "ncb000001011",
                "SPAJNo": "NCB000001072",
                "TransactionCode": "153854380724677",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PolicyHolder": {
                    "FullName": "testing production 1003",
                    "Email": "xxxxx@outlook.com",
                    "Phone": "085295962498",
                    "KTPNo": "0324823482382823",
                    "DOB": "06/10/2000",
                    "Address": "asdasd asdasd",
                    "Sex": "L",
                    "ProvinceName": "Nanggroe Aceh Darussalam (NAD)",
                    "CityName": "Kabupaten Aceh Barat",
                    "NPWP": ""
                },
                "Insured": {
                    "FullName": "testing production 1003",
                    "Email": "ibnu.nugroho@outlook.com",
                    "Phone": "085295962498",
                    "KTPNo": "0324823482382823",
                    "DOB": "06/10/2000",
                    "Address": "asdasd asdasd",
                    "Sex": "L",
                    "ProvinceName": "Nanggroe Aceh Darussalam (NAD)",
                    "CityName": "Kabupaten Aceh Barat"
                },
                "Beneficiary": null,
                "Bank": {
                    "BankName": "Mandiri",
                    "BankBranch": "Cirebon",
                    "BankAccountName": "ibnu nugroho",
                    "BankAccountNo": "04242323434324"
                }
            }
    },
```

### Get Daily Moringa Data By TrxID

##### Features
  - Get All Transaction by TrxID

##### Endpoint
POST
```sh
https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByTrxID?trxid=testtingID1245
```
#### URL Params Required:
##### -Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |

##### -Result 
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|StatusCode|| [text] | Y |4 | 00 = success, 50 = error |
|StatusMessage|| [text] | Y |100 | API Status success, error |
|Value| |[jsonObject] | Y | | | 
||ProductName| | [text] | Y |150 | |
||ProductPackageName| |[text] | Y |150 | |
||Premium| |[number]| Y | | |
||SumInsured| |[number]| Y | | |
||SPAJNo| |[text] | Y | 20 | |
||ReferenceCode| |[text] | Y | 20 | |
||TransactionCode| |[text] | Y | 20 | |
||TransactionDate| |[date] | Y | | format dd/MM/yyyy |
||PolicyHolder| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 250 | |
||| Email |[text] | Y | 50 | |
||| Phone |[text] | Y | | |
||| KTPNo |[text] | Y | 16 | |
||| DOB |[date] | Y | | format dd/MM/yyyy|
||| Address |[text] | Y | 200 | |
||| Sex |[text] | Y | | e.x pria, wanita |
||| ProvinceName |[text] | Y | |  |
||| CityName |[text] | Y | | |
||| NPWP |[text] | Y | | |
||Insured| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 250 | |
||| Email |[text] | Y | 50 | |
||| Phone |[text] | Y | | |
||| KTPNo |[text] | Y | 16 | |
||| DOB |[date] | Y | | format dd/MM/yyyy|
||| Address |[text] | Y | 200 | |
||| Sex |[text] | Y | | e.x pria, wanita |
||| ProvinceName |[text] | Y | |  |
||| CityName |[text] | Y | | |
||Beneficiary| |[jsonObject] | Y | | |
||| FullName |[text] | Y | 50 | |
||| Relation |[text] | Y | |e.x  istri, suami, anak, ayah, ibu, kakak, adik, orang tua|
||| Bob |[date] | Y | | format dd/MM/yyyy|
||Bank| |[jsonObject] | Y | | |
||| BankName |[text] | Y | | |
||| BankBranch |[text] | Y | | |
||| BankAccountName |[text] | Y | | |
||| BankAccountNo |[text] | Y | | |

##### Sample Call:
QJuery Ajax Call 
```sh
$.ajax({
    url: "https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByDate?date=03/10/2018",
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
    success : function(response) {
      console.log(response);
    }
  });
```

success
```sh
{
    "StatusCode": "00",
    "StatusMessage": "Success",
    "Value": {
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "Premium": 1500000,
                "SumInsured": 65000000,
                "ReferenceCode": "moringaku",
                "SPAJNo": "NCB000001071",
                "TransactionCode": "testtingID1245",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PolicyHolder": {
                    "FullName": "Test DOKU",
                    "Email": "test@gmail.com",
                    "Phone": "0215150555",
                    "KTPNo": "3201257300498888",
                    "DOB": "01/10/1987",
                    "Address": "Jl. Kebon Jeruk",
                    "Sex": "P",
                    "ProvinceName": "DKI Jakarta",
                    "CityName": "Kota Jakarta Barat",
                    "NPWP": "01020304050607"
                },
                "Insured": {
                    "FullName": "Test DOKU",
                    "Email": "test@gmail.com",
                    "Phone": "0215150555",
                    "KTPNo": "3201257300498888",
                    "DOB": "01/10/1987",
                    "Address": "Jl. Kebon Jeruk",
                    "Sex": "P",
                    "ProvinceName": "DKI Jakarta",
                    "CityName": "Kota Jakarta Barat"
                },
                "Beneficiary": null,
                "Bank": {
                    "BankName": "BCA",
                    "BankBranch": "Jakarta",
                    "BankAccountName": "Test",
                    "BankAccountNo": "123456789"
                }
            },
            {
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "Premium": 1500000,
                "SumInsured": 85000000,
                "ReferenceCode": "ncb000001011",
                "SPAJNo": "NCB000001072",
                "TransactionCode": "153854380724677",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PolicyHolder": {
                    "FullName": "testing production 1003",
                    "Email": "xxxxx@outlook.com",
                    "Phone": "085295962498",
                    "KTPNo": "0324823482382823",
                    "DOB": "06/10/2000",
                    "Address": "asdasd asdasd",
                    "Sex": "L",
                    "ProvinceName": "Nanggroe Aceh Darussalam (NAD)",
                    "CityName": "Kabupaten Aceh Barat",
                    "NPWP": ""
                },
                "Insured": {
                    "FullName": "testing production 1003",
                    "Email": "ibnu.nugroho@outlook.com",
                    "Phone": "085295962498",
                    "KTPNo": "0324823482382823",
                    "DOB": "06/10/2000",
                    "Address": "asdasd asdasd",
                    "Sex": "L",
                    "ProvinceName": "Nanggroe Aceh Darussalam (NAD)",
                    "CityName": "Kabupaten Aceh Barat"
                },
                "Beneficiary": null,
                "Bank": {
                    "BankName": "Mandiri",
                    "BankBranch": "Cirebon",
                    "BankAccountName": "ibnu nugroho",
                    "BankAccountNo": "04242323434324"
                }
            }
    },
```
