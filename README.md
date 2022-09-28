# qb-vehiclekeys
Vehcilekeys with key and qb-lock minigame instead of the ugly lockpick ui
BIG THANKS to https://github.com/Sna-aaa/qb-sna-vehiclekeys

The key is created with the vehicle plate and model in item description
Keys are given at car buy (events available)
The locksmith is used to buy additional keys and change locks of a car
When a player tries to enter the car, it check the lock value of the car
Npc cars are accessible the gta way (carjacking or window breaking)
If car is locked the player can lockpick it, else the player can enter
Once the player is in the car a check is made for the key item in inventory to start the engine
If the player have no key he can try to hotwire the car
For admin cars (/car) the car is now yours temporarly, so you have an "old style invisible key"

REQUIREMENTS:

https://github.com/qbcore-framework/qb-core 

https://github.com/YishengCheww/qb-lock

https://github.com/qbcore-framework/qb-inventory

Please do the following steps to function properly:

    Delete qb-vehiclekeys

    Copy the vehiclekeys image in img folder into qb-inventory\html\images

    Import player_vehicles.sql into your database

    Add in qb-core/shared/items.lua

	['vehiclekey'] 				 	 = {['name'] = 'vehiclekey',					['label'] = 'Vehicle key', 					['weight'] = 0, 		['type'] = 'item', 		['image'] = 'vehiclekeys.png', 				['unique'] = true, 	['useable'] = true, 	['shouldClose'] = true,	   ['combinable'] = nil,   ['description'] = "This is a car key, take good care of it, if you lose it you probably won't be able to use your car"},

Add item info to qb-inventory\html\js\app.js in function FormatItemInfo


        } else if (itemData.name == "vehiclekey") {
            $(".item-info-title").html('<p>' + itemData.info.model + '</p>');
            $(".item-info-description").html('<p>Plate : ' + itemData.info.plate + '</p>');


