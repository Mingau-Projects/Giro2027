# Minecraft Wheat Farming Bot

This project is a Minecraft bot that automates wheat farming tasks. It uses the Mineflayer library to connect to a Minecraft server and perform actions like tilling land, planting seeds, and harvesting crops and putting it in chest . The bot also manages its inventory, checks for valid block types, and handles disconnections and reconnections.
I made this because wheat farming is only semi automatic through redstone

## Features

- farming: The bot can till land, plant seeds, and harvest crops.
- overflow prevention: bot stops farming if the chest nearby
- Inventory management: The bot manages its inventory, equipping tools and seeds as needed, and depositing harvested crops in a chest.
- Block type checking: The bot checks the type of each block in the specified farming area and performs the appropriate action.
- Disconnection handling: The bot attempts to reconnect every 20 seconds if it gets disconnected.
- Chat commands: The bot listens for chat commands and responds to commands like `!help`, `!exit`, `!enable`, `!disable`, and `!set`. These commands allow users to interact with the bot and control its behavior.

## Installation

1. Clone this repository.
2. Run `npm install` to install the required dependencies.
3. Create a `.env` file in the root directory and set the following environment variables:
   - `host`: The IP address of the Minecraft server. (required)
   - `port`: The port number of the Minecraft server.
   - `auth`: The authentication method for the Minecraft server. (required)
   - `username`: The username of the Minecraft account.
   - `password`: The password of the Minecraft account.
   - `version`: The Client version of the Minecraft bot. if not given mineflayer autodetects

## Usage

1. Run `node index.js` to start the bot.
2. In Minecraft, use the chat commands to interact with the bot:
   - `!help`: Displays a list of available commands.
   - `!exit`: Quits the bot.
   - `!enable`: Enables automatic farming.
   - `!disable`: Disables automatic farming.
   - `!set`: Sets the farming area. The command format is `!set startcords endcords dustbincords`, e.g., `!set 1,2,3 4,5,6 7,8,9`.
3. In minecraft, use the !set command

## Notes

1.  currently bot dies of hunger code has to be modified to disable sprint if hunger is low and  to eat food or craft  if feasable
2.  bot doesnt defend itself
3.  bot doesnt do anti afk techniques if it is idle
    1 & 2 workaround - give bot effect through command block(resistance,saturation,instanthealth,etc) or set his respawn point(through bed by logging into bot or /setworldspawn cmd) near farm or splashing saturation and health potions on him (expensive)
    3 - bot will rejoin if kicked by antiafk plugins so itsnt much of an isssue

## Roadmap

1.  hunger management
2.  defending
3.  anti afk
4.  actions based on fastest route instead of lopping through farm cords
5.  check if required seeds count doesnt exceed inventory space and minempty slots limit
6.  more 

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License.

## Troubleshooting
Rarely Pathfinding or maybe other issue bot might get stuck on death
If bot try to join incompattable / modded / offline aternos server it will give error `TypeError: Cannot read properties of undefined (reading 'minecraftVersion')` because they set their version as -1 which is invalid according to mineflayer d
If you are using an Aternos server and encounter strange errors like(SyntaxError: "[object Object]" is not valid JSON
at JSON.parse (<anonymous>)
at Client.<anonymous> ) when the server is offline. This is because Aternos servers often have custom offline messages that cause issues with parsing JSON in the Mineflayer library.

This project is licensed under the MIT License.
