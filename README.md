# API Gateway Product
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
http://api.moringaku.com/partner/heksa/heksaku.php
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
|ReferenceCode| |[text] | Y | 20 | RefId from moringa |
|TransactionCode| |[text] | Y | 20 | TrxId from moringa |
|TransactionDate| |[date] | Y | | format dd/MM/yyyy |
|PaymentType| |[text] | Y | 20 | CC = Credit Card, VA = Virtual Account |
|PolicyHolder| |[jsonObject] | Y | | |
|| FullName |[text] | Y | 250 | |
|| Email |[text] | Y | 50 | |
|| Phone |[text] | Y | | |
|| KTPNo |[text] | Y | 16 | |
|| DOB |[date] | Y | | format dd/MM/yyyy|
|| Address |[text] | Y | 200 | |
|| Sex |[text] | Y | | e.x L = pria, P = wanita |
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
|| Sex |[text] | Y | | e.x L = pria, P = wanita |
|| ProvinceName |[text] | Y | |  |
|| CityName |[text] | Y | | |
|Beneficiary| |[ArrayjsonObject] | Y | | |
|| FullName |[text] | Y | 50 | |
|| Relation |[text] | Y | |e.x  istri, suami, anak, ayah, ibu, kakak, adik, orang tua|
|| DOB |[date] | Y | | format dd/MM/yyyy|
|| Sex |[text] | Y | | e.x L = pria, P = wanita|
|| Percentage |[number] | Y | | |
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
    url: "http://api.moringaku.com/partner/heksa/heksaku.php",
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
            "ProductType":"2",
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
            "Beneficiary": [{
			        "FullName": "Jony",
			        "Relation": "suami",
			        "DOB": "14/03/1987",
			        "Gender": "L",
			        "Percentage": 25
		        }, {
			        "FullName": "Marina",
			        "Relation": "anak",
			        "DOB": "14/03/2019",
			        "Sex": "P",
			        "Percentage": 25
		        }, {
			        "FullName": "Susi Menarika",
			        "Relation": "saudara kandung",
			        "DOB": "15/03/1989",
			        "Gender": "P",
			        "Percentage": 50
		        }
	        ],
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
http://api.moringaku.com/partner/heksa/heksaku2.php
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
|ReferenceCode| |[text] | Y | 20 | RefId from moringa |
|TransactionCode| |[text] | Y | 20 | TrxId from moringa |
|SPAJNo| |[text] | Y | 20 | |
|PolicyNo| |[text] | Y | 30 | |
|PolicySoftCopyLink| |[text] | Y | 500 | |
|Status| |[text] | Y |500 | BERHASIL, GAGAL|
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
    url: "http://api.moringaku.com/partner/heksa/heksaku2.php",
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
            "PolicyNo":"8190100001",
            "PolicySoftCopyLink":"https://heksainsurance.co.id/heksaecommerce/home/cetakpolis?polNo=8190100001",
            "Status": "BERHASIL",
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
http://api.moringaku.com/partner/heksa/heksaku3.php
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
    url: "http://api.moringaku.com/partner/heksa/heksaku3.php",
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
http://api.moringaku.com/partner/heksa/heksaku4.php
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
|ReferenceCode| |[text] | Y | 20 | refid from moringa |
|TransactionCode| |[text] | Y | 20 | trxid from moringa |
|SPAJNo| |[text] | Y | 20 | |
|PolicyNo| |[text] | Y | 20 | |
|ProductType| |[number] | Y | | 1 = Bulanan, 2 = Tahunan |
|ProductPackageName| |[text]| Y | | Bronze,Silver,Gold,Basic,Standard,Premium  |
|BillingPayments| |[ArrayJsonObject] | Y |  |  |
| | BillingCode | [Text] | Y | 50 |  |
| | PaymentDate | [date] | Y | | (tanggal pembayaran) format dd/MM/yyyy|
| | DueDate | [date] | Y | | (tanggal Jatuh tempo) format dd/MM/yyyy|
| | PaymentType | [Text] | Y | 50 | 1 = Credit Card, 2 = VA, 3 = OVO |
| | BillingOrder | [number] | Y |  |  |
| | BillingYearOrder | [number] | Y |  |  |
| | Amount | [number] | Y |  |  |
| | Status | [Text] | Y |  | BERHASIL, GAGAL |

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
    url: "http://api.moringaku.com/partner/heksa/heksaku4.php",
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
            "SPAJNo":"NCB19010009",
            "PolicyNo": "8190100003",
            "ProductType":"2"
            "ProductPackageName":"Silver"
            "BillingPayments":[{
                    "BillingCode":"190200000030",
                    "PaymentDate":"20/12/2019",
                    "DueDate":"05/01/2019",
                    "PaymentType":"1",
                    "BillOrder":"2",
                    "BillYearOrder":"2",
                    "Amount":"3000000",
                    "Status":"BERHASIL"
                }, {
                    "BillingCode":"190200000030",
                    "PaymentDate":"20/12/2019",
                    "DueDate":"05/01/2020",
                    "PaymentType":"1",
                    "BillOrder":"3",
                    "BillYearOrder":"3",
                    "Amount":"3000000",
                    "Status":"BERHASIL"
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
### Submit Virtual Account Page URL
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Submit Nomor Virtual Account From **Heksa** To **Moringa** API
  - Kirim Virtual Account ketika pilih Virtual Account Sebagai Jenis Pembayaran doku
#
##### - Endpoint
```sh
http://api.moringaku.com/partner/heksa/heksaku5.php
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
|NoVirtualAccount| |[text] | Y | 250 | |
|Process| |[text] | Y | 250 | NewBusiness, Renewal |
|DateProcess| | [Date] | Y | | format dd/MM/yyyy|

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
    url: "http://api.moringaku.com/partner/heksa/heksaku5.php",
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
            "NoVirtualAccount":"8856075900000106",
            "Process":"NewBusiness",
            "DateProcess":"02/25/2019"
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
### Submit Update Status Polis Page URL
#### URL & Params Required:

##### - Features
  - Sender : **Heksa**
  - Target API : **Moringa**
  - Update Status Polis From **Heksa** To **Moringa** API
  - Kirim Status Polis Ke Moringa dengan Status (Inforce,Surrender,Lapse)
#
##### - Endpoint
```sh
http://api.moringaku.com/partner/heksa/heksaku6.php
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
|PolicyNo| |[text] | Y | 30 | |
|Status| |[text] | Y | 50 | Inforce,Surrender,Lapse |

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
    url: "http://api.moringaku.com/partner/heksa/heksaku6.php",
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
            "PolicyNo":"8190100001",
            "Status":"Lapse"
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
|status|| [number] | Y | | 200 = success, 500 = error |
|message|| [text] | Y |100 | API Status success, error |
|data| |[jsonObject] | Y | | | 
||ProductName| | [text] | Y |150 | |
||ProductPackageName| |[text] | Y |150 | |
||ProductType| |[number] | Y |  | 1 = Bulanan, 2 = Tahunan |
||Premium| |[number]| Y | | |
||SumInsured| |[number]| Y | | |
||SPAJNo| |[text] | Y | 20 | |
||PolicyNo| |[text] | Y | 30 | |
||ReferenceCode| |[text] | Y | 20 | |
||TransactionCode| |[text] | Y | 20 | |
||TransactionDate| |[date] | Y | | format dd/MM/yyyy |
||PaymentType| |[text] | Y | 20 | CC = Credit Card, VA = Virtual Account, OVO = OVO |
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
||| Sex |[text] | Y | | e.x L = pria, P = wanita|
||| Percentage |[number] | Y | | |
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
    "status": 200,
    "message": "success",
    "data": [{
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "ProductType": "2",
                "Premium": "1500000",
                "SumInsured": "65000000",
                "ReferenceCode": "moringaku",
                "SPAJNo": "NCB000001071",
                "PolicyNo": "8100500001",
                "TransactionCode": "testtingID1245",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PaymentType": "CC",
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
                "Beneficiary": [{
			            "FullName": "Jony",
			            "Relation": "suami",
			            "DOB": "14/03/1987",
			            "Sex": "L",
			            "Percentage": 100
		            }
	            ],
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
                "Premium": "1500000",
                "SumInsured": "85000000",
                "ReferenceCode": "ncb000001011",
                "SPAJNo": "NCB000001072",
                "PolicyNo": "8100500002",
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
                "Beneficiary": [{
			            "FullName": "Jony",
			            "Relation": "suami",
			            "DOB": "14/03/1987",
			            "Sex": "L",
			            "Percentage": 25
		            }, {
			            "FullName": "Marina",
			            "Relation": "anak",
			            "DOB": "14/03/2019",
			            "Sex": "P",
			            "Percentage": 25
		            }, {
			            "FullName": "Susi Menarika",
			            "Relation": "saudara kandung",
			            "DOB": "15/03/1989",
			            "Sex": "P",
			            "Percentage": 50
		            }
	            ],
                "Bank": {
                    "BankName": "Mandiri",
                    "BankBranch": "Cirebon",
                    "BankAccountName": "xxxxxxxxxxxx",
                    "BankAccountNo": "04242323434324"
                }
            }
        ]
    },
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data" : null
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
|status|| [number] | Y | | 200 = success, 500 = error |
|message|| [text] | Y |100 | API Status success, error |
|data| |[jsonObject] | Y | | | 
||ProductName| | [text] | Y |150 | |
||ProductPackageName| |[text] | Y |150 | |
||ProductType| |[number] | Y |  | 1 = Bulanan, 2 = Tahunan |
||Premium| |[number]| Y | | |
||SumInsured| |[number]| Y | | |
||SPAJNo| |[text] | Y | 20 | |
||PolicyNo| |[text] | Y | 30 | |
||ReferenceCode| |[text] | Y | 20 | |
||TransactionCode| |[text] | Y | 20 | |
||TransactionDate| |[date] | Y | | format dd/MM/yyyy |
||PaymentType| |[text] | Y | 20 | CC = Credit Card, VA = Virtual Account |
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
||| Sex |[text] | Y | | e.x L = pria, P = wanita|
||| Percentage |[number] | Y | | |
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
    url: "https://heksainsurance.co.id/heksaecommerceapi/api/GetDataByTrxID?trxid=testtingID1245",
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
    "status": 200,
    "message": "success",
    "data": {
                "ProductName": "Heksa Proteksi Plus",
                "ProductPackageName": "Silver",
                "ProductType": "2",
                "Premium": "1500000",
                "SumInsured": "65000000",
                "SPAJNo": "NCB000001071",
                "PolicyNo": "8100500001",
                "ReferenceCode": "moringaku",
                "TransactionCode": "testtingID1245",
                "TransactionDate": "03/10/2018",
                "PaymentStatus": "GAGAL",
                "PaymentType": "VA",
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
                "Beneficiary": [{
			            "FullName": "Jony",
			            "Relation": "suami",
			            "DOB": "14/03/1987",
			            "Gender": "L",
			            "Percentage": 25
		            }, {
			            "FullName": "Marina",
			            "Relation": "anak",
			            "DOB": "14/03/2019",
			            "Sex": "P",
			            "Percentage": 25
		            }, {
			            "FullName": "Susi Menarika",
			            "Relation": "saudara kandung",
			            "DOB": "15/03/1989",
			            "Gender": "P",
			            "Percentage": 50
		            }
	            ],
                "Bank": {
                    "BankName": "BCA",
                    "BankBranch": "Jakarta",
                    "BankAccountName": "Test",
                    "BankAccountNo": "123456789"
                }
            }
    },
