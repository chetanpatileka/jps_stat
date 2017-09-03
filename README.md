# jps_stat
###### A bash script to moniter memory and cpu details of all java programs running on current linux system.
## How to use
* Clone this repo and extract and open the folder
* Right click on ` jpsstat.sh ` file and select ` properties `
* Under ` Permissions ` tab, check the ` Allow executing file as program ` option.
* Now open this folder in terminal and enter ` ./jpsstat.sh `
* This will list the memory details and cpu use of all running java programs with live refresh.
## How to stop
* Once the script is running and displaying the details, if you want to stop the script running, press ` ctrl+c ` and then enter ` reset `
## Script details
* This uses ` jps ` command to get the list of all processes running java programs (_jvm instances_)
* Then for each _procecss_id_ obtained from jps, it runs ` jstat -gc <process_id>`
* It calculates Heap memory by adding following fields of output - 
  * ` S0U `: Survivor space 0 utilization
  * ` S1U `: Survivor space 1 utilization
  * ` EU ` : Eden space utilization
  * ` OU ` : Old space utilization
* It tracks cpu uses using ` ps -p $pid -o %cpu ` command 
* It uses ` tput cuu <# of lines> ` to refresh screen
## Requirements
* Jdk
* Linux System (Tested on Ubuntu 16.04 LTS)
* Bash version >=  4.0


## License
MIT License

Copyright (c) 2017 Amarjeet Anand

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

