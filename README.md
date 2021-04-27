
Bluetooth File Transfer
=======================


Receiver written with Python(Only run with Python from 3.9)

Sender written with Kotlin

Sender(Android) and receiver keep connection with below rules:

1. Sender will send keep alive message(IMA) every 5 second, and receiver will response(ACK).
2. If sender lost for more than 10 sec, receiver will be automatically reset to a listening status.
3. If receiver lost for more than 5 sec, sender will disconnect and retry connect every 10 sec.
4. Sender will send a finish(FIN) when app is being closed.

Sender will send file with below rules:

1. Sender send start sending message(STR).
2. Sender send file data with binary.
3. Sender send finished signal to notify receiver close file(EOF)
4. Receiver will send response(ACK) to sender let sender know file received successfully.
