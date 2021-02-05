**getReportingCode**
----
  Returns an array of structured Reporting Codes for one Account Code in JSON format.
  
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
          "description":"ANZ Bank",
          "acct_code":"00-6120-00-00",
          "reporting_codes":[
              {
                  "report_desc":"Reporting Code 1",
                  "report_code":1,
                  "label":"Code 1234",
                  "value":1234
              },
              {
                  "report_desc":"Financial Statements - Separation Codes",
                  "report_code":2,
                  "label":"Current",
                  "value":"03"
              },
              {
                  "report_desc":"Financial Statements - Grouping/Consolidation Codes",
                  "report_code":3,
                  "label":"Accumulated Funds & Reserves",
                  "value":"NNN"
              },
              {
                  "report_desc":"Key Financial Data",
                  "report_code":4,
                  "label":"Capital Expenditure",
                  "value":60
              },
              {
                  "report_desc":"Trading Entities",
                  "report_code":5,
                  "label":"Book Shop",
                  "value":"010"
              },
              {
                  "report_desc":"Financial Statements - Additional Consolidation",
                  "report_code":6,
                  "label":"Deposits Held",
                  "value":"L10"
              },
              {
                  "report_desc":"Cash Flow Statement - Grouping Codes",
                  "report_code":7,
                  "label":"Cash Flows from Financing Activities",
                  "value":30
              },
              {
                  "report_desc":"Cash Flow Statement - Cash Inflow Codes",
                  "report_code":8,
                  "label":"Proceeds from long term borrowings",
                  "value":50
              },
              {
                  "report_desc":"Cash Flow Statement - Cash Outflow Codes",
                  "report_code":9,
                  "label":"",
                  "value":""
              }
          ],
          "__tassversion": "01.053.3.000",
          "token":{
              "timestamp":"{ts '2021-01-22 09:38:14'}",
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
    http://api.tasscloud.com.au/tassweb/api/?method=getReportingCode&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getReportingCode">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
