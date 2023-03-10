# Raven site
The RAVEN site has two parts: a flask server (raven-server) and an html + js front-end (raven-site). The front end sends requests to the flask server specifying the criteria for generating the RAVEN problem. Then the server generates the problem. This guide will instruct you on how to install both.

## Front end
1. *Install:* Clone the RAVEN site from [here](https://github.com/victorvikram/raven-site): `git clone <url>`
2. *Run:* Open `index.html`(the site will only work if you also run the back end)

## Back end
### Install
1. Clone the RAVEN server from [here](https://github.com/victorvikram/raven-server): `git clone <url>`
2. If you don't already have python and `pip`, you can install it [here](https://www.python.org/). Alternatively, you can install [Anaconda](http://anaconda.com/) which comes with many data science packages preinstalled. 
3. You may need to add `pip` and `python` to the system path if the installer didn't do that automatically. This allows you to run `pip` and `python` commands from the command line without specifying the full path ([here](https://datatofish.com/add-python-to-windows-path/) are example instructions for Windows, a google search will provide instructions for other OSes).
4. From the root directory of the RAVEN server, run `pip install -r requirements.txt`. This installs the necessary python packages.

### Run
1. From the RAVEN server root directory, first you need to set an environment variable. Different systems accomplish this differently:
*Powershell*: `$env:FLASK_APP = "app"`
*Cmd*: `set FLASK_APP=app`
*Bash*: `export FLASK_APP=app`
2. Then, run `flask run -h localhost -p 5000`. This runs the flask server on the port `5000`, which is where the front end will be sending its requests. If you must change the address of the server (not recommended) you will need to change all instances of the string `localhost:5000` in the file `static/js/main.39a7fb9c.js` to the new server address `<ADDRESS>:<PORT>`.
And that's all!
