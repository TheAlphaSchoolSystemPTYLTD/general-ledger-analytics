**getReportingCodeSetup**
----
  Returns an array of structured Reporting Code Setup data in JSON format.
  
* **Version History:**

  TASS v52.5 - Method Added

* **Version:**

  3

* **Permission:**

  General Ledger > Reporting Codes (tab)

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**

   `includelookups [boolean]` -  Must be 'true' or 'false' for whether returning lookup details.
   
   **Optional:**

   none

   **Conditional:**
 
   none

* **Success Response:**

    ```javascript
      {
          "rpt1_code_desc":{
              "description":"Reporting Code 1",
              "lookups":[
                  {
                      "report_code":"01",
                      "report_description":"Income from Fees"
                  },
                  {
                      "report_code":"02",
                      "report_description":"State Govt Grants"
                  },
                  {
                      "report_code":"03",
                      "report_description":"Federal Govt Grants"
                  },
                  {
                      "report_code":"04",
                      "report_description":"Other Income"
                  }
              ],
              "ref_num":1
          },
          "token":{
              "includelookups":true,
              "timestamp":"{ts '2020-03-02 09:32:46'}"
          }
      }
    ```

* **Error Response:**

    `includelookups` not supplied
    ```javascript
    __invalid: {
      "includelookups": "field is required"
    }
    ```

    `includelookups` not a valid boolean
    ```javascript
    __invalid: {
      "includelookups": "Value is not a valid boolean."
    }
    ```
    
* **Sample Parameters:**

  ```javascript
    {
      "includelookups":"true"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getReportingCodeSetup&appcode=API22&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We1Gqx9%2Fzb%2BcbVFartivsDN%2FxGgAIIjtABAYfzYPqTCpLf3gb0nW3h%2FTrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getReportingCodeSetup">
       <input type="hidden" name="appcode" value="API22">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We1Gqx9/zb+cbVFartivsDN/xGgAIIjtABAYfzYPqTCpLf3gb0nW3h/TrPFLMhAdNcVvHD0Gz4FkRj5jRAD1aAGQ</textarea>
    </form>
  ```
