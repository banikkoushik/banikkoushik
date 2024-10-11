#coded by N17RO (noob hackers)

#modules required
import argparse
import requests, json
import sys
from sys import argv
import os

#arguments and parser

parser = argparse.ArgumentParser()

parser.add_argument ("-v", help= "target/host IP address", type=str, dest='target', required=True )

args = parser.parse_args()

#colours used
red = '\033[31m'
yellow = '\033[93m'
lgreen = '\033[92m'
clear = '\033[0m'
bold = '\033[01m'
cyan = '\033[96m'

#banner of script
print (red+"""

██╗██████╗ ██████╗ ██████╗  ██████╗ ███╗   ██╗███████╗
██║██╔══██╗██╔══██╗██╔══██╗██╔═══██╗████╗  ██║██╔════╝
██║██████╔╝██║  ██║██████╔╝██║   ██║██╔██╗ ██║█████╗  
██║██╔═══╝ ██║  ██║██╔══██╗██║   ██║██║╚██╗██║██╔══╝  
██║██║     ██████╔╝██║  ██║╚██████╔╝██║ ╚████║███████╗
╚═╝╚═╝     ╚═════╝ ╚═╝  ╚═╝ ╚═════╝ ╚═╝  ╚═══╝╚══════╝
                                                      v 1.0
"""+red)
print (lgreen+bold+"         <===[[ coded by N17RO ]]===> \n"+clear)
print (yellow+bold+"   <---(( search on youtube Noob Hackers ))--> \n"+clear)


ip = args.target

api = "http://ip-api.com/json/"

try:
        # Ensure the keys exist before trying to print them
try:
    data = requests.get(api + ip).json()
    sys.stdout.flush()
    a = lgreen + bold + "[$]"
    b = cyan + bold + "[$]"

    print(a, "[Victim]:", data.get('query', 'N/A'))
    print(red + "<--------------->" + red)
    print(b, "[ISP]:", data.get('isp', 'N/A'))
    print(red + "<--------------->" + red)
    print(a, "[Organisation]:", data.get('org', 'N/A'))
    print(red + "<--------------->" + red)
    print(b, "[City]:", data.get('city', 'N/A'))
    print(red + "<--------------->" + red)
    print(a, "[Region]:", data.get('region', 'N/A'))
    print(red + "<--------------->" + red)
    print(b, "[Longitude]:", data.get('lon', 'N/A'))
    print(red + "<--------------->" + red)
    print(a, "[Latitude]:", data.get('lat', 'N/A'))
    print(red + "<--------------->" + red)
    print(b, "[Time zone]:", data.get('timezone', 'N/A'))
    print(red + "<--------------->" + red)
    print(a, "[Zip code]:", data.get('zip', 'N/A'))
    print(" " + yellow)

except KeyboardInterrupt:
    print('Terminating, Bye' + lgreen)
    sys.exit(0)
except requests.exceptions.ConnectionError as e:
    print(red + "[~]" + " check your internet connection!" + clear)
    sys.exit(1)
