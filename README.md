# icici-bank-apis-sandbox
Working of ICICI Bank API's

ICICI has open-sourced many APIs devided into mainly following sections

    1. Building Blocks
    2. Business Banking
    3. Loans and Cards
    4. Accounts and Deposits
    5. Payments
    6. Trade Service

Here are some examples of API calls with the actual response using the sandbox. 

        Main Class:- Building Blocks
        Used For:- Pan Validation
        Description:- This API is used to provide geographical details of user on successful PAN validation.
        URL:- https://developerapi.icicibank.com:8443
        Query:- POST https://developerapi.icicibank.com:8443/api/v0/panValidation
        Headers:- `{ pan: 'XXXXXXX' }`
        Response:- {
                    "status": 1,
                    "data": 
                    {
                        "Returncode": "1",
                        "PAN": "XXXXXXXXXX",
                        "PANStatus": "E",
                        "LastName": "Anderson",
                        "FirstName": "Neo ",
                        "MiddleName": "",
                        "PANtitle": "Shri",
                        "Lastupdatedate ": "29/03/2016",
                        "Filler1": "",
                        "Filler2": "",
                        "Filler3": "" 
                    },
                    "errorCode": 0 
                    }

Here is the example from `Payments` functionality.  

        Main Class:- Payments
        Used For:- Pay To Virtual Address UPI 2.0
        Description:- This common API is used to support to initiate a pay request to virtual address and global recipients (IFSC + Account no / Mobile + MMD / Aadhaar + IIN).
        URL:- https://developerapi.icicibank.com:8443
        QUERY:- https://developerapi.icicibank.com:8443/api/v0/upi2/PayToVirtualAddress
        Headers:- {"OTP": "NPCI%2C2015082%2C1.0%7$base64date$"
                    "AccountProvider": "5",
                    "MPIN": "NPCI%2C2015082%2C1.0%7C$base64data$",
                    "MobileNumber": "902890XXXX",
                    "carddigits": "5456",
                    "expirydate": "1117",
                    "deviceId": "8452165486XXXX",
                    "seqNumber": "ef1e92b4a01d4618a0eca5fdecc37ff23f3",
                    "channelcode": "ImoXXXX",
                    "AccountNumber": "8754215XXXX",
                    "VirtualAddress": "TEST@icici",
                    "name": "abc",
                    "defaultdebit": "D",
                    "defaultcredit": "D",
                    "actionflag": "R"
                    }
        Response:- {
                    "success": "true",
                    "response": "0",
                    "message": "Transaction Successful",
                    "BankRRN": "603415867949",
                    "UpiTranlogId": "592",
                    "UserProfile": "10",
                    "SeqNo": "ef1e92b4a01d4618a0eca5fdecc37ff23f3",
                    "MobileAppData": "SUCCESS" 
                    }