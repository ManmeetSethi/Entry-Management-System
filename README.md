# Entry-Management-System

### Try out my take on the entry management system here: 

### Key Assumptions:
Enter valid hostname and address as: Rahul, A-1 refer to point 2 for details. 
Network Issue: This does not affect the functionality of the web-app: For sending out SMS, Twilio is being used which in its free version only sends the messages to verified mobile numbers, so it won’t work for unregistered mobile numbers if you want to test it out yourself reach out to me and I’ll have your number added. If the SMS can’t be sent due to this reason the network issue message is displayed, but it actually isn’t an issue with the app, just a shortcoming of using the free version:) Don’t take my word for it, the sample screenshot of received messages is attached. Also, there are several limitations with Twilio in India which can be found here, combine that with the limitations of the free version and voila.
https://support.twilio.com/hc/en-us/articles/223134167-Limitations-sending-SMS-messages-to-Indian-mobile-devices

The host details exist in the CSV file, host.csv these are the details of the employees in the organization as only they can host visitors, for a visitor to be checked in successfully, he has to enter a valid hostname and address as both of those are being used to verify the authenticity of the visitor.

## Approach:
As soon as a visitor clicks on the check-in button, he is asked to enter his own details along with the host’s name and address(which are used to authenticate the visitor). 

The timestamp is captured and an email and SMS is sent to the host, the details are taken from host.csv file and the details of the visitor are stored in the visitor.csv and status is set to 1 denoting ‘active’.(CSVs are chosen here because we wanted to deploy the POC on the cloud’s free version, but to make it more scalable any RDBMS can be used also because I have a Data Science Background and we love CSVs for some reason:)

When the visitor wants to check-out, a list of (active) visitors is shown, he chooses his own name and then the SMS and email are sent to him, with the timestamp and his status is changed to 0(inactive).

The details of all visitors are maintained in the visitor.csv with all relevant details acting as the visitor log.

The web-app is scripted entirely in Python, with Flask for Frontend.

## Heroku Link:
https://innovaccer-visiting-system.herokuapp.com/


