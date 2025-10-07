Step by Step guide For yall
---

1️⃣ Setup

1. Place the script (CoinSystem.lua) in ServerScriptService.


2. Make sure API Services are enabled in Game Settings (for DataStore).


3. Ensure each player has a TextLabel in their PlayerGui to show coins.

Name can be anything, but it must be inside a ScreenGui.

Example hierarchy:

PlayerGui
  └── CoinGui (TextLabel)

The script searches for the first descendant named CoinGui and updates its .Text.





---

2️⃣ Configuring Coin Rates

Open CoinSystem.lua and find the CoinConfig table:


local CoinConfig = {
    KillEnemy = 10,      -- coins per enemy
    CollectItem = 5,     -- coins per item
    CompleteQuest = 50   -- coins per quest
}

Change numbers to adjust how much the player earns.

Add new events easily:


MineGem = 20,
CompleteDaily = 100,


---

3️⃣ Adding Coins in Game Events

Anywhere in your game logic where a player earns coins, call:


AddCoins(player, CoinConfig.KillEnemy)       -- for killing enemy
AddCoins(player, CoinConfig.CollectItem)     -- for collecting an item
AddCoins(player, CoinConfig.CompleteQuest)   -- for completing quest

Replace the event with the appropriate key from CoinConfig.



---

4️⃣ GUI Updates

The script automatically updates the TextLabel in the player’s GUI.

Text format: "Coins: <current amount>".

Works with his existing GUI, no need to create a new one.



---

5️⃣ Data Persistence

Player coins are saved in DataStore under their UserId.

Coins are loaded automatically when the player joins.

Coins are saved automatically when the player leaves.



---

✅ Optional Tips

1. He can add new events in CoinConfig anytime without touching the core logic.


2. He can style the TextLabel (size, color, position) freely — the script just updates the text.


3. Works with multiple earn sources simultaneously (e.g., enemies + items + quests).




---

If you want, I can make a diagram showing the Coin System flow — from earning → updating GUI → saving to DataStore — so he can fully visualize it for GitHub or team documentation.

Do you want me to make that diagram?

