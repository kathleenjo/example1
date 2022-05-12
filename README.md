# testing
<br/><hr/><br/>

|   What's in the box   |   Product Features   |
|   -----   |   -----   |
| • IoT Developer Kit main board<br>• Protective case<br>• Battery <br>• Power adapter<br>• USB Charging Cable<br>• Quick Start Guide<br>• SIM with 500 MB of data<br>• Mobile and web apps that will assist in IoT Development<br>• Code snippets|The kit comes pre-bundled with connectivity and is sold exclusively through DevEdge.<br/>Specifications:<br>• 32-bit ARM Cortex M4 MCU<br>• LTE CAT-M Module <br>• 2.4GHz Wi-Fi<br>• BLE Bluetooth <br>• GNSS <br>• RGB LED <br>• White LED <br>• Temperature sensor <br>• Accelerometer<br>• Ambient Light Sensor<br>• Pressure Sensor<br>• Buzzer<br>• Button<br>• Li-ion Battery<br>• I2C Expansion Connector <br>• Type-C USB Connector  |


- Hello
- World
  1. Hi
  2. Bye

## JSON
```json
{
  "isConnected": 2,
  "errors": [],
  "messages": [],
  "dataUsage": {
    "renewDate": 1650917936982,
    "dataUsed": 86.2,
    "dataCap": 500
  },
  "deviceStatus": {
    "pluggedIn": false,
    "batteryLevel": 83,
    "deviceOnline": true,
    "cloudConnected": true,
    "cellularConnected": true,
    "wifiConnected": true,
    "bluetoothConnected": true
  },
  "accelerometer": {
    "x": 0,
    "y": 0,
    "z": -1
  },
  "cellSignalStrength": {
    "dbm": -73
  },
  "map": {},
  "temperature": {
    "temperatureCelsius": 21.1
  },
  "lastReport": 1650917936982
}
```

