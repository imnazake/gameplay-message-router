# Gameplay Message Router

A subsystem that allows registering for and sending messages between unconnected gameplay objects.
<br>
You can send and listen for messages that contain data in specific channels (defined using gameplay tags).
<br>
(e.g: you can use this subsystem for sending data that needs to be displayed in the user-interface without directly exposing game code).

##### Created By
+ Epic Games, Inc.
 
##### Engine Version
+ 5.0.0 or higher

#### Supported Platforms
+ Windows (I use Windows)

#### Network Replication
+ Not Replicated

##### How To Use
+ Clone this repository to your project Plugins folder or copy/paste it from Lyra project. (YourProject/Plugins/GameplayMessages)
+ Add 'GameplayMessageRuntime' to your PrivateDependencyModuleNames in YourProject.Build.cs file.
+ Regenerate project solution files.

+ Create your message structure which contains all the data that you want to send.

![](/Docs/Capture01.PNG)

+ In your class create a function to send the message when called, and add a gameplay tag that will represent the channel to be used for sending/receiving.

![](/Docs/Capture02.PNG)
![](/Docs/Capture03.PNG)

+ Now to test it in blueprint i created a child actor class from MyActor C++ class and another actor that doesn't necessarily need to inherit from MyActor.

![](/Docs/Capture04.PNG)

+ In Actor01 blueprint, i created a sample message to send as soon as the actor begin play is called. (after 1 second delay to allow the other actor to start listening otherwise it might not receive the message because it was not registered/listening)

![](/Docs/Capture05.PNG)

+ In Actor02 blueprint, to receive the messages we need to specify a channel and select the relevant message structure we sent from Actor01.
On begin play we start listening for messages sent on ( Game.Data.SampleChannel ) and print the data to screen as soon as it received.

![](/Docs/Capture06.PNG)

+ Define gameplay tags to use for sending or receiving messages on specific channels.

![](/Docs/Capture07.PNG)
![](/Docs/Capture08.PNG)

+ Select the structure that contains your message data (SampleMessage in this case, sent from Actor01).

![](/Docs/Capture09.PNG)

+ After placing both of the actors in the level when you begin play you should see the message displayed on the screen which is sent from Actor01 and displayed from Actor02.

![](/Docs/Capture10.PNG)
