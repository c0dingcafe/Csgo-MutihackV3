from tkinter import *
import pymem
import pymem.process
import re
import webbrowser
from itertools import cycle
import threading
import subprocess
import requests
import time
import sys
import os
import keyboard
import time
from win32gui import GetWindowText, GetForegroundWindow
######################################################################################################################
# HWID "Hardware id lock"    This portion of the code locks the user out of the program if they dont have the right HWID.

# There HWID can be put into the pastebin below and will then work

hwid = str(str(subprocess.check_output('wmic csproduct get uuid')).strip().replace(r"\r", "").split(r"\n")[1].strip())
r = requests.get("https://pastebin.com/cxU0VUsm")


def printSlow(text):
    for char in text:
        print(char, end="")
        sys.stdout.flush()
        time.sleep(.11)


def Main_Program():
    if hwid in r.text:
        print("---------------------------")
        printSlow("Access granted")
        print("\n")
        print("---------------------------")
        print("\nHWID: " + hwid)
        print("\n")
        print("---------------------------")
        print("\n")
        time.sleep(.02)
    else:
        print("Error! HWID Not In Database!")
        print("Please contact https://discord.gg/Z9MxmBmKDP for help. HWID: " + hwid)
        os.system('pause >NUL')


if __name__ == "__main__":
    Main_Program()
######################################################################################################################
#Login panel
def anything(str):
    for letter in str:
        sys.stdout.write(letter)
        sys.stdout.flush()
        time.sleep(0.1)


anything("Welcome to sleepy's hacks \n")
print("---------Welcome---------")
username = input("Username:")
if username == "sleepy" :
    print("\n")
    print ("_______________________________")
    print("\n")
else :
    print ("please try another user name. This user name is incorrect")


password = input ("Password:")
if password  == "1234" :
    print("\n")
    print("---------------------------")
    print ("ACCESS  GRANTED")
    print("---------------------------")
    print ("Welcome User ")
    #continue for things like opening webpages or hidden files for access

else :
      print("Username or Password is incorrect")
      time.sleep(5)   # Delays for 5 seconds. You can also use a float value.
      exit()

######################################################################################################################
#Injection
print("---------------------------")
print("Injecting Sleepy's hacks")

def updt(total, progress):
    """
    Displays or updates a console progress bar.

    Original source: https://stackoverflow.com/a/15860757/1391441
    """
    barLength, status = 20, ""
    progress = float(progress) / float(total)
    if progress >= 1.:
        progress, status = 1, "\r\n"
    block = int(round(barLength * progress))
    text = "\r[{}] {:.0f}% {}".format(
        "#" * block + "-" * (barLength - block), round(progress * 100, 0),
        status)
    sys.stdout.write(text)
    sys.stdout.flush()

runs = 400
for run_num in range(runs):
    time.sleep(0.01)
    updt(runs, run_num + 1)

print("Sleepy's Hacks have been injected")

import time
time.sleep(5)   # Delays for 5 seconds. You can also use a float value.
######################################################################################################################
#Banner
print("""
        ~+

                 *       +
           '                  |
       ()    .-.,="``"=.    - o -
             '=/_       \     |
          *   |  '=._    |
               \     `=./`,        '
            .   '=.__.=' `='      *
   +                         +
        O      *        '       .


 ______     __         ______     ______     ______   __  __    _    ______     __  __     ______     ______     __  __     ______    
/\  ___\   /\ \       /\  ___\   /\  ___\   /\  == \ /\ \_\ \  /_/\ /\  ___\   /\ \_\ \   /\  __ \   /\  ___\   /\ \/ /    /\  ___\   
\ \___  \  \ \ \____  \ \  __\   \ \  __\   \ \  _-/ \ \____ \ \_\/ \ \___  \  \ \  __ \  \ \  __ \  \ \ \____  \ \  _"-.  \ \___  \  
 \/\_____\  \ \_____\  \ \_____\  \ \_____\  \ \_\    \/\_____\      \/\_____\  \ \_\ \_\  \ \_\ \_\  \ \_____\  \ \_\ \_\  \/\_____\ 
  \/_____/   \/_____/   \/_____/   \/_____/   \/_/     \/_____/       \/_____/   \/_/\/_/   \/_/\/_/   \/_____/   \/_/\/_/   \/_____/ 
     (FREE CSGO HACKS JOIN MY DISCORD)
""")

######################################################################################################################
# defs
def callback(url):
    webbrowser.open_new(url)
######################################################################################################################
def button_action():
    if(change_button["text"]=="Start Wallhack"):
        change_button.configure(text="Stop Wallhack")
        print("\n")
        print("SCRIPT IS RUNNING")
        print("\n")
    else:
        change_button.configure(text="Start Wallhack")
        print("\n")
        print("SCRIPT IS STOPPED")
        print("\n")
    try:
        pm = pymem.Pymem('csgo.exe')
        client = pymem.process.module_from_name(pm.process_handle, 'client.dll')

        clientModule = pm.read_bytes(client.lpBaseOfDll, client.SizeOfImage)
        address = client.lpBaseOfDll + re.search(rb'\x83\xF8.\x8B\x45\x08\x0F', clientModule).start() + 2

        pm.write_uchar(address, 2 if pm.read_uchar(address) == 1 else 1)
        pm.close_process()
    except:
        change_button.configure(text="Start Wallhack")
        print("error: please read the README file If you're having trouble join my discord")
        print("\n")