## YAML
```yaml
openapi: 3.0.1
info:
  title: Call Forwarding Verification
  description: >-
    The Identity business will involve sharing call fowarding attribute
    with Partners for the purpose of verifying the identity of end users and
    protecting them from fraud.
  x-data-sensitivity: External
  x-type-of-consumer: P
  
  x-breadth-of-consumption: FC
  contact:
    name: IFM API Team
    url: 'http://api.t-mobile.com'
    email: IFMProjectTeam@T-Mobile.com
  version: 2.0.0
servers:
  - url: 'https://dit01-pd.t-mobile.com/ifm/v1/call-forwarding-verification'
    description: NPE server endpoint
  - url: 'https://api.t-mobile.com//ifm/v1/call-forwarding-verification'
    description: PROD server endpoint
paths:
  /details:
    post:
      x-type-of-consumer: P
      x-breadth-of-consumption: FC
      tags:
        - Call Forwarding Verification
      summary: >-
        This operation is used to get call forwarding information based on MSISDN and
        Consent.
      description: >-
        Subscriber is generic service, user can call this service using below
        url: http://{hostname}/v1/call-forwarding-verification
      operationId: getCallForwardingDetails
      parameters:
        - name: Date
          in: header
          description: API be called timestamp passed by API Caller
          required: true
          schema:
            type: string
            format: date-time
          example: 'Mon, 05 Mar 2018 16:38:08 GMT'
        - name: interaction-id
          in: header
          description: >-
            This Id is going to represent a interactionid which is sent by
            partner
          schema:
            pattern: .*$
            type: string
          example: 072420174258356309
        - name: activity-id
          in: header
          description: Unique identifier of the request
          required: true
          schema:
            pattern: .*$
            type: string
          example: c34e7acd-384b-4c22-8b02-ba3963682508
        - name: service-transaction-id
          in: header
          description: >-
            This Id is going to represent a service transaction id which is sent
            by partner
          schema:
            pattern: .*$
            type: string
          example: f6cfc010-3ab6-1efd-d920-47c515a8b167
        - name: x-authorization
          in: header
          description: OAuth 2.0 access token
          schema:
            pattern: .*$
            type: string
          example: >-
            Bearer
            eyJraWQiOiI0Nzc1M2UzZi0zOGFjLTQ1ODQtZ1sfg1xYTE1Nzk5NWMiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiI5T1VJaTE1TUxVS01QMnVKMXdudUFOZFJJakRFUDNncyIsInJ0Ijoie1wic2VnbWVudGF0aW9uSWRcIjpcIlBPTEFSSVNcIn0iLCJkZWFsZXJDb2RlIjoiIiwiaXNzIjoiaHR0cHM6XC9cL3FhdDAxLmFwaS50LW1vYmlsZS5jb21cL29hdXRoMlwvdjQiLCJtYXN0ZXJEZWFsZXJDb2RlIjoiIiwiYXV0aFRpbWUiOiIxNTk1NTMyMDcxMjExIiwic3RvcmVJZCI6IiIsInVzbiI6IjIzZDc5MDZhLTgzNDktN2U5NC1lNWM1LTQwYzAwZWU1ZDJkZSIsImF1ZCI6IjlPVUlpMTVNTFVLTVAydUoxd251QU5kUklqREVQM2dzIiwic2VuZGVySWQiOiIiLCJuYmYiOjE1OTU1MzIwNzEsInNjb3BlIjoiIiwiYXBwbGljYXRpb25JZCI6IiIsImV4cCI6MTU5NTUzNTY3MSwiaWF0IjoxNTk1NTMyMDcxLCJjaGFubmVsSWQiOiIiLCJqdGkiOiI4ZGI4YTc2OC1jMjg0LTBkNWQtOTc3NS01YjUxNDA2NTEzOWQifQ.wbRq1BI35Y8Dp2ZklHCiSzAs6FxgDY5Obkny6Zodue34dshku5SQOKMevPQuhW1spKUBd551XuznmzpJ5-KqIqY70iNZztj1T_D34fs6yGrymH-97xQvwlGQY2bdLaz_NGAIbuMO98gNSeQjx5PP15J6mFH1W9IT8KwbYJFSwagH_2i1samDb2UV5_43uRMckbu0otn7EFDQFOWPmYqU4P3uN-kiF1NDocvgnVaC_JyJjcCY5-hzCm2_NmjfYwRqR1Xc8Hc82U9MH0vkVQSVYRn7DhVuyvUzwWa9MKPilHmtFJ97nRHSoEfYQNIuv5ml44yMKNRY7Mavf0itpxBwYg
        - name: x-auth-originator
          in: header
          description: ID Token
          schema:
            pattern: .*$
            type: string
          example: >-
            Bearer
            eyJraWQiOiI0Nzc1M2UzZi0zOGFjLTQ1ODQtZ1sfg1xYTE1Nzk5NWMiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiI5T1VJaTE1TUxVS01QMnVKMXdudUFOZFJJakRFUDNncyIsInJ0Ijoie1wic2VnbWVudGF0aW9uSWRcIjpcIlBPTEFSSVNcIn0iLCJkZWFsZXJDb2RlIjoiIiwiaXNzIjoiaHR0cHM6XC9cL3FhdDAxLmFwaS50LW1vYmlsZS5jb21cL29hdXRoMlwvdjQiLCJtYXN0ZXJEZWFsZXJDb2RlIjoiIiwiYXV0aFRpbWUiOiIxNTk1NTMyMDcxMjExIiwic3RvcmVJZCI6IiIsInVzbiI6IjIzZDc5MDZhLTgzNDktN2U5NC1lNWM1LTQwYzAwZWU1ZDJkZSIsImF1ZCI6IjlPVUlpMTVNTFVLTVAydUoxd251QU5kUklqREVQM2dzIiwic2VuZGVySWQiOiIiLCJuYmYiOjE1OTU1MzIwNzEsInNjb3BlIjoiIiwiYXBwbGljYXRpb25JZCI6IiIsImV4cCI6MTU5NTUzNTY3MSwiaWF0IjoxNTk1NTMyMDcxLCJjaGFubmVsSWQiOiIiLCJqdGkiOiI4ZGI4YTc2OC1jMjg0LTBkNWQtOTc3NS01YjUxNDA2NTEzOWQifQ.wbRq1BI35Y8Dp2ZklHCiSzAs6FxgDY5Obkny6Zodue34dshku5SQOKMevPQuhW1spKUBd551XuznmzpJ5-KqIqY70iNZztj1T_D34fs6yGrymH-97xQvwlGQY2bdLaz_NGAIbuMO98gNSeQjx5PP15J6mFH1W9IT8KwbYJFSwagH_2i1samDb2UV5_43uRMckbu0otn7EFDQFOWPmYqU4P3uN-kiF1NDocvgnVaC_JyJjcCY5-hzCm2_NmjfYwRqR1Xc8Hc82U9MH0vkVQSVYRn7DhVuyvUzwWa9MKPilHmtFJ97nRHSoEfYQNIuv5ml44yMKNRY7Mavf0itpxBwYg
      requestBody:
        description: call forwarding request
        content:
          '*/*':
            schema:
              $ref: '#/components/schemas/callForwardingRequest'
            example:
              callForwardingRequest:
                msisdn: '4049930243'
                consentMerchant: Bank of America
                consentTimestamp: '2019-05-21T13:34:31.536Z'
                consentType: onetime
        required: true
      responses:
        '200':
          description: Ok
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
            ETag:
              description: >-
                Entity Tag: the version of the resource, usually a hash of the
                representation
              schema:
                pattern: .*$
                type: string
          content:
            '*/*':
              schema:
                $ref: '#/components/schemas/CallForwardingResponseInfo'
              example:
                callForwardingResponse:
                  callForwarding: '0'
                  account:
                    customerType: '4'
                  doNotSellSetting: '0'
        '400':
          description: Bad Request
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '400'
                userMessage: Bad Request
                systemMessage: Bad Request
                detailLink: 'http://aaa.bbb.ccc/'
        '401':
          description: Unauthorized
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '401'
                userMessage: Invalid Access Token
                systemMessage: Invalid Access Token
                detailLink: 'http://aaa.bbb.ccc/'
        '403':
          description: Access Denied
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '403'
                userMessage: Access Denied
                systemMessage: Access Denied
                detailLink: 'http://aaa.bbb.ccc/'
        '404':
          description: Not Found
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '404'
                userMessage: Not Found
                systemMessage: Not Found
                detailLink: 'http://aaa.bbb.ccc/'
        '405':
          description: Method Not Allowed
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Allow:
              description: list of supported methods for URI
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[\S]*$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '405'
                userMessage: Method Not Allowed
                systemMessage: Method Not Allowed
                detailLink: 'http://aaa.bbb.ccc/'
        '409':
          description: Conflict
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '409'
                userMessage: Conflict
                systemMessage: Conflict
                detailLink: 'http://aaa.bbb.ccc/'
        '415':
          description: Unsupported Media Type
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '415'
                userMessage: Unsupported Media Type
                systemMessage: Unsupported Media Type
                detailLink: 'http://aaa.bbb.ccc/'
        '500':
          description: Internal Server Error
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '500'
                userMessage: Internal Server Error
                systemMessage: Internal Server Error
                detailLink: 'http://aaa.bbb.ccc/'
        '503':
          description: Service Unavailable
          headers:
            service-transaction-id:
              description: >-
                This Id is going to represent a service transaction id which is
                sent by partner
              schema:
                pattern: .*$
                type: string
            Date:
              description: >-
                The Date general HTTP header contains the date and time at which
                the message was originated.
              schema:
                type: string
                format: date-time
            Content-Type:
              description: The MIME type of this content
              schema:
                maxLength: 256
                minLength: 1
                pattern: '^[ \S]+$'
                type: string
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Error'
              example:
                code: '503'
                userMessage: Service unavailable
                systemMessage: Service unavailable
                detailLink: 'http://aaa.bbb.ccc/'
      security:
        - Oauth:
            - 'read:SubscriberInfo'
      x-api-pattern: ExecuteFunction
      x-codegen-request-body-name: SearchNetworkRequest
components:
  schemas:
    Error:
      required:
        - code
        - userMessage
      type: object
      properties:
        code:
          pattern: '^[\S ]+$'
          type: string
          description: >-
            A succinct, domain-specific, human-readable text string to identify
            the type of error for the given status code
          example: ProductNotFound
        userMessage:
          pattern: '^[\S ]+$'
          type: string
          description: A human-readable message describing the error.
          example: Failed to find product.
        systemMessage:
          pattern: .*$
          type: string
          description: >-
            Text that provides a more detailed technical explanation of the
            error
          example: PRODUCT_NOT_FOUND
        detailLink:
          pattern: .*$
          type: string
          description: >-
            link to custom information providing greater detail on error or
            errors
          example: 'http://aaa.bbb.ccc/'
      description: >-
        Format defined in
        http://api-standards.apps.px-npe01.cf.t-mobile.com/http/status-codes/error-response-format/
        and error details reference:
        https://qwiki.internal.t-mobile.com/display/ESG/JWT+Implementation+-+Change+Summary
    callForwardingRequest:
      required:
        - consentMerchant
        - consentTimestamp
        - consentType
        - msisdn
      type: object
      properties:
        msisdn:
          maxLength: 15
          minLength: 10
          pattern: '[0-9]{10,15}'
          type: string
          description: >-
            Mobile Subscriber Integrated Services Digital Network Number. A
            number uniquely identifying a subscription in a GSM or a UMTS mobile
            network. Simply put, it is the telephone number to the SIM card in a
            mobilecellular phone.
          example: '9723021456'
        consentMerchant:
          maxLength: 50
          minLength: 5
          pattern: .*$
          type: string
          description: Merchant name
          example: Bank of America
        consentTimestamp:
          type: string
          description: Time stamp format
          format: date-time
          example: '2015-12-08T00:34:31.536Z'
        consentType:
          maxLength: 7
          minLength: 7
          type: string
          description: Represents onetime or ongoing consent
          example: onetime/ongoing
          enum:
            - onetime
            - ongoing
      description: CallForwardingRequest Info
      example:
        callForwardingRequest:
          msisdn: '4049930243'
          consentMerchant: Bank of America
          consentTimestamp: '2019-05-21T13:34:31.536Z'
          consentType: onetime
    CallForwardingResponseInfo:
      type: object
      properties:
        callForwardingResponse:
          $ref: '#/components/schemas/CallForwardingResponse'
    CallForwardingResponse:
      type: object
      properties:
       callForwarding:
          enum:
            - '0'
            - '1'
          type: string
          description: >-
            Indicates whether call forwarding is enabled to forward to a
            specific MSISDN. Values: 1 indicates call forward enabled  , 0 indicates is disabled
       account:
          $ref: '#/components/schemas/Account'
       doNotSellSetting:
          type: string
          description: 'DNS Setting. Value of 0 indicates subscriber has opted to not sell their data.'
      description: CallForwardingResponse Info
    Account:
      type: object
      properties:
        customerType:
          enum:
            - '4'
          type: string
          description: 'Value of 4 is returned when the msisdn is unsupported'
  parameters:
    interactionidParam:
      name: interaction-id
      in: header
      description: This Id is going to represent a interactionid which is sent by partner
      schema:
        pattern: .*$
        type: string
      example: idAB12345678
    content-typeParam:
      name: Content-Type
      in: header
      description: Content-Types that are allowed for request including application/json
      required: true
      schema:
        type: string
        enum:
          - application/json
      example: application/json
    acceptParam:
      name: Accept
      in: header
      description: Accept that are allowed for response including application/json
      required: true
      schema:
        type: string
        enum:
          - application/json
      example: application/json
    AuthorizationParam:
      name: Authorization
      in: header
      description: OAuth 2.0 access token with the authentication type set as Bearer.
      required: true
      schema:
        pattern: '[bB]earer .*$'
        type: string
      example: >-
        Bearer
        eyJraWQiOiJiNzM5Yzc0NS1hNmUyLWE4NjYtOTljMS1kYmY1NGEwZjNlZDUiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiJBVWpHYTV1QTJBWFdVMnVFSDF0aFNRdEtKQ0NrOGFsOSIsInJ0Ijoie1wic2VnbWVudGF0aW9uSWRcIjpcIlBPTEFSSVNcIn0iLCJpc3MiOiJodHRwczpcL1wvcGQwMS5hcGkudC1tb2JpbGUuY29tXC9vYXV0aDJcL3Y0IiwibWFzdGVyRGVhbGVyQ29kZSI6IiIsImF1dGhUaW1lIjoiMTU0ODQ1OTYzODY1MCIsInVzbiI6ImU0ZjM2NjEwLWNjZjgtYTg1Zi01OWM5LTQxODI4YjdiYTc4ZSIsImF1ZCI6IkFVakdhNXVBMkFYV1UydUVIMXRoU1F0S0pDQ2s4YWw5Iiwic2VuZGVySWQiOiIiLCJuYmYiOjE1NDg0NTk2MzksImFwcGxpY2F0aW9uSWQiOiIiLCJleHAiOjE1NDg0NjMyMzksImlhdCI6MTU0ODQ1OTYzOSwiY2hhbm5lbElkIjoiIiwianRpIjoiNzYxZmQyOGUtMTIwOS0yM2RkLTViNTgtMDI0ZjZhZGI5ZDg3In0.EqSwwSylQLijnG1eGwE195DotpnOO2iNgL7ohY7rMatEIShqHVT8HeKhNVPw_t6tINv7cJFBhwZEhpSqQq2arOJCa7D-4slsqwyucmxWp0hAZYFaxII4-ag3zT5TPkbE0OFaYGPopoN6rlcim4fBOEEH8XDhGc6iVjGt56i9gXQcK8DywMSnsi4Yleys5346w14Wxam7x67gE0892T7sGLLuRo-yEeTu5opTfyEneNAtVBwnJmXxRo_Vy5NjunmhdJB5Aau4FJxmWhf5o7JH5BEYFVfHbmh0-bC9zcggp4IfQ5jBVt-IIEJe6G_FoVO2OdebXikVf6uaL7RqFHdaig
    serviceTransactionIdParam:
      name: service-transaction-id
      in: header
      description: >-
        This Id is going to represent a service transaction id which is sent by
        partner
      schema:
        pattern: .*$
        type: string
      example: idAB12345678
    xAuthorizationParam:
      name: x-authorization
      in: header
      description: OAuth 2.0 access token
      schema:
        pattern: .*$
        type: string
      example: >-
        eyJraWQiOiJiNzM5Yzc0NS1hNmUyLWE4NjYtOTljMS1kYmY1NGEwZjNlZDUiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiJBVWpHYTV1QTJBWFdVMnVFSDF0aFNRdEtKQ0NrOGFsOSIsInJ0Ijoie1wic2VnbWVudGF0aW9uSWRcIjpcIlBPTEFSSVNcIn0iLCJpc3MiOiJodHRwczpcL1wvcGQwMS5hcGkudC1tb2JpbGUuY29tXC9vYXV0aDJcL3Y0IiwibWFzdGVyRGVhbGVyQ29kZSI6IiIsImF1dGhUaW1lIjoiMTU0ODQ1OTYzODY1MCIsInVzbiI6ImU0ZjM2NjEwLWNjZjgtYTg1Zi01OWM5LTQxODI4YjdiYTc4ZSIsImF1ZCI6IkFVakdhNXVBMkFYV1UydUVIMXRoU1F0S0pDQ2s4YWw5Iiwic2VuZGVySWQiOiIiLCJuYmYiOjE1NDg0NTk2MzksImFwcGxpY2F0aW9uSWQiOiIiLCJleHAiOjE1NDg0NjMyMzksImlhdCI6MTU0ODQ1OTYzOSwiY2hhbm5lbElkIjoiIiwianRpIjoiNzYxZmQyOGUtMTIwOS0yM2RkLTViNTgtMDI0ZjZhZGI5ZDg3In0.EqSwwSylQLijnG1eGwE195DotpnOO2iNgL7ohY7rMatEIShqHVT8HeKhNVPw_t6tINv7cJFBhwZEhpSqQq2arOJCa7D-4slsqwyucmxWp0hAZYFaxII4-ag3zT5TPkbE0OFaYGPopoN6rlcim4fBOEEH8XDhGc6iVjGt56i9gXQcK8DywMSnsi4Yleys5346w14Wxam7x67gE0892T7sGLLuRo-yEeTu5opTfyEneNAtVBwnJmXxRo_Vy5NjunmhdJB5Aau4FJxmWhf5o7JH5BEYFVfHbmh0-bC9zcggp4IfQ5jBVt-IIEJe6G_FoVO2OdebXikVf6uaL7RqFHdaig
    xAuthOriginatorParam:
      name: x-auth-originator
      in: header
      description: ID Token
      schema:
        pattern: .*$
        type: string
      example: >-
        eyJraWQiOiJiNzM5Yzc0NS1hNmUyLWE4NjYtOTljMS1kYmY1NGEwZjNlZDUiLCJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJzdWIiOiJBVWpHYTV1QTJBWFdVMnVFSDF0aFNRdEtKQ0NrOGFsOSIsInJ0Ijoie1wic2VnbWVudGF0aW9uSWRcIjpcIlBPTEFSSVNcIn0iLCJpc3MiOiJodHRwczpcL1wvcGQwMS5hcGkudC1tb2JpbGUuY29tXC9vYXV0aDJcL3Y0IiwibWFzdGVyRGVhbGVyQ29kZSI6IiIsImF1dGhUaW1lIjoiMTU0ODQ1OTYzODY1MCIsInVzbiI6ImU0ZjM2NjEwLWNjZjgtYTg1Zi01OWM5LTQxODI4YjdiYTc4ZSIsImF1ZCI6IkFVakdhNXVBMkFYV1UydUVIMXRoU1F0S0pDQ2s4YWw5Iiwic2VuZGVySWQiOiIiLCJuYmYiOjE1NDg0NTk2MzksImFwcGxpY2F0aW9uSWQiOiIiLCJleHAiOjE1NDg0NjMyMzksImlhdCI6MTU0ODQ1OTYzOSwiY2hhbm5lbElkIjoiIiwianRpIjoiNzYxZmQyOGUtMTIwOS0yM2RkLTViNTgtMDI0ZjZhZGI5ZDg3In0.EqSwwSylQLijnG1eGwE195DotpnOO2iNgL7ohY7rMatEIShqHVT8HeKhNVPw_t6tINv7cJFBhwZEhpSqQq2arOJCa7D-4slsqwyucmxWp0hAZYFaxII4-ag3zT5TPkbE0OFaYGPopoN6rlcim4fBOEEH8XDhGc6iVjGt56i9gXQcK8DywMSnsi4Yleys5346w14Wxam7x67gE0892T7sGLLuRo-yEeTu5opTfyEneNAtVBwnJmXxRo_Vy5NjunmhdJB5Aau4FJxmWhf5o7JH5BEYFVfHbmh0-bC9zcggp4IfQ5jBVt-IIEJe6G_FoVO2OdebXikVf6uaL7RqFHdaig
  securitySchemes:
    Oauth:
      type: oauth2
      x-scheme: bearer
      x-bearerFormat: JWT
      description: |
        When you sign up for an account, you are given your first API key.
        To do so please follow this link: https://www.t-mobile.com/site/signup/
        Also you can generate additional API keys, and delete API keys (as you may
        need to rotate your keys in the future).
      flows:
        authorizationCode:
          authorizationUrl: 'https://dit01-pd.api.t-mobile.com/oauth2/v6/authorization'
          tokenUrl: 'https://dit01-pd.api.t-mobile.com/oauth2/v6/tokens'
          scopes:
            'see-bootcamp:users:*': 'Read, update and delete Users'
        clientCredentials:
          tokenUrl: 'https://dit01-pd.api.t-mobile.com/oauth2/v6/tokens?grant_type=client_credentials'
          scopes:
            'read:consumerOnboardingInfo': Get access token
x-servers:
  - url: 'https://dit01-pd.t-mobile.com'
    description: Sandbox Server
  - url: 'https://api.t-mobile.com'
    description: Live Server

```
