# CHALLENGE 1
## Information
    Commands: file, exiftool
Check from the 'file' command if it is really .jpg file. Then to look for the files info or details I used the 'exiftool' command. In the exiftool I found out long strings. <br>
![1](week1/Challenge1/1.jpg) <br>
Trying a random method of converting those strings from base64 and got the flag.
(used this link https://www.base64decode.org/)

    Flag: picoCTF{the_m3tadata_1s_modified}

## Matryoshka Doll
    Commands: file, binwalk, binwalk -e, cat
By using 'binwalk' command, we can see that is has hidden zip files in it. Use 'binwalk -e' command to unzip the files. <br>
![](week1/Challenge1/2.1.jpg) <br>
Proceed with the same procedure till you get a text file. <br>
![](week1/Challenge1/2.2.jpg) <br>
Read the text file. <br>
![](week1/Challenge1/2.3.jpg) <br>

    Flag: picoCTF{96fac089316e094d41ea046900197662}

## tunn3l v1s10n
    Commands:file, xxd, mv, binwalk
Using the file command we get nothing useful. Type 'xxd' command and there we get the initials as 'BM' which denotes a bitmap file. Change the extension of the file by 'mv' command and try to open it. Nothing happens <br>
![](week1/Challenge1/3.1.jpg) <br>
Open the hex values of the given file. (used this site for hex values https://hexed.it/) <br>
![](week1/Challenge1/3.2.jpg) <br>
Download a random bitmap image from the browser and compare the initial hex values. <br>
![](week1/Challenge1/3.3.jpg) <br>
Make the required changes in the hex values by comparing both the files. <br>
![](week1/Challenge1/3.4.jpg) <br>
Try to open the image and the image opens but we do not get a correct flag. <br>
![](week1/Challenge1/3.5.jpg) <br>
Using the exiftool look for the details of the file. We can observe a huge difference in the image height ad width. <br>
![](week1/Challenge1/3.6.jpg) <br>
Open python idle and convert image height and width into hex values and find it in the hex values of the file. <br>
![](week1/Challenge1/3.7.jpg) <br>
Try all sorts of hex values for the image height till you observe something else. <br>
![](week1/Challenge1/3.8.jpg) <br>
And yesss... U got the flag <br>
![](week1/Challenge1/3.9.jpg)

    Flag: picoCTF{qu1t3_a_v13w_2020}

## MacroHard WeakEdge
    Commands: file, unzip, cat
Use the usual 'file' command. Unzip the .pptm file. <br>
![](week1/Challenge1/4.1.jpg) <br>
In the last there is a file called hidden. Read the file and you'll get some chracters. Try decoding it from base64.
(used this link https://www.base64decode.org/).... Yess you got the flag. <br>
![](week1/Challenge1/4.2.jpg) <br>

    Flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}

## Enhance!
    Commands: binwalk, mv
Changed the name of the downloaded file as per my convenience. Use the command 'binwalk' to check for the file type and extensions. Use 'mv' command to change the file extension. <br>
![](week1/Challenge1/5.1.jpg) <br>
Open the .xml file in notepad and notice it carefully. It is a flag. <br>
![](week1/Challenge1/5.2.jpg)<br>

    Flag: picoCTF{3nh4nc3d_24374675}

## Advanced Potion Making
    Commands: file, exiftool, xxd
Tried 'file' and 'exiftool' but got no information. Look for the hex values by 'xxd' command.The initial hex values are similar to that of the .png file (source : https://en.wikipedia.org/wiki/List_of_file_signatures). <br>
![](week1/Challenge1/6.1.jpg) <br>
Change the hex values to its default value. Look for its height and width and change it accordingly. <br>
![](week1/Challenge1/6.2.jpg) <br>
![](week1/Challenge1/6.5.jpg) <br>
![](week1/Challenge1/6.3.jpg) <br>
Nothing is useful when we open the file. Use online stegsolve platforms and use its tools.
(https://georgeom.net/StegOnline/image) <br>
![](week1/Challenge1/6.4.jpg) <br>

    Flag: picoCTF{w1z4rdry}

## File Types
    Commands: file, mv, binwalk, lzip, lzop, lzma, xd
Using the 'file' command we get to know the file is a shell archive. Copy the file and rename the file with extension .sh. Execute the file. There is a uudecode error. <br>
![](week1/Challenge1/7.1.jpg) <br>
Install uudecode. After installing it works.. <br>
![](week1/Challenge1/7.2.jpg) <br>
Check for the list of files. There is a new file 'flag' in it. Chech its extension using 'file' command. It is an archive file so extract its content using 'binwalk' command. There are multiple compressions so install libraries if not there and keep decompressing. Also rename the file if there is an error occuring due to unknown suffix. <br>
![](week1/Challenge1/7.3.jpg) <br>
![](week1/Challenge1/7.4.jpg) <br>
![](week1/Challenge1/7.5.jpg) <br>
![](week1/Challenge1/7.6.jpg) <br>
![](week1/Challenge1/7.7.jpg) <br>
Ascii text is given in the last file. Convert it from base64 or hex values to get the flag. Hex conversion works. <br>

    Flag: picoCTF{f1len@m3_m@n1pul@t10n_f0r_0b2cur17y_3c79c5ba}

## HIDEME
    Commands: file, exiftool, binwalk, unzip
Start with the regular and most common commands. By 'binwalk' command we get to know a there is another image inside this image in a zip file. <br>
Unzip it and go to the secret folder to open the image. <br>
![](week1/Challenge1/8.1.jpg) <br>
![](week1/Challenge1/8.2.jpg) <br>
![](week1/Challenge1/8.3.jpg) <br>
![](week1/Challenge1/8.4.jpg) <br>

    Flag: picoCTF{Hiddinng_An_imag3_within_@n_ima9e_96539bea}

## MSB
    Commands: python3, ls
Firstly I tried all sorts of methods like using commands that are used for steganography and visiting online platforms for steganography. <br>
On the online steganography platforms, solving via LSB is given but not for MSB. I searched for the code online to get the data through MSB(as the name of the challenge says) and got this github link (https://github.com/Pulho/sigBits). <br>
![](week1/Challenge1/9.1.jpg) <br>
I copied the code in my vscode and executed it on my terminal as per the given instructions. <br>
![](week1/Challenge1/9.2.jpg) <br>
Then I opened the file and by the 'find' method found the flag. <br>
![](week1/Challenge1/9.3.jpg) <br>

    Flag: picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_ee3cb4d8}

## Extensions
    Commands: file, mv
Using the 'file' command know about the extension of the file and change it using 'mv' command if different. <br>
![](week1/Challenge1/10.1.jpg) <br>
![](week1/Challenge1/10.2.jpg) <br>

    Flag: picoCTF{now_you_know_about_extensions}


# CHALLENGE 2 - Try Hack Me
## TIP - OFF
Copy the URL given and use 'wget' command to save the file. <br>
![](week1/Challenge2/TryHackMe/1.1.jpg) <br>
By the given instructions we have to find out the information of the file. Use 'exiftool' to do so. <br>
![](week1/Challenge2/TryHackMe/1.2.jpg)

    Flag: SakuraSnowAngelAiko

## RECONNAISSANCE
Search the username on the web and you'll find two accounts for the same username. One for github and the other of twitter. <br>
![](week1/Challenge2/TryHackMe/2.1.jpg) <br>
Open the github account and look for the repositories. Apart from the repos that are forked look at the remaining ones. There is a private key in the PGP repo. Copy the raw data URL. <br> 
![](week1/Challenge2/TryHackMe/2.2.jpg) <br>
Curl the URL and proceed with 'gpg' to manage the PGP keys. <br>
![](week1/Challenge2/TryHackMe/2.3.jpg)<br>

    Flag 1: SakuraSnowAngel83@protonmail.com

Now open the twitter profile of the given username. 
Look at the posts and there you can find the full name of the attacker. <br>
![](week1/Challenge2/TryHackMe/2.4.jpg) <br>

    Flag 2: Aiko Abe

## UNVEIL
Look for the repos serial wise. Open the ETH repo and check for commits. <br>
![](week1/Challenge2/TryHackMe/3.1.jpg) <br>
Look for the data on the web. <br>
![](week1/Challenge2/TryHackMe/3.2.jpg) <br>

    Flag 1: Ethereum
    Flag 2: 0xa102397dbeeBeFD8cD2F73A89122fCdB53abB6ef
Go to https://etherscan.io/ to scan for wallet id <br>
![](week1/Challenge2/TryHackMe/3.4.jpg) <br>
![](week1/Challenge2/TryHackMe/3.5.jpg) <br>

    Flag 3: Ethermine
    Flag 4: Tether

## TAUNT
Look at the username of the twitter account previously found. <br>
![](week1/Challenge2/TryHackMe/4.1.jpg) <br>

    Flag 1: SakuraLoverAiko
Look at the hint of the question. There you'll find the required URL. <br>
![](week1/Challenge2/TryHackMe/4.2.jpg) <br>

    Flag 2: http://deepv2w7p33xa4pwxzwi2ps4j62gfxpyp44ezjbmpttxz3owlsp4ljid.onion
Given the hint, regitser yourself on https://wigle.net/ and look for advanced search. Enter the SSID of the home wifi to get BSSID. <br>
![](week1/Challenge2/TryHackMe/4.3.jpg) <br>

    Flag 3: 84:AF:EC:34:FC:F8

## HOMEBOUND
Search the nearest airport to the given location in the post. <br>
![](week1/Challenge2/TryHackMe/5.3.jpg) <br>
![](week1/Challenge2/TryHackMe/5.4.jpg) <br>

    Flag 1: DCA
Look at the post of the attacker's ladt layover. Web search for the 'Sakura Lounge'. <br>
![](week1/Challenge2/TryHackMe/5.5.jpg) <br>
![](week1/Challenge2/TryHackMe/5.6.jpg) <br>

    Flag 2: HND
Web search the given image and you'll find the name of the city is Niigata in Japan. Open the google maps and look fot it. Move towards the right and you will see the lake asked. <br>
![](week1/Challenge2/TryHackMe/5.2.jpg) <br>

    Flag 3:Lake Inawashiro
As per the wifi details given in the last question the city mentioned is 'HIROSAKI' <br>
![](week1/Challenge2/TryHackMe/5.1.jpg) <br>

    Flag 4: Hirosaki


# CHALLENGE 2 - Gralhix
## EXERCISE #006
Using the google lens look for the exact image. There is a news report with the same image of bomb blast in Iraq. <br>
(source: https://www.iraqinews.com/iraq-war/8-people-killed-wounded-bomb-blast-near-shops-south-baghdad/) <br>

    ANSWER: NO
## EXERCISE #004
Web search the given image. You'll get the a wix site with the exact image. <br>
(source: https://oanresort.wixsite.com/chuuk/about) <br>
Search for the island on which Oan Resort is there and look for its coordinates. <br>
Go to Google Earth and set the island exactly given in the image to now the direction of the camera. The position at which we have stopped is around 320 deg from north. <br>
![](week1/Challenge2/Gralhix/4.1.jpg) <br>

    ANSWER: a) Oan Resort
            b) 7.4469° N, 151.7473° E
            c) North West
## EXERCISE #003
Web search the event and there will be several news articles on the same. One of them tells us about the place. <br>
(source: https://www.tccb.gov.tr/en/news/542/74924/somali-cumhurbaskani-muhammed-cumhurbaskanligi-kulliyesinde) <br>
![](week1/Challenge2/Gralhix/3.1.jpg)

    ANSWER: a) Presidential Complex, Turkey
            b) 39.9308°N 32.7989°E
## EXERCISE #014
Search the date, time for the earthquake details. Got https://www.romania-insider.com/5-3-magnitude-earthquake-shakes-romania-friday-night news article which mentions about the earthquake. <br>
![](week1/Challenge2/Gralhix/14.1.jpg) <br>
Search for the white building in the video to get the place and verify the place with the news article. The place is Artrium (Chisinau, Moldova). <br>
![](week1/Challenge2/Gralhix/14.2.jpg) <br>
![](week1/Challenge2/Gralhix/14.3.jpeg) <br>
Make exactly the same scene on Google Earth to get the coordinates. <br>
![](week1/Challenge2/Gralhix/14.4.jpg) <br>

    ANSWER: a) 5.6
            b) 47°00'56"N 28°51'14"E
