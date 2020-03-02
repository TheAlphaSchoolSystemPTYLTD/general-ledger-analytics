**getAccountBalances**
----
  Returns an array of structured account balances details in JSON format.
  
* **Version History:**

  TASS v52.5 - Method Added

* **Version:**

  3

* **Permission:**

  General Ledger > Accounts

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `year [string]` - Year Number.

   `period [string]` - Period Number.
   
   **Optional:**

   none

   **Conditional:**
 
   none

* **Success Response:**

    ```javascript
      {
          "token":{
              "year":2019,
              "period":7,
              "timestamp":"{ts '2020-03-02 15:36:25'}"
          },
          "account_blances":[
              {
                  "budg4_amt":0,
                  "budg5_amt":0,
                  "ytd_budg4_amt":0,
                  "stats_qty":0,
                  "def_tax_code":"EX",
                  "type_ind":"A",
                  "budg1_amt":0,
                  "year":2019,
                  "budg6_amt":0,
                  "description":"ANZ Bank",
                  "open_amt":0,
                  "acct_code":"00-6120-00-00",
                  "group_code":"",
                  "ytd_budg3_amt":0,
                  "budg2_amt":0,
                  "ytd_budg1_amt":0,
                  "debit_amt":0,
                  "pre_close_amt":0,
                  "ytd_budg6_amt":0,
                  "close_amt":0,
                  "ytd_budg2_amt":0,
                  "budg3_amt":0,
                  "ytd_budg5_amt":0,
                  "period":7,
                  "credit_amt":0
              }
          ]
      }
    ```

* **Error Response:**

    `year` not supplied
    ```javascript
    __invalid: {
      "year": "field is required"
    }
    ```

    `period` not supplied
    ```javascript
    __invalid: {
      "period": "field is required"
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    {
      "year":"2019",
      "period":"2"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getAccountBalances&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getAccountBalances">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
