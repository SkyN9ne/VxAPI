![Alt text](/img/icon.png?raw=true "Falcon Sandbox API Icon")

# VxWebService Python API Connector
The Falcon Sandbox Python API Connector (e.g. for [hybrid-analysis.com](https://hybrid-analysis.com)).

## Requirements

* [Python](https://python.org) >= 3.4.0+
* To install the required Python modules, please run `pip install -r requirements.txt`
* Using a Debian or Ubuntu-based OS, this can be done by running `sudo apt-get install python3-pip`. It will then be available via `pip3`
* Using Windows, this can be done automatically when installing `Python` (proper checkbox on the installer has to be checked). It should then be available via `pip` 

Versions
---

### API V2

This version has broad support for all capabilities of `VxWebService` APIv2 and much more. New features include:

* Support for API v2
* Improved application performance
* Unified and simplified CLI schema
* Bulk quick-scan and sandbox submissions
* Improved file-handling
* Test coverage

#### For example: `python3 vxapi.py scan_file C:\file-repo all`

![Alt text](/img/scan_example.png?raw=true "Falcon Sandbox API CLI Example Bulk Quick Scan")

### API V1

The legacy version utilizing the APIv1 is not supported anymore. For backwards compatibility, it is still available in the `v1` branch however.

## Usage:
---------

### Define the configuration file

Copy the `config_tpl.py` and name it as `config.py`

The configuration file specifies a triplet of API key, secret and the server:

* `api_key` (should be compatible with API v2 - so it should contain at least 60 chars)
* `server` - The full URL of the WebService instance e.g. `https://www.hybrid-analysis.com`

Please fill them with the appropriate data. You can generate a public (restricted) API key by following these instructions:
<https://www.hybrid-analysis.com/knowledge-base/issuing-self-signed-api-key>

If you have the full version of Falcon Sandbox, create any kind of API key in the admin area:
<https://hybrid-analysis.com/apikeys>

### Install Python's `requests` module if you're using python < 3.5 [python-requests](https://docs.python-requests.org/en/master/)

-- On Debian/Ubuntu and related OS's:

    sudo apt-get install python3-requests
    
or
    
    pip3 install requests
    
-- On Windows:

    pip install requests

### Install Python's `colorama` module, [pip colorama](https://pypi.org/project/colorama/)

On Debian/Ubuntu and related OS's:
    
    pip3 install colorama
    
On Windows:

    pip install colorama

### Run the connector. Use `help` or `-h` (on any API endpoint) to get to know about the various endpoint options. Use `-v` for a more verbose output.

* Depending on your API Key's privileges, you will see different options.
* A few specific actions connected with the system's state and submitting those files, are only available while using a Premium API Key.
* If you are interested in obtaining one, please contact with our [Payload Security Support](https://payload-security.com/contact)

**Help:**

    python3 vxapi.py -h
    
After choosing the `action_name`
    
    python3 vxapi.py action_name -h
    
Use the 'verbose' mode to get more wordy output

    python3 vxapi.py action_name -v

![Alt text](/img/cli_example.png?raw=true "Falcon Sandbox API CLI Example Output")

### Notes:

* Most Linux OS's have two versions of `python` installed. 
* To ensure that the program will work correctly, please use `python3`.
* On Windows after having installed `Python`, please add the parent folder to the `%PATH%` environment variable. Then use `python` to callout the script.

### FAQ

##### My API Key authorization level was updated, but VxApi is still showing the old value.

`VxApi` is caching key response data. To get the fresh one, remove the `cache/` directory's content and try re-running it.

##### How can I run tests attached to the project?

You could call `pytest` from the project's root directory. (installed testing library must be installed). `PyLint` works for linting if needed


###### License

GNU GENERAL PUBLIC LICENSE, Version 3, 29 June 2007
see the [`LICENSE.md`](https://github.com/PayloadSecurity/VxAPI/blob/master/LICENSE.md)

