curl --location --request POST 'https://sit.nonprod.tcsaiwisdomnext.tcsapps.com/wisdomv3/api/ragnormal/chat/defined-context/925/16' \
--header 'Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmcmVzaCI6ZmFsc2UsImlhdCI6MTc0MTM0MzExMSwianRpIjoiMGU0NTcyNzAtOGRlNi00NjdhLTk5OWEtYzU3Mjk1NjczNGMxIiwidHlwZSI6ImFjY2VzcyIsInN1YiI6eyJlbWFpbCI6ImFtaXJkaGFnYWRlc2FuLnJhamFzZWthckB0Y3MuY29tIiwicm9sZXMiOiJBZG1pbiJ9LCJuYmYiOjE3NDEzNDMxMTEsImNzcmYiOiI1YmRiYWMzOC1kZjVmLTRkMzUtYmZhNC1iNjBjZjYyNjBmZDciLCJleHAiOjE3NDEzNzU1MTF9.FsJT_yno3KcbWYABCQzt6c3xd-ZRqAabY7JduqPaik4' \
--header 'Content-Type: application/json' \
--data-raw '{
    "provider_name": "AzureOpenAI",
    "model_name": "gpt-4o",
    "temperature": 0.1,
    "human_message": "Generate a technical specification for the given code. Keep in mind that this technical specification should be comprehensive enough to enable Spring boot java microservice generation.",
    "system_message": "You are a COBOL expert, who can understand the code and assist in generating technical specification for a given context.",
    "context": "IDENTIFICATION DIVISION.        PROGRAM-ID. ORDER-FULFILL.        AUTHOR. ASSISTANT.                ENVIRONMENT DIVISION.        INPUT-OUTPUT SECTION.        FILE-CONTROL.            SELECT ORDER-FILE ASSIGN TO '\''ORDERS.DAT'\''                ORGANIZATION IS LINE SEQUENTIAL.            SELECT INVENTORY-FILE ASSIGN TO '\''INVENTORY.DAT'\''                ORGANIZATION IS LINE SEQUENTIAL.            SELECT REPORT-FILE ASSIGN TO '\''FULFILLMENT.RPT'\''                ORGANIZATION IS LINE SEQUENTIAL.                DATA DIVISION.        FILE SECTION.        FD ORDER-FILE.        01 ORDER-RECORD.           05 ORDER-ID            PIC X(6).           05 PRODUCT-ID          PIC X(8).           05 QUANTITY-ORDERED    PIC 9(3).           05 CUSTOMER-ID         PIC X(5).                FD INVENTORY-FILE.        01 INVENTORY-RECORD.           05 INV-PRODUCT-ID      PIC X(8).           05 QUANTITY-ON-HAND    PIC 9(5).           05 PRODUCT-PRICE       PIC 9(3)V99.                FD REPORT-FILE.        01 REPORT-LINE            PIC X(80).                WORKING-STORAGE SECTION.        01 WS-FLAGS.           05 EOF-ORDER           PIC X(1) VALUE '\''N'\''.           05 EOF-INVENTORY       PIC X(1) VALUE '\''N'\''.                01 WS-REPORT-HEADER.           05 FILLER              PIC X(22) VALUE '\''Order Fulfillment Report'\''.                   01 WS-ORDER-DETAIL.           05 FILLER              PIC X(7) VALUE '\''Order: '\''.           05 WS-ORDER-ID         PIC X(6).           05 FILLER              PIC X(11) VALUE '\'', Product: '\''.           05 WS-PRODUCT-ID       PIC X(8).           05 FILLER              PIC X(12) VALUE '\'', Quantity: '\''.           05 WS-QUANTITY         PIC 9(3).           05 FILLER              PIC X(9) VALUE '\'', Status: '\''.           05 WS-STATUS           PIC X(12).                PROCEDURE DIVISION.        MAIN-PROGRAM.            OPEN INPUT ORDER-FILE            OPEN INPUT INVENTORY-FILE            OPEN OUTPUT REPORT-FILE                        WRITE REPORT-LINE FROM WS-REPORT-HEADER                        READ ORDER-FILE                AT END MOVE '\''Y'\'' TO EOF-ORDER            END-READ                        PERFORM PROCESS-ORDERS UNTIL EOF-ORDER = '\''Y'\''                        CLOSE ORDER-FILE            CLOSE INVENTORY-FILE            CLOSE REPORT-FILE                        STOP RUN.                    PROCESS-ORDERS.            MOVE ORDER-ID TO WS-ORDER-ID            MOVE PRODUCT-ID TO WS-PRODUCT-ID            MOVE QUANTITY-ORDERED TO WS-QUANTITY                        PERFORM CHECK-INVENTORY                        WRITE REPORT-LINE FROM WS-ORDER-DETAIL                        READ ORDER-FILE                AT END MOVE '\''Y'\'' TO EOF-ORDER            END-READ.                CHECK-INVENTORY.            MOVE '\''UNFULFILLED'\'' TO WS-STATUS                        PERFORM READ-INVENTORY UNTIL                 EOF-INVENTORY = '\''Y'\'' OR                INV-PRODUCT-ID = PRODUCT-ID                            IF EOF-INVENTORY = '\''N'\'' AND QUANTITY-ON-HAND >= QUANTITY-ORDERED                MOVE '\''FULFILLED'\'' TO WS-STATUS            END-IF                        CLOSE INVENTORY-FILE            OPEN INPUT INVENTORY-FILE.                    READ-INVENTORY.            READ INVENTORY-FILE                AT END MOVE '\''Y'\'' TO EOF-INVENTORY            END-READ.  ",
    "module_type": "BusinessModule",
    "fetch_from_db": false,
    "include_chat_history": true,
    "should_clear_session": false,
    "no_of_past_messages": 10
}'

