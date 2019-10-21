# yahooGroupsArchiver

#### A simple python script that archives all messages from a public Yahoo Group

Yahoo! Groups will be [discontinuing most services](https://help.yahoo.com/kb/groups/SLN31010.html) as of 14/Dec/2019.

yahooGroupsArchiver archives all the files in a Yahoo! Group. 
Messages are downloaded in a JSON format, with one .json file per message.
This script supports cookie import from Firefox; to allow for archiving of private groups. 

Requirements: Python 3, with json, requests, os, time, sys, shutil, and sqlite3

Uncomment the appropriate line in the code block following line 36 to reflect you OS and Firefox profile path. 

Before each use, sign into [Yahoo! Groups](https://groups.yahoo.com) to make sure your cookies are current.


## Usage
**`python3 yahooGroupsArchiver.py <groupName> [options] [nologs]`**
where *`<groupName>`* is the name of the group you wish to archive (e.g: hypercard)

**Options**
(One only)
* *`update'* - the default., Archive all new messages since the last time the script was run
* *`retry`* - Archive any new messages, and attempt to archive any messages that could not be downloaded last time
* *`restart`* - Delete all previously archived messages and archive again from scratch

By default a log file called <groupname>.txt is created and stores information such as what messages could not be received. This is entirely for the benefit of the user: it's not needed at all by the script during any re-runs (although re-runs will append new information to the log file). If you don't want a log file to be created or added to, add the `nologs` keyword when you call the script.

## Note
Yahoo may attempt to block robots and may trottle or block sessions interacting with large numbers of messages. This is temporary, and lasts for less than 2 hours typically. 

## To do

Add support for group files and photos. 

## Credits
This code is based almost entirely on the works of [Andrew Ferguson](https://github.com/andrewferguson), and [Daniel t. ](https://github.com/danasmera). Created with consultation of Avery [Dame-Griff](http://averydame.net/) for the [Queer Digital History Project](http://queerdigital.com/)  API documentation is from the [Archive Team](http://www.archiveteam.org/index.php?title=Yahoo!_Groups) 
