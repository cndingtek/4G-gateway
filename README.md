# 4G_Gateway
This is gateway in python for CNDINGTEK 4G LTE devices. 
As the CNDINGTEK 4G LTE devices uses private protocol to upload data, sometimes the users have questions or problems while they try to drive the devices to their own clould server.In order to help users to start the testing, CNDINGTEK offer this project in MIT license. 

# Test Environment
Python 3.8.1
Windows 10
# Supported Sensors
support nb-iot sensors from CNDINGTEK
dh100 door sensor
do200 parking sensor
df200 hand sanitelizer level sensor
dt310 temperature/humidity sensor
df400 toilet paper level sensor
dc500 people counter
df530 lpg tank level sensor
df702 waste bin level sensor (TODO)
# Usage
check the .py file with the model name you want to integrate, there is parse_data_xx function, which parse the incoming packet which is filtered by the hand_client function in 4G_Server_Gateway.py.
The 4G_Server_Gateway.py include demo for server listening and tcp client incoming data from sensors. After packet parsed, upload_data function will be called to upload/forward to user application or any other 3rd party application in http. Of course, user can forward in other format like mqtt and etc based on their own requirements.

# FAQ
IEEE754_Hex_To_Float error in x64 system.
try to change 
line 26:data_middle = struct.pack("q", data_first)
to
data_middle = struct.pack("l", data_first)

