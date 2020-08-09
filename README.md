# Mac App Controller for MFC Deck

Mac App Controller for MFC Deck lets you control applications on your Mac using [MFC Deck](https://mfcdeck.com) and the [MFC Deck Key Command shortcut](https://mfcdeck.com/key-command). This shortcut installs a deck and cards for controlling various Mac applications, such as:

- ATEM Software Control
- Finder
- Mail
- QuickTime Player
- Xcode
- Xcode-beta
- Zoom

***

## System Requirements

The following applications and shortcuts must be installed on your iOS device for this installer to work.

- [MFC Deck](https://mfcdeck.com)
- [MFC Deck Key Command shortcut](https://mfcdeck.com/key-command)

Use the menu items to get these apps and shortcuts before continuing.

## Installing a New Mac App Deck

1. Tap New Mac App Deck…
2. Select the Mac application you want to create a control deck for.
3. Enter the name of your deck. If the deck already exists, you will be prompted to enter a new name or replace the existing deck.
4. The selected deck will then be created in MFC Deck.
5. Choose to open the deck or return to the main menu.

## MFC Deck Key Command

Using the cards in a Mac App Deck requires the use of the [MFC Deck Key Command shortcut](https://mfcdeck.com/key-command).

It is recommended that you create a copy of MFC Deck Key Command for each computer you wish to control. You must enter the following information into Authentication dictionary at the beginning of the shortcut:

- **host**: The hostname for the macOS computer you wish to control. You can get the hostname from System Preferences > Sharing
- **username**: The username for the account you wish to control.
- **password**: The password for the selected user.

**NOTE: Your username and password are stored in the clear within the shortcut. Be sure you DO NOT share this shortcut with anyone, or else they could gain access to your computer.**

## Usage

1. Open MFC Deck.
2. Go to the Mac app deck you created earlier.
3. Tap on the card corresponding to the app action you wish to perform on your macOS computer.

## Troubleshooting

If you are running macOS Catalina or higher, you may have to enable several security preferences in order for your commands to be processed properly. Open System Preferences > Security & Privacy and perform the following actions:

**System Preferences > Security & Privacy > Privacy > Accessibility**

- Terminal should be in the list of apps that can control your computer
- System Events should be in the list of apps that can control your computer

Terminal is used to send the osascript shell script command, which runs the AppleScript used by the System Events to dispatch commands to the correct application.

**System Preferences > Sharing**

- Remote Login must be enabled

***

## Developer

Want to control additional apps on your Mac? Read the API documentation below on how to create your own App Dictionary.

## App Dictionary Format

Each dictionary key corresponds to a Mac app that MFC Deck can control. Each dictionary key points to an array of cards where each card is a single command to be sent to an application on your macOS computer or a shortcut to run on your iOS device.

- **Key Command**: Send a command to the macOS computer.
- **Shortcut**: Run a shortcut with optional input.

The App Dictionary is a dictionary with the following key value pairs:

- **Name**: Name of the app to control (and default deck name)
- **Icon**: The icon to use for the deck
- **Color**: The color of the deck
- **Cards**: An array holding either dictionaries that follow the Key Command format or the Shortcut format, described below.

### Key Command Dictionary Format

- **Name**: The name of the card.
- **Command**: The key command to send to the macOS computer. For instance: Command W
- **Icon**: The card's icon. Use sfsymbols or shortcut icons names.
- **Color**: The card's color. Specify shortcut colors (see list below)
- **App**: Name of the Mac app to control. If blank, the frontmost application will receive the command.

### Shortcut Dictionary Format

- **Name**: The name of the card.
- **Shortcut**: The shortcut to run.
- **Input**: The input to pass to the shortcut.
- **Icon**: The card's icon. Use sfsymbols or shortcut icons names.
- **Color**: The card's color. Specify shortcut colors (see list below)

### Icons

A list of SF Symbol values can be found by downloading the SF Symbols app at:

https://developer.apple.com/sf-symbols

### Colors

The following color strings are supported:

- Red
- Vermillion
- Apricot
- Pollen
- Mint
- Turquoise
- Light Blue
- Cerulean
- Delft Blue
- Violet
- Lilac
- Pink
- Fog
- Limestone
- Sand

### Sample App Dictionaries

You can view the App Dictionaries for the sample applications in this shortcut at: [https://github.com/adamtow/mac-app-controller-mfcdeck/tree/master/apps](https://github.com/adamtow/mac-app-controller-mfcdeck/tree/master/apps).

If you want to submit your own apps to be included in a future version of this shortcut, submit a Pull request.


