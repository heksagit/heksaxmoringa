# API Gateway Product Bulanan
PT Asuransi Heksa Insurance X Moringa API Gateway 
___________________________________________________________


### Submit aplication Data
#### URL & Params Required:
##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Submit Data aplication from **Heksa** to **Moringa** API
#

##### - Endpoint
```sh
http://heksaku.moringaku.com/bulanan/heksaku.php
```
#

##### - Method : POST
#

##### - Authorization Basic Auth

| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |

#
##### - Body Structure

| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ProductName| | [text] | Y |150 | |
|ProductPackageName| |[text] | Y |150 | |
|ProductType| |[number] | Y |  | 1 = Bulanan, 2 = Tahunan |
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
|| DOB |[date] | Y | | format dd/MM/yyyy|
|Bank| |[jsonObject] | Y | | |
|| BankName |[text] | Y | | |
|| BankBranch |[text] | Y | | |
|| BankAccountName |[text] | Y | | |
|| BankAccountNo |[text] | Y | | |
#

##### - Result Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|  |  |  |  |  |  |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/bulanan/heksaku.php",
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
            "ProductType":"1",
            "Premium":1500000.0,
            "SumInsured":84000000.0,
            "SPAJNo":"NCB013",
            "ReferenceCode":"Ref01",
            "TransactionCode":"031312313",
            "TransactionDate":"",
            "PolicyHolder": {
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
            "Insured": {
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
            "Beneficiary": {
              "FullName":"penerima1",
              "Relation":"Anak",
              "DOB":"02/07/2017"
            },
            "Bank": {
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
#

##### Sample response:
###### Success Response
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
    }
}
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data": {
    }
}
```
#
____________________________________________________________________
### Submit Payment Status
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Submit Status Payment From **Heksa** To **Moringa** API
#
##### - Endpoint
```sh
http://heksaku.moringaku.com/bulanan/heksaku2.php
```
#
##### - Method : POST
#

##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
|SPAJNo| |[text] | Y | 20 | |
|status| |[text] | Y |500 | Berhasil, Gagal|
#

##### - Result Structure
| Params |  | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| status |  | [Text] | Y | 4 |  |
| message |  | [Text] | Y | 100 |  |
| data |  | [jsonObject]  |  |  |  |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/bulanan/heksaku2.php",
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
#

##### Sample response:
###### Success Response
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
    }
}
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data": {
    }
}
```
#

____________________________________________________________________

### Request Data Informasi Referral
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Request Data Informasi Referral From **Moringa** API
#

##### - Endpoint

```sh
http://heksaku.moringaku.com/bulanan/heksaku3.php
```
#
##### - Method : POST
#

##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body 
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
#

##### - Result Structure
| Params |  | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| status |  | [Text] | Y | 4 |  |
| message |  | [Text] | Y | 100 |  |
| data |  | [jsonObject]  |  |  |  |
|  | FullName | [Text] |  | 150 |  |
|  | Phone | [Text] |  | 20 |  |
|  | Email | [Text] |  | 150 |  |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/bulanan/heksaku3.php",
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
#

##### - Sample response:
###### Success Response
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
      "FullName":"Jhone Djo",
      "Phone":"082342423423423",
      "Email":"082424342"
    }
}
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data": {
        "FullName":"",
        "Phone":"",
        "Email":""
    }
}
```
#

____________________________________________________________________
### Submit Payment Status Renewal
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Submit Status Renewal Payment From **Heksa** To **Moringa** API
#
##### - Endpoint
```sh
http://heksaku.moringaku.com/bulanan/heksaku4.php
```
#
##### - Method : POST
#

##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
|SPAJNo| |[text] | Y | 20 | |
|PolicyNo| |[text] | Y | 20 | |
|RecurrPayments| |[ArrayJsonObject] | Y |  |  |
| | RecurrID | [Text] | Y | 50 |  |
| | RecurrDate | [date] | Y | | format dd/MM/yyyy|
| | PaymentType | [Text] | Y | 50 | 1 = Credit Card, 2 = VA |
| | Month | [number] | Y |  |  |
| | Year | [number] | Y |  |  |
| | Amount | [number] | Y |  |  |
| | Status | [Text] | Y |  | Berhasil, Gagal |

#

##### - Result Structure
| Params |  | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| status |  | [Text] | Y | 4 |  |
| message |  | [Text] | Y | 100 |  |
| data |  | [jsonObject]  |  |  |  |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/bulanan/heksaku4.php",
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
            "PolicyNo": "011233144",
            "RecurrPayments":[{
                    "RecurrID":"90AFECAF-3367-4F5E-B381-AEDC0A18E640",
                    "RecurrDate":"22/03/2019",
                    "PaymentType":"2",
                    "Month":"2",
                    "Year":"2019",
                    "Amount":"500000",
                    "Status":"Berhasil"
                }, {
                    "RecurrID":"D9ECF1A6-7AA4-4A9C-B148-48504E663C32",
                    "RecurrDate":"22/03/2019",
                    "PaymentType":"2",
                    "Month":"3",
                    "Year":"2019",
                    "Amount":"500000",
                    "Status":"Berhasil"
                }
            ]
    },
    success : function(response) {
      console.log(response);
    }
  });
```
#

