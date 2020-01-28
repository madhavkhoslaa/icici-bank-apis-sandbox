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

1. 

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

2. 

Here is the example from `Payments` functionality.  

        Main Class:- Payments
        Used For:- Pay To Virtual Address UPI 2.0
        Description:- This common API is used to support to initiate a pay request to virtual address and global recipients (IFSC + Account no / Mobile + MMD / Aadhaar + IIN).
        URL:- https://developerapi.icicibank.com:8443
        Query:- https://developerapi.icicibank.com:8443/api/v0/upi2/PayToVirtualAddress
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

3.

Example of internet banking fund transfer for business.
    
        Main Class:- Business Banking
        Used For:- P2P - Person to Person Fund Transfer
        Description:- Enables funds transfer from remitter BC account to beneficiary account using MMID and Mobile Number.
        URL:- https://developerapi.icicibank.com:8443
        Query:- POST https://developerapi.icicibank.com:8443/api/v0/personToPersonFundTransfer
        Headers:- {
                    "BeneMobileNumber": "9800000001",
                    "BeneMMId": "9229154",
                    "Amount": "1",
                    "TranReferenceNumber": "123132128834",
                    "PaymentRef": "FTTransferP2P",
                    "RemName": "RenName",
                    "RemMobile": "9860001122",
                    "RetailerCode": "rcode",
                    "PassCode": "123456",
                    "TransactionDate": "20150707171319"
                    }
        Response:- {
                    "ImpsResponse": 
                    {
                        "Response": "description",
                        "BankRRN": "ICICI's Unique transaction Ref number",
                        "TranRefNo": "Transaction Ref No Sent By BC",
                        "ActCode": "responseCode",
                        "BeneName": "Beneficiary Name" 
                    } 
                    }

4. 

Example of balance enquiry from Trade Service. 

        Main Class:- Trade Service
        Used For:-Outward Remittance Balance Inquiry
        Description:- Partner initiate Account Balance service to know the actual balance in the account of the partner
        URL:- https://developerapi.icicibank.com:8443
        Query:- https://developerapi.icicibank.com:8443/api/v1/RemittanceBalanceInquiry
        Headers:- 
                <?xml version="1.0" encoding="UTF8"?>
                <xml>
	                <VostroBalance>
		                <CorrespondentId> xxxxxxxxxx </CorrespondentId>
		                <MessageType>AccountBalance</MessageType>
		
		                <VostroAccNumber> xxxxxxxxxx </VostroAccNumber>
	                </VostroBalance>
	                <Signature>
		
		                <SignatureValue>XXXXXXXX</SignatureValue>
		
	                </Signature>
	
                </xml>
        Response:- 
                <xml>
                    <MessageType>AccountBalance</MessageType>
                    <CorrespondentID> xxxxxxxxxx </CorrespondentID>
                    <ClientShortName>ICI</ClientShortName>
                    <VostroAccNo>xxxxxxxxxx</VostroAccNo>
                    <ErrorDescription />
                    <VostroBalanceAmt>2528024.29</VostroBalanceAmt>
                    <VostroCurrency>INR</VostroCurrency>
                    <ResponseDateTime>15-11-2018 11:35:38</ResponseDateTime>
                <xml>