# junious
A helper script written in bash that helps you download songs from YouTube using youtube-dl. 

---
## How to use it
* Download the source code and add the 'junious' Bash script to your PATH 
>(The above step is not compulsary but if you dont do this you can only use this script in the directory you have it in)

* Make a text file with the titles of the songs you want to be downloaded written in it, one song per line

* Name it whatever you want, eg., songlist

* open up a terminal window and type: junious \<name-of-the-text-file\>, eg., 'junious songlist'
 
* Wait for the download to finish

* The newly downloaded songs can be found in a folder named 'Songs' in the directory you ran the command from. 

---
## How it works
The script reads through each line in the songlist (text file) and makes a search request to YouTube for each of these songs. It downloads each of these webpages and stores them in a 'tmp' within the present working directory (this folder is automatically deleted after all the songs have been downloaded). 

It then uses grep to look for all the video ID's present in these webpages and stores them in a file called 'tmp_links' in the 'tmp' folder within the present working directory. It does this on a song by song basis. It then picks the first one from this file for each of the songs as that one is the most relevant.

It then passes the URL to youtube-dl to download the file. It uses the `-x` and `--prefer-ffmpeg` flags to extract the audio and stores it as an mp3 file. 

It also the `--user-agent` flag. I found that it doesn't work without this sometimes. More information on this can be found in the source code.

---
# More features will be added soon.
