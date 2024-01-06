# qd

Queue Downloader (QD) is a simple script for scanning remote locations and multi-threaded sequential download of files. It takes list of locations from given input file, resursively traverses directories and searches for files of given extensions.

## How to

1. Create a file with locations you want to download or search. *One Link - One Line*. (Please remember, all urls of downloaded directories must end with / (slash) character, otherwise won't work the --no-parent wget parameter and recursive search of that given location will not be performed.)

3. Execute `qd` command with requested set of parameters.

Example 1):
```
qd -e D -f qd.link
```
An input file called `qd.link` will be processed. Locations will be recursively searched for files with extensions "doc,docx,ppt,txt,xls,pdf,odp,odt"

Example 2):
```
qd -a aria2 -m 2M -n 3 -e D -f qd.link
```
An input file called `qd.link` will be processed. Locations will be recursively searched for files with extensions "doc,docx,ppt,txt,xls,pdf,odp,odt". It will be used accelerator called aria2, where the maximum speed of downloaded files will be limited to 2M/s and there will be 3 threads fetching the data in parallel.

## Dependencies

* bash (tested with 5.2.21)
* wget (tested with 1.21.4)
* supported accelerators:
  * aria2 (tested with 1.37.0)
  * axel (tested with 2.17.8)