######################################################################################################################
def no_flash():
    if no_flash["text"] == "Start No Flash":
        no_flash.configure(text="Stop No Flash")
        print("\n")
        print("SCRIPT IS RUNNING")
        print("\n")
    else:
        no_flash.configure(text="Start No Flash")
        print("\n")
        print("SCRIPT IS STOPPED")
        print("\n")
    try:
        dwLocalPlayer = 0xD8A2DC
        m_flFlashMaxAlpha = 0xA41C

        pm = pymem.Pymem("csgo.exe")
        client = pymem.process.module_from_name(pm.process_handle, "client.dll").lpBaseOfDll
        while True:
            player = pm.read_int(client + dwLocalPlayer)
            if player:
                flash_value = player + m_flFlashMaxAlpha
                if flash_value:
                    pm.write_float(flash_value, float(0))
            time.sleep(1)
    except:
        no_flash.configure(text="Start No Flash")
        print("error: please read the README file If you're having trouble join my discord")
        print("\n")
######################################################################################################################
def radar_action():
    if radar_button["text"] == "Start Radar":
        radar_button.configure(text="Stop Radar")
        print("\n")
        print("SCRIPT IS RUNNING")
        print("\n")
    else:
        radar_button.configure(text="Start Radar")
        print("\n")
        print("SCRIPT IS STOPPED")
        print("\n")
    try:
        pm = pymem.Pymem('csgo.exe')
        client = pymem.process.module_from_name(pm.process_handle,
                                                'client.dll')
        clientModule = pm.read_bytes(client.lpBaseOfDll, client.SizeOfImage)
        address = client.lpBaseOfDll + re.search(rb"\x80\xB9.{5}\x74\x12\x8B\x41\x08", clientModule).start() + 6
        pm.write_uchar(address, 0 if pm.read_uchar(address) != 0 else 2)
        pm.close_process()
    except:
        radar_button.configure(text="Start Radar")
        print("error: please read the README file If you're having trouble join my discord")
        print("\n")
#######################################################################################################################
def bunny_hop():
    if bunny_hop["text"] == "Start Bunnyhop":
     bunny_hop.configure(text="Stop Bunnyhop")
     print("\n")
     print("SCRIPT IS RUNNING")
     print("\n")
    else:
        bunny_hop.configure(text="Start Bunnyhop")
        print("\n")
        print("SCRIPT IS STOPPED")
        print("\n")
    try:
        class BunnyHopper:
                dwForceJump = 0x524CFDC
                dwLocalPlayer = 0xD8A2DC
                m_fFlags = 0x104
        
                pm = pymem.Pymem("csgo.exe")
                client = pymem.process.module_from_name(pm.process_handle, "client.dll").lpBaseOfDll
    
                while True:
                    if not GetWindowText(GetForegroundWindow()) == "Counter-Strike: Global Offensive":
                        continue
    
                    if keyboard.is_pressed("space"):
                        force_jump = client + dwForceJump
                        player = pm.read_int(client + dwLocalPlayer)
                        if player:
                            on_ground = pm.read_int(player + m_fFlags)
                            if on_ground and on_ground == 257:
                                pm.write_int(force_jump, 5)
                                time.sleep(0.08)
                                pm.write_int(force_jump, 4)
                        time.sleep(0.002)
    except:
       bunny_hop.configure(text="Start Bunnyhop")
       print("error: please read the README file If you're having trouble join my discord")
       print("\n")
######################################################################################################################

# GUI
gui = Tk()
gui.title("Sleepy's hacks")
gui.geometry("800x300")

# Wallhack Button
change_button = Button(gui, text="Start Wallhack", fg="black" , command=button_action)
change_button.place(x = 100, y = 50, width=300, height=100)

#Flash button
no_flash = Button(gui, text="Start No Flash", command=no_flash)
no_flash.place(x=400, y=50, width=300, height=100)

#Radar button
radar_button = Button(gui, text="Start Radar", command=radar_action)
radar_button.place(x=400, y=150, width=300, height=100)

#Bunnyhop button
bunny_hop = Button(gui, text="Start Bunnyhop", command=bunny_hop)
bunny_hop.place(x=100, y=150, width=300, height=100)

# Text
Text = Label(gui, text="version 3.0", fg="black")
Text.place(x = 10, y = 0,width=70, height=50)

# Hyperlink
link = Label(gui, text="Github", fg="blue", cursor="hand2")
link.place(x = 500, y = 250, width=100, height=50)
link.bind("<Button-1>", lambda e: callback("https://github.com/c0dingcafe"))

# Hyperlink
link = Label(gui, text="Discord", fg="blue", cursor="hand2")
link.place(x = 200, y = 250, width=100, height=50)
link.bind("<Button-1>", lambda e: callback("https://discord.gg/Z9MxmBmKDP"))



mainloop()
