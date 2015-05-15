## Server Monitoring for Status Board ##

SM4SB attempts to allow system administrators to easily visualize server performance data using Panic's "Status Board" iPad app.  It's a two part solution, consisting of:
  * a [collection of shell scripts](http://smccandl.net/isu/statusboard/code) that gathers server performance data and sends it to a web service, and
  * the web service that stores the collected data where it can be found and displayed by Status Board.

|[http://www.smccandl.net/isu/statusboard/images/SM4SB\_sm.PNG](http://www.smccandl.net/isu/statusboard/images/SM4SB.PNG)|[http://www.smccandl.net/isu/statusboard/images/SM4SB\_web\_sm.PNG](http://www.smccandl.net/isu/statusboard/images/SM4SB_web.PNG)|
|:-----------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------|

## Project Goals ##

  * **2 Minute Setup** - The scripts require no configuration.  Just untar the [collection of shell scripts](http://smccandl.net/isu/statusboard/code) on your server and create one cron job
  * **Simple Integration** - After you setup the scripts, just head to the (for now, very plain) [dashboard site](http://smccandl.net/isu/statusboard/), find your server's files and copy the link for use in Status Board.

## Installation ##

  1. Download [the code](http://www.smccandl.net/isu/statusboard/code/) to your server
  1. Decide where it should live, like /home/me/scripts
```
  $ cd /home/me/scripts
  $ tar xvf /downloads/sm4sb_v1.0.tar
```
  1. Copy scripts you want to enable from "off" folder to "on" folder
  1. Setup cron job to run every 5 mins (using crontab -e)
```
  */5 * * * * cd /home/me/scripts/sm4sb; ./gather.sh
```
  1. Wait 5 mins for data to arrive
  1. Grab your iPad and point Safari to  [the dashboard](http://smccandl.net/isu/statusboard/)
  1. Copy the link of one of your CSVs from the dashboard
  1. Switch to Status Board and drag a new chart to the design space
  1. Status Board should ask if you want to use the copied link.

## Help ##

**It's alpha code** so please consider this a test.  Questions and ideas, email help@smccandl.net.

## Future Plans ##

  * Threshold-based alerting
  * More types of collected data
  * User login?
  * Nicer dashboard