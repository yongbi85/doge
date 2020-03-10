Doge

# Features
- Look at your games collection from any browser in your home
- See how it changes over time
- See what's installed on your Switch
- Showcase your collection
- Heavily uses Nut (https://github.com/blawar/nut)
- Copy from https://github.com/wowsuchdoge/doge v2.1.5 but with nsz scan enable in doge

# Setup
- Install Python 3 and Nut's dependencies
  - Make sure you are at least running Python 3.6
  - `pip3 install colorama pyopenssl requests tqdm unidecode image bs4 urllib3 flask`
  - You may need to update pip to latest version if the above command fails
- Install NodeJS LTS / 10 from https://nodejs.org/en/ (or `brew install node@10` on Mac) and restart your computer
  - Node 10, not 8, not 11
- Set your games folder root in `/nut/conf/nut.conf` (paths.scan, use / instead of \ even on Windows, ex: C:/games)
- If not on Windows, change the `PYTHON_CMD` to `python3` or whatever your python alias is
- Run start.bat (Windows) or start.sh (Mac/Linux)
- Visit the url you see in your web browser

# Docker
- Unofficial Docker image is available at https://github.com/krptg0/doge (my own docker is coming very soon, with git enable inside the docker to keep nut up to date)
- Contact krptg over Github for assistance, or open an issue directly on his repo

# Credits
- Doge
- wowsuchdoge
- Thanks to blawar, morrison22, krptg, Bob, DBZTrunks, and more!

# How To
- If you're having trouble, make sure Nut runs fine on it's own (don't run it without any params because it will rename your files)
  -  `nut.py -s` (in nut folder)
- Update checking is powered by using a db url that has update info
  - Add any db urls you want to `titleUrls` in `nut/conf/nut.conf`
- To see which Switch games you have installed, run digableinc/tinfoil (dz) on your Switch, from https://github.com/digableinc/tinfoil
  - Make sure it's configured to connect to the nut server on your computer
- To see pictures in the Grid View mode, you must enable eShop scraping / `SCRAPE_ESHOP` in `doge.config.json`
  - This will take a while, so be patient
- To change your login:
  - For the Nut server login, change `/nut/conf/users.conf` (and make sure to add a valid admin login into `doge.config.json`'s `NUT_USER`/`NUT_PASS`)
  - For Doge, see `doge.config.json`'s USERS section
- If you have a URL that you can make send you a notification, set it into `URL_NOTIFY_NEW_FILES`
  - `%msg` will be replaced with a message about which games were found (up to a few at once)
  - Pushbullet/etc gives you a URL like this so you can get notifications on your phone
- Rename your Switches that show up in the dropdown:
  - See `SWITCH_ALIASES` in the config to get from serial to alias
- Auto Unlocking just runs `nut.py --unlock-all`, so if it's not working, run that yourself from the command line and check for errors
  - You will need a populated `keys.txt`, which is not included
  - Make sure you set where you want files to go in nut.conf's "paths", by default they will be moved into sub-folders)
