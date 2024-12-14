# Gameplay Message Router

The Gameplay Message Router is a robust subsystem designed for registering and facilitating communication between unconnected gameplay objects. This system allows you to send and receive messages containing specific data through defined channels, utilizing gameplay tags. Developed by Epic Games, Inc., this subsystem is compatible with Unreal Engine 5.0.0 or higher and currently supported on the Windows platform.

For latest engine versions plugin update [click here](https://github.com/imnazake/gameplay-message-router/issues/3)

## Getting Started

To integrate the Gameplay Message Router into your project, follow these simple steps:

1. Obtain the Lyra game project from the [Lyra Github Repo](https://github.com/EpicGames/UnrealEngine/tree/ue5-main/Samples/Games/Lyra/Plugins/GameplayMessageRouter) (requires a Github account linked to Epic Games).
2. Copy the 'GameplayMessageRuntime' plugin from the Lyra project's plugins folder and paste it into your project's plugins folder (YourProject/Plugins/GameplayMessageRuntime).
3. Add 'GameplayMessageRuntime' to your `YourProject.Build.cs` file.
4. Regenerate your project's solution files.

## How to Use

### 1. Set up your message structure:

![Message Structure](/Docs/Capture01.PNG)

### 2. Create a function to send the message:

In your class, create a function to send the message and add a gameplay tag representing the channel:

![Send Message](/Docs/Capture02.PNG)
![Channel Tag](/Docs/Capture03.PNG)

Note: You can also broadcast messages directly from Blueprint using the `BroadcastMessage` node.

![Broadcast Message](/Docs/BP_Capture01.png)

### 3. Test it in Blueprint:

Create a child actor class from `MyActor` C++ class and another actor that doesn't necessarily need to inherit from `MyActor`.

![Actor Classes](/Docs/Capture04.PNG)

In `Actor01` Blueprint, create a sample message to send on begin play.

![Actor01 Blueprint](/Docs/Capture05.PNG)

In `Actor02` Blueprint, specify a channel and select the relevant message structure to receive the message from `Actor01`.

![Actor02 Blueprint](/Docs/Capture06.PNG)

### 4. Define gameplay tags and message structures:

Define gameplay tags for sending or receiving messages on specific channels.

![Gameplay Tags](/Docs/Capture07.PNG)
![Gameplay Tags](/Docs/Capture08.PNG)

Select the structure containing your message data (e.g., `SampleMessage`).

![Message Structure](/Docs/Capture09.PNG)

### 5. Test the setup:

After placing both actors in the level, the message sent from `Actor01` should be displayed on `Actor02` when the game begins.

![Gameplay Test](/Docs/Capture10.PNG)

Enjoy seamless communication between gameplay objects using the Gameplay Message Router!

## Supported Engine Versions

5.0 or higher

## Supported Platforms

- Windows
- Mac
- Linux

## Network Replication Support

Not Supported
