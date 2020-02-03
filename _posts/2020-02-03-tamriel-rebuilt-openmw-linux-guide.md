---
layout: post
title: "Tamriel Rebuilt with OpenMW under Ubuntu Linux"
date: 2020-02-03
---


Nostalgia hit me a couple of months ago, so I decided to reinstall Morrowind under OpenMW. Since I was familiar with the story and quests,I wanted more out of the game and the setting.
[Tamriel Rebuilt](https://www.tamriel-rebuilt.org/) was the obvious solution. This amazing mod has a storied development history, with many regions in Tamriel added over the years.
Below are the steps that I followed to install the clean stack above.

1. buy the game from GOG.com or any other reputable source.
2. download the setup….exe after buying the game
3.  install openmw :
	$ sudo add-apt-repository ppa:openmw/openmw
	$ sudo apt-get update
	$ sudo apt-get install openmw openmw-launcher
4. install innoextract
	sudo apt install innoextract
5. navigate to /home/username/.local/share/openmw/data
6. copy the setup.exe file inside this folder
7. extract the game files from the installer :
	innoextract /home/username/.local/share/openmw/data/setup…..exe

8. run openmw installation wizard

9. Run openmw from an existing installation. The path is here :
	/home/username/.local/share/openmw/data/app/Data Files

10. You now have the greatest game ever installed and ready to go. But wait! We still want to install Tamriel rebuilt.

11.Go here : https://www.tamriel-rebuilt.org/content/how-install-tamriel-rebuilt . You will need two types of files, master files and data files.
	Master file location : https://www.tamriel-rebuilt.org/downloads/main-release
	Data file location : https://drive.google.com/file/d/1Ukb85nnPVeA7M-ubVZlBfAZB8_7hjMuT/view (will take awhile – 1.1gb file)

12.Extract the master file into home/username/.local/share/openmw/data/app/Data Files

13. Extract the data files in home/username/.local/share/openmw/data/app/

14. Make sure that PT_Data.bsa is in the Data Files folder. Also you should have TR_Mainland.esm, TR_OldTravels.esp, TR_Preview.esp, TR_Travels.esp, TR_Travels_(Preview_and_Mainland).esp

15. Make sure you copy and merge the sound files from your Tamriel_Data(HD) folder into your Data Files folder.

16. Now you need to register your BSA mod file. Navigate to  $HOME/.config/openmw and edit the openmw.cfg file in the top part. Next to the Morrowind Tribunal and Bloodmoon.bsa files add the mod files, like this :

fallback-archive=Morrowind.bsa
fallback-archive=Tribunal.bsa
fallback-archive=Bloodmoon.bsa
fallback-archive=PT_data.bsa
fallback-archive=TR_Data.bsa

17. edit your Morrowind.ini file under .local/share/openmw/data/app. Scroll down to line 726 and add these lines next to your archives :

Archive 0=Tribunal.bsa
Archive 1=Bloodmoon.bsa
Archive 2=PT_Data.bsa
Archive 3=TR_Data.bsa

18. Launch OpenMW and go crazy.
