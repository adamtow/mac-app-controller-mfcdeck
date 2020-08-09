# Mac App Controller for MFC Deck

Mac App Controller for MFC Deck lets you control applications on your Mac using [MFC Deck](https://mfcdeck.com) and the [MFC Deck Key Command shortcut](https://mfcdeck.com/key-command).

***

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
