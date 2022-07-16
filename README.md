# Gameplay Messages Subsystem

A subsystem that allows registering for and sending messages between unconnected gameplay objects.
<br>
You can send and listen for messages that contain data in specific channels (defined using gameplay tags).
<br>
(e.g: you can use this subsystem for sending/updating data that needs to be displayed in the user-interface).

##### Created By
+ Epic Games, Inc.
 
##### Engine Version
+ 5.0.0 or higher

#### Supported Platforms
+ Windows

#### Network Replication
+ Not Replicated

##### How To Use
Create your message structure which contains all the data that you want to send.

![](/Docs/Capture01.PNG)

In your class create a function to send the message when called, and add a gameplay tag that will represent the channel to be used for sending/receiving.

![](/Docs/Capture02.PNG)