## EXERCISE #026
Search the images serial wise. This will help to tell the journey as the pictures seem to be from the gallery of the person according to the file names. <br>
First Image is of Chorsu Bazaar, Tashkent, Uzbekistan. <br>
![](week1/Challenge2/Gralhix/IMG_2597.jpg) <br>
Second Image is infront of the Anhor Lokomotiv Park, Tashkent, Uzbekistan. <br>
![](week1/Challenge2/Gralhix/IMG_2626.jpg) <br>
Finding the place in the third image is difficult. There are many clues but the final one is 'rent a car'. Search for it in google street view in Tashkent. Try to look for the shop next to wide roads. The shop we are looking for is Orient rent a car. Look at the street view of it and you'll find the required place.<br>
![](week1/Challenge2/Gralhix/26.1.jpg)<br>
Next we are supposed to look at the nearest railway station to this place. Search for it.<br>
![](week1/Challenge2/Gralhix/26.2.jpg)<br>
![](week1/Challenge2/Gralhix/26.5.jpg)<br>
Fourth place isn't easy to find. There are no landmarks given in the picture. I searched for 'yellow cars near Tashkent Uzbekistan' and I got this.<br>
![](week1/Challenge2/Gralhix/26.3.jpg)<br>
Samarkand.....Interesting. Next I searched for parking areas in Samarkand and looked at almost all of them just next to the road.<br>
![](week1/Challenge2/Gralhix/26.4.jpg)<br>
![](week1/Challenge2/Gralhix/26.6.jpg)<br>
![](week1/Challenge2/Gralhix/26.7.jpg)<br>

    ANSWERS: a) Stantsiya Tashkent Station
             b) On foot in all the other images
             c) Afrosiyob Train
             d) 210 km/hr
             e) 11.3 + 332 = 343.3 km



