# solisAPI
HTML code to install on web server to set charge times for Solis Battery Inverter

There's a youTube video showing these scripts/utilities in action. The date stamp on the video is May 2024 and the API calls and code were valid then.
https://www.youtube.com/watch?v=SHr3Gqpplqc

There are three files, all HTML (with PhP and Javascript) to install on a web server
The first two, agilePrices and solisSetBatteryChargeTimes are just helper utilities which assemble a HTML GET string to send to the third utility (setBatteryChargeTimes) which calls the Solis API using CURL.

You can run the third utility (setBatteryChargeTimes) by itself, but in any case, you MUST edit the script and enter your own
keyID
KeySecret
username
password (currently pulled in from the second utility using HTML GET)
plant/station name

The agilePrices will be useful for UK users who are on Octopus's Agile Pricing contract. This file can be editted to set the tarriff and region code which are bound to change in the future. Currently the region is set to Southern England.

The job of solisSetBatteryChargeTimes is to create the 18 elements of the string that is eventually sent to the SolisCloud through the API. It can be altered too, because right now I know no-one who actually discharges the battery to the grid - so all the discharge currents and times default to zero. 

Also in solisSetBatteryChargeTimes there is a password input really so you done have to hard code it in the php in the last utility (setBatteryChargeTimes)

Personally, I put a username/password access control on the pages on my website where I run this as a bit of insurance against others gaining access to the keys and secrets in my copy of the scripts.

