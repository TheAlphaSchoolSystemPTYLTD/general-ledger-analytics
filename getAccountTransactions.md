**getAccountTransactions**
----
  Returns an array of structured Account Transaction data in JSON format.
  
* **Version History:**

  TASS v52.5 - Method Added

* **Version:**

  3

* **Permission:**

  General Ledger > Ledger Details Report

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `year [string]` -  Year Number
   
   **Optional:**

   none

   **Conditional:**

   `period [string]` -  Period Nuumber, must be supplied if acct_code is not.

   `acct_code [string]` -  Account Code, must be supplied if period is not.

* **Success Response:**

    ```javascript
      {
          "transactions":[
              {
                  "year":2018,
                  "details":[
                      {
                          "date":"2018-07-03 00:00:00.0",
                          "credit":37.65,
                          "debit":0,
                          "journal_code":"CBJ",
                          "description":"Funds Transferred",
                          "source":"BANK TFR",
                          "reference_number":0,
                          "Analysis":"",
                          "supplier":"",
                          "journal_number":4637
                      }
                  ],
                  "period":7,
                  "acct_code":"00-6120-00-00",
                  "acct_desc":"ANZ Bank"
              }
          ],
          "token":{
              "year":2018,
              "period":7,
              "timestamp":"{ts '2020-03-02 11:20:15'}",
              "acct_code":"00-6120-00-00"
          }
      }
    ```

* **Error Response:**

    `year` not supplied
    ```javascript
    __invalid: {
      "year": "field is required"
    }
    ```

    `period` and `acct_code` not supplied
    ```javascript
    __invalid: {
      "condition": "period or acct_code must be specified."
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    {
      "year":"2018",
      "acct_code":"00-6120-00-00",
      "period":"7"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getAccountTransactions&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getAccountTransactions">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