##### Sample response:
###### Success Response
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
    }
}
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data": {
    }
}
```
#
____________________________________________________________________

____________________________________________________________________
### Submit Repayment Page URL
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Submit Repayment Page URL From **Heksa** To **Moringa** API
  - Kirim URL untuk pembayaran ulang apabila tidak ada transaksi selama 1 jam / terjadi error pada doku
#
##### - Endpoint
```sh
http://heksaku.moringaku.com/bulanan/heksaku5.php
```
#
##### - Method : POST
#

##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|ReferenceCode| |[text] | Y | 20 | |
|TransactionCode| |[text] | Y | 20 | |
|URL| |[text] | Y | 250 | |

#

##### - Result Structure
| Params |  | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
| status |  | [Text] | Y | 4 |  |
| message |  | [Text] | Y | 100 |  |
| data |  | [jsonObject]  |  |  |  |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "http://heksaku.moringaku.com/bulanan/heksaku5.php",
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
            "URL":"https://heksainsurance.co.id/heksaecommerce/beli/repayment?trxid=Trx002&refid=Ref001"
    },
    success : function(response) {
      console.log(response);
    }
  });
```
#

##### Sample response:
###### Success Response
```sh
{
    "status": 200,
    "message": "Success",
    "data": {
    }
}
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data": {
    }
}
```
#
____________________________________________________________________


### Get Daily Moringa Data By Date
#### URL & Params Required:

##### - Features
  - Sender : **Moringa**
  - Target API : **Heksa**
  - Get All Transaction in 1 day
#

##### - Endpoint

```sh
https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByDate?date=<dd/MM/yyyy>
```
#


##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|  |  |  |  |  |  |
#

##### - Result Structure
| Params |  | Data Type | Mandatory | Length | Description |
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
||| DOB |[date] | Y | | format dd/MM/yyyy|
||Bank| |[jsonObject] | Y | | |
||| BankName |[text] | Y | | |
||| BankBranch |[text] | Y | | |
||| BankAccountName |[text] | Y | | |
||| BankAccountNo |[text] | Y | | |
#

##### - Sample Call:
###### JQuery Ajax Call 
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
#

##### - Sample response:
###### Success Response
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
                    "Phone": "08555555555",
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
                    "Phone": "0855555555555",
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
                    "BankAccountName": "xxxxxxxxxxxx",
                    "BankAccountNo": "04242323434324"
                }
            }
    },
```
###### Failed Response
```sh
{
    "StatusCode": "500",
    "StatusMessage": "There is an error in system",
    "Value" : null
}
```
#
____________________________________________________________________

### Get Daily Moringa Data By TrxID
#### URL & Params Required:

##### - Features
  - Sender : **Moringa**
  - Target API : **Heksa**
  - Get All Transaction by TrxID
#

##### - Endpoint

```sh
https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByTrxID?trxid=testtingID1245
```
#

##### - Method : POST
#

##### - Authorization Basic Auth
| Params | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|
|username| [text] | Y | | |
|password|[text] | Y | | |
#

##### - Body Structure
| Params | | Data Type | Mandatory | Length | Description |
|--|--|--|--|--|--|
|  |  |  |  |  |  |
#

##### - Result Structure
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
||| DOB |[date] | Y | | format dd/MM/yyyy|
||Bank| |[jsonObject] | Y | | |
||| BankName |[text] | Y | | |
||| BankBranch |[text] | Y | | |
||| BankAccountName |[text] | Y | | |
||| BankAccountNo |[text] | Y | | |
#

##### - Sample Call:
###### JQuery Ajax Call 
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
#

##### - Sample response:
###### Success Response
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
                    "Phone": "08555555555",
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
                    "Email": "xxxx@outlook.com",
                    "Phone": "08555555555",
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
                    "BankAccountName": "xxxxxxxxxxx",
                    "BankAccountNo": "04242323434324"
                }
            }
    },
```

###### Failed Response
```sh
{
    "StatusCode": "500",
    "StatusMessage": "There is an error in system",
    "Value" : null
}
```
#
____________________________________________________________________