```

###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data" : null
}
```
#
____________________________________________________________________


### Get Daily Moringa Data Renewal By Date
#### URL & Params Required:

##### - Features
  - Sender : **Moringa**
  - Target API : **Heksa**
  - Get All Transaction Renewal in 1 day
#

##### - Endpoint

```sh
https://heksainsurance.co.id/heksaecommerceapi/api/GetDataRenewalByDate?date=<dd/MM/yyyy>
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
|status|| [number] | Y | | 200 = success, 500 = error |
|message|| [text] | Y |100 | API Status success, error |
|data| |[jsonObject] | Y | | | 
||ReferenceCode| | [text] | Y |20 | refid from moringa |
||TransactionCode| |[text] | Y |20 | trxid from moringa |
||SPAJNo| |[text] | Y | 20  | |
||PolicyNo| |[text]| Y | 30 | |
||ProductType| |[number]| Y | |  1 = Bulanan, 2 = Tahunan |
||ProductPackageName| |[text] | Y |  | Bronze,Silver,Gold,Basic,Standard,Premium  |
||BillingPayments| |[ArrayJsonObject] | Y | | |
||| BillingCode |[text] | Y | 50 | |
||| PaymentDate |[date] | Y | | (tanggal pembayaran) format dd/MM/yyyy |
||| DueDate |[date] | Y |  | (tanggal Jatuh tempo) format dd/MM/yyyy|
||| PaymentType |[text] | Y | 50 | 1 = Credit Card, 2 = VA, 3 = OVO |
||| BillingOrder |[number] | Y | |  |
||| BillingYearOrder |[number] | Y | | |
||| Amount |[number] | Y | | |
||| Status |[text] | Y | | BERHASIL, GAGAL |
#

##### - Sample Call:
###### JQuery Ajax Call 
```sh
$.ajax({
    url: "https://heksainsurance.co.id/heksaecommerceapi/api/GetDataRenewalByDate?date=03/10/2018",
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
    "status": 200,
    "message": "Success",
    "data": [
        {
            "ReferenceCode": "moringaku",
            "TransactionCode": "15580870319021431",
            "SPAJNo": "UNCB10050001",
            "PolicyNo": "8100500001",
            "ProductType": 1,
            "ProductPackageName": "Basic",
            "BillingPayments": [
                {
                    "BillingCode": "190500000179",
                    "PaymentDate": "17/05/2019",
                    "DueDate": "25/05/2019",
                    "PaymentType": "2",
                    "BillingOrder": 2,
                    "BillingYearOrder": 1,
                    "Amount": 150000,
                    "Status": "BERHASIL"
                }
            ]
        },{
            "ReferenceCode": "moringaku2",
            "TransactionCode": "15580870319021431",
            "SPAJNo": "UNCB10050002",
            "PolicyNo": "8100500002",
            "ProductType": 1,
            "ProductPackageName": "Basic",
            "BillingPayments": [
                {
                    "BillingCode": "190500000180",
                    "PaymentDate": "17/07/2019",
                    "DueDate": "27/06/2019",
                    "PaymentType": "2",
                    "BillingOrder": 2,
                    "BillingYearOrder": 1,
                    "Amount": 150000,
                    "Status": "BERHASIL"
                },{
                    "BillingCode": "190500000180",
                    "PaymentDate": "17/07/2019",
                    "DueDate": "27/07/2019",
                    "PaymentType": "2",
                    "BillingOrder": 3,
                    "BillingYearOrder": 1,
                    "Amount": 150000,
                    "Status": "BERHASIL"
                }
            ]
        }
    ]
    },
```
###### Failed Response
```sh
{
    "status": 500,
    "message": "There is an error in system",
    "data" : null
}
```
#
____________________________________________________________________
