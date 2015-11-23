[![Version button](https://img.shields.io/github/release/adamb70/CSGO-Market-Float-Finder.svg)](https://github.com/adamb70/CSGO-Market-Float-Finder/releases)
[![Download button](https://img.shields.io/badge/download-here-green.svg)](http://bit.ly/CSGOmarketfloat)

# CSGO-Market-Float-Finder
Find Counter Strike: Global Offensive Steam Market skin float values, seeds, and skin type. Tabulates data for easy sorting.

![alt tag](http://i.imgur.com/q2Dqh51.png?1)

## Download

**Please read the instructions using this program!**

[Download](http://bit.ly/CSGOmarketfloat)

## Instructions
#### Signing In
**You must sign in with a Steam account that owns CS:GO!**
	
1. Launch the program and log in with your Steam account. You may check 'Remember Me' to autofill details when you launch the program, but be aware that this will store your Steam username and password **in plaintext** in the settings.txt file.

2. If it is your first time launching the program Steam will send you an authentication email, which the program will ask for. Enter this code and press 'OK'. The program will now save a 'sentry_username.bin' file which will authenticate you every time you log in from now on.

NOTE: If the program tells you that you need to sign in before processing items after your first login, just restart the program and try again. I will try and fix this bug soon.

#### Finding Market Data
1. Take the Steam Market URL of the item you want.(eg. http://steamcommunity.com/market/listings/730/%E2%98%85%20Gut%20Knife%20%7C%20Doppler%20%28Factory%20New%29)

2. Paste the URL into the Market URL box

3. Select the number of items to retrieve (1-3000).
**NOTE:** Using a high number such as 3000 will take a while, and using 3000 may cause Steam to throttle your connection for a few minutes. The Steam market only allows 100 results at a time, so 3000 items will query Steam 30 times.

4. Choose a currency and press 'Retrieve Items'.

5. Choose a Time Delay for each item in the process. If the time delay is too low Steam will not respond to the message in time and no more results will be added to the table. If this occurs, you will have to close the program and start again.

6. Wait until the processing finishes. You may pause the program and continue by pressing 'Pause' and 'Start'. **NOTE:** If you pause the processing and want to start processing a new set of data, clear the table first.

7. Once the processing has finished you need to filter by float value to find the lowest one, and then take note of that item's position. The position represents the item's place in the Steam market at the time of gathering the data. If this position says '27' for example, it will be on the second page since Steam displays 10 items per page.

8. To get around this 10 item limit, add **'?query=&start=0&count=100'** to the end of the market URL in your browser. This will make Steam display 100 items per page. Now if your item is position '27' it will be shown on the first page. This makes using the Javascript market link easy.

9. The Javascript Market Link can be pasted into your browser address bar, but first you must manually type **'javascript:'**. This is due to browser security reasons. If the Steam item is on the current page, the Javascript link
 will bring up a dialog to buy the item. If this dialog does not come up, the item has either moved page since gathering data (usually to the next page), or has already been sold.

#### Additional Features
* Export as .CSV can be used to export the current contents of the table into a spreadsheet.
* Parse Single Item:
     - This option brings up a menu that allows you to enter an 'Inspect in game' link, and returns the float value for that skin. This can be used to find the float value for items from outside of the Steam Market.
You should not use this while processing market data, as this could mix the results up. Pause any processing first, and resume it after.
* Settings:
    - The settings file contains default settings for the program. The currency is set to 0 (USD) by default, but can be set to:
      - 1 for GBP
      - 2 for EUR
      - 3 for RUB
      - 4 for CAD
      - 5 for BRL
    - The settings file will also contain your Steam username and password **IN PLAINTEXT** if you choose to check 'Remember Me' on the login form. You can delete these two lines if you have checked 'Remember Me' in the past and no longer want them remembered.

## Information
Uses **[Pysteamkit](https://bitbucket.org/AzuiSleet/pysteamkit/overview)** - A Python [SteamKit](https://github.com/SteamRE/SteamKit) port by Aziusleet

## TODO
* Show full information, not only float, on Parse Single Item dialog.
