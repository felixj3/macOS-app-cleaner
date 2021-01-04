# MacOS Application Cleaner

## Dependencies
```
1. macOS (Bash)
```
Although all of the commands used in the script are either Bash shell built-in commands or from a Unix-like OS, the file paths that this program searches through are currently only specific to macOS machines. 

If your device uses macOS, this script should work in Bash, and may or may not work in other shells.

## Installation
1. Clone this repository and navigate to the folder
2. Run in your terminal (Bash) ```chmod 755 clean``` (this allows you to read, write, and execute this script, while allowing others to read and execute only)
3. Run in your terminal ```./clean``` to start the program

The folder can be placed anywhere on your mac, just make sure the contents of the folder stay together.

## Usage
```usage: clean [-h | -p]```
* ```-h or --help```: help
* ```-p or --pretend```: run program without actually moving files into the trash

## Motivation
After deleting applications, they often leave a bunch of files on your mac in various locations. Most of the time, those files don't take up much space, however it's possible that these leftover files take up a significant amount of space. Regardless, these files are useless if the application has been deleted.

When I look at the storage left on my mac, a ton of space is taken up by "System", which holds many files, such as your saved iMessages, as well as left over files from deleted applications. I used to search through a ton of locations on my mac in order to find leftover files and delete them in order to make more room. With this script, I only have to type in the general name of my application, and it will show me each file that roughly\* matches the name before I confirm its move to the trash bin.

<ins>**This script only moves files into your trash bin.**</ins> In case you accidentally confirmed a file to be removed, it can still be recovered by going into your trash bin. You can also look into the ```history.txt``` file to see the previous locations of files/directories the program moved.

\* For example, if you typed in the value: GitHub, the pattern the program uses is ```*github*```, matching any file/directory that contains "github". This may create unwanted side effects since you may only want to remove things related to github desktop for example, but it would move any file/directory that simply contains github in the name. You always confirm a move to trash before it occurs, and everything this program does is always reversible.

## Liability
Besides the following:
```
1. Moving certain files to trash (after your confirmation)
2. Creating a temporary file
3. Deleting that file once the program has finished
``` 
this program does not change the state of your filesystem. However, I made this program more for myself than as a product, so if you choose to use it, there are no guarantees that it will only perform the tasks it's supposed to do (move leftover files into the trash that match the application name you provide).