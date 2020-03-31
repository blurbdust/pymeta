# pymeta
![](https://img.shields.io/badge/Python-3.6+-blue.svg)&nbsp;&nbsp;
![](https://img.shields.io/badge/License-GPL%203.0-green.svg)


Pymeta is a Python3 rewrite of the tool [PowerMeta](https://github.com/dafthack/PowerMeta), created by [dafthack](https://twitter.com/dafthack) in PowerShell. It uses specially crafted search queries to identify and download the following file types (pdf, xls, xlsx, csv, doc, docx, ppt, pptx) from a given domain using Google and Bing scraping. Once downloaded, metadata is extracted from these files using Phil Harvey's [exiftool](https://sno.phy.queensu.ca/~phil/exiftool/) and added to a ```.csv``` report. Metadata is a common place for penetration testers to find internal domain names, usernames, software/version numbers, and help identify an organization's naming convention.

Pymeta can also be pointed at a directory to extract metadata from files manually downloaded using the ```-dir``` command line argument. See the [Usage](#Usage), or [All Options](#All-Options) section for more information. 


## Install
* PyPi (last release)
```
pip3 install pymetadata
```

* GitHub (latest code)
```
git clone https://github.com/m8r0wn/pymeta
cd pymeta
python3 setup.py install
```

## Usage
* Search Google and Bing for files within example.com and extract metadata to a csv report:<br>
```pymeta -d example.com```

* Extract metadata from files within the given directory and create csv report:<br>
```pymeta -dir Downloads/```


## All Options
```
Target Options:
  -d DOMAIN             Target domain
  -dir FILE_DIR         Pre-existing directory of files

Search Options:
  -s {google,bing,all}  Search engine(s) to scrape (Default: all)
  -m MAX_RESULTS        Max results per file type, per search engine (Default: 50)
  -j JITTER             Seconds between search requests (Default: 2)

Download Options:
  --stealth             Use the wayback mahcine as a proxy for file downloads

Output Options:
  -o OUTPUT_DIR         Path to store PyMeta's download folder (Default: ./)
  -f FILENAME           Custom report path/name.csv (Optional)
  --debug               Show links as they are collected during scraping
```
    
## Credit
- Beau Bullock [(@dafthack)](https://twitter.com/dafthack) - [https://github.com/dafthack/PowerMeta](https://github.com/dafthack/PowerMeta)
- Phil Harvey - [https://sno.phy.queensu.ca/~phil/exiftool/](https://sno.phy.queensu.ca/~phil/exiftool/)
