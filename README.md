# __BankApp__
### __Asp.Net Core 7 (.NET 7) | True Ultimate Guide__

<br>

### __Requirement:__
Imagine a banking application. Create an Asp.Net Core Web Application that serves bank account details based on the request path.

<br>

Consider the following hard-coded bank account details:

accountNumber = 1001, accountHolderName = "Example Name", currentBalance = 5000

You can store these details as an anonymous object. Eg: new { property1 = value, property2 = value }

<br>

### __Example #1:__

If you receive a HTTP GET request at path "/" (default route), it has to return welcome message with status code HTTP 200.

Request Url: /

Request Method: GET

Response Status Code: 200

Response body (output):

Welcome to the Best Bank

<br>

### __Example #2:__

If you receive a HTTP GET request at path "/account-details", it has to return all the details of bank account as Json format as response with status code HTTP 200.

Request Url: /account-details

Request Method: GET

Response Status Code: 200

Response body (output):

```
{

    "accountNumber": 1001,

    "accountHolderName": "Example Name",

    "currentBalance": 5000

}
```
![2022-10-26_19-54-22-155ece174ce805f5092cf57ed0e5f941](https://user-images.githubusercontent.com/60389872/203997054-703e7a96-ad81-496c-8716-d60801ca7007.png)


<br>

### __Example #3:__

If you receive a HTTP GET request at path "/account-statement", it has to return a dummy PDF file (assumed as bank statement) as response with status code HTTP 200.

Request Url: /account-statement

Request Method: GET

Response Status Code: 200

Response body (output):

[some dummy PDF file]

<br>

### __Example #4:__

If you receive a HTTP GET request at path "/get-current-balance/{accountNumber}", it has to return the corresponding current balance value as response with status code HTTP 200.

The "accountNumber" should be an int value and should be equal to "1001".

Request Url: /get-current-balance/1001

Request Method: GET

Response Status Code: 200

Response body (output):

5000

![2022-10-26_19-54-23-ae17e776265e1841ab4b9bea302a4f03](https://user-images.githubusercontent.com/60389872/203997102-2f651200-f8be-4613-9484-14e33b54da1a.png)

<br>

### __Example #5:__

If you receive a HTTP GET request at path "/get-current-balance/", if the "accountNumber" is not supplied, it should return HTTP 404 response.

Request Url: /get-current-balance

Request Method: GET

Response Status Code: 404

Response body (output):

Account Number should be supplied

<br>

### __Example #6:__

If you receive a HTTP GET request at path "/get-current-balance/{accountNumber}", if the "accountNumber" is not equal to '1001', it should return HTTP 400 response.

Request Url: /get-current-balance/10

Request Method: GET

Response Status Code: 400

Response body (output):

Account Number should be 1001

![2022-10-26_19-54-23-8f0d2b1ae5d6d40c9f363c435159214d](https://user-images.githubusercontent.com/60389872/203997183-c484746e-5b15-4bb6-b4f1-626ddbf89f2b.png)

<br>

### __Route Constraints:__

The "accountNumber" parameter should be an int value

<br>

### __Instructions:__

- Create controller(s) with attribute routing.

- Use essential route parameters and route constraints.

- Use parameter validation when necessary.

- Return ContentResult, JsonResult, FileResult and other status code results when necessary.

- Return the appropriate HTTP response status code, based on above examples.
