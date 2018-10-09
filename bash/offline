#!/bin/bash

# usage: offline <protocols>
# example: offline gps bluetooth

CVARS=$@
for VAR in $CVARS; do
	if [[ $VAR == "wifi" ]]; then
		rfkill block wifi
		echo "Blocked WIFI."
	elif [[ $VAR == "gps" ]]; then
		rfkill block gps
		echo "Blocked GPS."
	elif [[ $VAR == "bluetooth" ]]; then
		rfkill block bluetooth
		echo "Blocked Bluetooth."
	else
		echo "Error: invalid wireless communication option provided: $VAR"
	fi
done

if [[ -z $1 ]]; then
	rfkill block wifi
	rfkill block gps
	rfkill block bluetooth
	echo "Blocked WIFI, GPS, Bluetooth."
	exit
fi