{
    "email": "mohammed",
    "role": "Admin",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmcmVzaCI6ZmFsc2UsImlhdCI6MTc0MTQyNDA5MiwianRpIjoiOTNkNTNjYzItYWIyNC00ZDZkLTk5ZTMtZTRhYmI2YjJmYjNlIiwidHlwZSI6ImFjY2VzcyIsInN1YiI6eyJlbWFpbCI6Im1vaGFtbWVkbmF2YXNraGFuLmFAdGNzLmNvbSIsInJvbGVzIjoiQWRtaW4ifSwibmJmIjoxNzQxNDI0MDkyLCJjc3JmIjoiNDU3ZmJkY2MtYmNlNS00Y2ZkLWE3MmUtMzYzYzU3ODU2NzVhIiwiZXhwIjoxNzQxNDU2NDkyfQ.CvKONlfziay6QHDGrJH6fBhDq_-W7_-bohPy0brijzY"
}
 
{
    "email": "aravind",
    "role": "Admin",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmcmVzaCI6ZmFsc2UsImlhdCI6MTc0MTQyNDEzMCwianRpIjoiYmIwMGY0NWItZjg1MS00YzRiLTk0NTUtYzBjMjE1ZjZiNzAzIiwidHlwZSI6ImFjY2VzcyIsInN1YiI6eyJlbWFpbCI6ImFyYXZpbmQucmF2aTNAdGNzLmNvbSIsInJvbGVzIjoiQWRtaW4ifSwibmJmIjoxNzQxNDI0MTMwLCJjc3JmIjoiYzk5ODU4ODgtNzg0MS00NzA0LWFmZDUtMGM4MmJmOTc1ZjY4IiwiZXhwIjoxNzQxNDU2NTMwfQ.2y2xHxSy-MaVIwRmFMGyfg7xAX6IHuIsqZiRVqW4IuU"
}
{
    "email": "amir",
    "role": "Admin",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJmcmVzaCI6ZmFsc2UsImlhdCI6MTc0MTQzMjEwMCwianRpIjoiNDNlMGJjM2YtMjcyOC00YjllLTg5MTUtYTA1ZGYzMjc4MzQwIiwidHlwZSI6ImFjY2VzcyIsInN1YiI6eyJlbWFpbCI6ImFtaXJkaGFnYWRlc2FuLnJhamFzZWthckB0Y3MuY29tIiwicm9sZXMiOiJBZG1pbiJ9LCJuYmYiOjE3NDE0MzIxMDAsImNzcmYiOiJiMzcyNDY3OC04Y2VhLTRjMmItYTg0ZC0zOTQwMDkzYzQ5YmEiLCJleHAiOjE3NDE0NjQ1MDB9.3TI5IssoSELOskhBajbck-CdchTDymumfQz0tfP0_oI"
}
