# icici-bank-apis-sandbox
Working of ICICI Bank API's

ICICI has open-sourced many APIs devide into mainly following sections

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
        URL:- `https://developerapi.icicibank.com:8443`
        Query:- `POST https://developerapi.icicibank.com:8443/api/v0/panValidation`
        Headers:- `{ pan: 'XXXXXXX' }`
        Response:- 
        `
        {
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
        `
    