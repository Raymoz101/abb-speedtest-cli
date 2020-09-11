# abb-speedtest [![dependencies](https://david-dm.org/lukealford/abb-speedtest-cli/status.svg)](https://david-dm.org/lukealford/abb-speedtest-cli) <a href="https://codeclimate.com/github/lukealford/abb-speedtest-cli/maintainability"><img src="https://api.codeclimate.com/v1/badges/34a78004c17aa3757568/maintainability" /></a>

A CLI tool for running https://speed.aussiebroadband.com.au  in a headless environment built with nodejs

Chrome is required as a main dependencie as I'm using [puppeteer-core](https://github.com/GoogleChrome/puppeteer) and it requires it preinstalled.


**Setup**

Install nodejs 8.5.0+

Clone & Install dependencies
```
git clone https://github.com/lukealford/abb-speedtest-cli.git
npm install -g
```


## Basic usage

Run using `abb-speedtest`


```
-----------Results-----------
Date: 4/12/2019 6:10:06 pm
Server Melbourne
Ping 29 ms
Jitter 4 ms
Download 47.5 Mbps
Upload 17.5 Mbps
-----------------------------

```

## Options


```
Usage: abb-speedtest [options]

Runs a speedtest using speed.aussiebroadband.com.au

Options:
  -V, --version            output the version number
  -l, --location [Sydney] [optional]    use specific server location
  -q, --quiet [optional]   silences the progress console output messages (errors still outputed)
  -h, --hide [optional]  disables result reporting to ABB
  -j, --json [optional]    return json
  -c, --csv [optional]     return csv format
  -d, --dcsv [optional]    return csv format in speedtest-cli shape (non-save flow only)
  -s, --save [optional]    saves format to user\Documents\abb-speedtests
  -o, --output [optional]  overwrites output location
  -h, --help               output usage information

```


### Dependencies

```json

    "chrome-launcher": "^0.10.5",
    "commander": "^2.20.0",
    "puppeteer-core": "^1.14.0",
    "request": "^2.88.0",
    "store": "^2.0.12"

```

## Docker setup and usage

Instead of installing all components directly, you can also build a Docker container like this:
```
docker build --tag=abb-speedtest .
```

Then to run it:
```
docker run --rm abb-speedtest
# Optionally, include parameters like this:
docker run --rm abb-speedtest --json
# You can also set the Docker container timezone manually like this:
docker run --rm -e TZ=Australia/Perth abb-speedtest
```

In these cases, you do not need to install any dependencies, apart from having a working Docker system.

