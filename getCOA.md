**getCOA**
----
  Returns an array of structured General Ledger Account data in JSON format.
  
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

   `date [date dd/mm/yyyy]`
   
   **Optional:**

   `start_num [integer]` - `start_num` required if `flex_code` supplied

   `flex_code [string]` - `flex_code` required if `start_num` supplied

   **Conditional:**
 
   none

* **Success Response:**

    ```javascript
      {
          "accounts":{
              "1":{
                  "end_year_num":2100,
                  "budget1_title":"Board Approved",
                  "desc_text":"Gross Tuition Fees",
                  "start_period_num":1,
                  "budget2_title":"Revised",
                  "end_period_num":12,
                  "budget6_title":"Weekly",
                  "budget4_title":"Quarter Review",
                  "def_tax_code":"EX",
                  "type_ind":"I",
                  "start_year_num":1992,
                  "budget3_title":"Half Year Reviewed",
                  "analy_prompt_text":"",
                  "budget5_title":"Monthly Review",
                  "acct_code":"02-0110-00-00",
                  "group_code":"T-RI010"
              },
              "2":{
                  "end_year_num":2100,
                  "budget1_title":"Board Approved",
                  "desc_text":"Grant Income",
                  "start_period_num":1,
                  "budget2_title":"Revised",
                  "end_period_num":12,
                  "budget6_title":"Weekly",
                  "budget4_title":"Quarter Review",
                  "def_tax_code":"TS",
                  "type_ind":"I",
                  "start_year_num":1992,
                  "budget3_title":"Half Year Reviewed",
                  "analy_prompt_text":"",
                  "budget5_title":"Monthly Review",
                  "acct_code":"02-0112-00-00",
                  "group_code":"T-RI010"
              }
          },
          "token":{
              "date":"2018-10-04",
              "flex_code":"02",
              "year":2018,
              "timestamp":"{ts '2020-03-02 15:17:29'}",
              "start_num":1
          }
      }
    ```

* **Error Response:**

    `currentstatus` not supplied
    ```javascript
    __invalid: {
      "currentstatus": "field is required"
    }
    ```

    `currentstatus` must be 'current' or 'future' or 'past' or 'noncurrent'
    ```javascript
    __invalid: {
      "currentstatus": "Current Status must be 'current' or 'future' or 'past' or 'noncurrent'."
    }
    ```

    `includephoto` not a valid boolean
    ```javascript
    __invalid: {
      "includephoto": "Value is not a valid boolean."
    }
    ```

    `thumbnail` not a valid boolean
    ```javascript
    __invalid: {
      "thumbnail": "Value is not a valid boolean."
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    { 
      "currentstatus":"current",
      "includephoto":"true",
      "thumbnail":"true"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getCOA&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getCOA">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
