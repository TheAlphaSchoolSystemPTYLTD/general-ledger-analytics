**getResponsibilities**
----
  Returns an array of structured Responsibilities data in JSON format.
  
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

   `acct_code [string]` -  Account Code
   
   **Optional:**
 
   none

   **Conditional:**
 
   none

* **Success Response:**

    ```javascript
      {
          "responsibilities":[
              {
                  "initials":"A",
                  "user_code":"AJ",
                  "limit_amount":500,
                  "surname":"Johnstone",
                  "salutation":"Mr",
                  "responsibility_level":3,
                  "preferred_name":"Alanx",
                  "user_type":"T",
                  "email":"peter.pumpkin@tassweb.com.au",
                  "given_names":"Alan Pierre"
              }
          ],
          "token":{
              "timestamp":"{ts '2020-03-02 13:57:32'}",
              "acct_code":"00-6120-00-00"
          }
      }
    ```

* **Error Response:**

    `acct_code` not supplied
    ```javascript
    __invalid: {
      "acct_code": "field is required"
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    {
      "acct_code":"00-6120-00-00"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getResponsibilities&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getResponsibilities">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
