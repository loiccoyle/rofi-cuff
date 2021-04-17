# rofi-cuff
<a href="./LICENSE.md"><img src="https://img.shields.io/badge/license-MIT-blue.svg"></a>

Rofi wrapper for [`cuff`](https://github.com/loiccoyle/cuff). Use the [`Jackett`](https://github.com/jackett/jackett) search API to find torrents.

[See it in action](https://imgur.com/7roVMqQ)

# Installation

### Dependencies

* [`rofi`](https://github.com/davatorium/rofi)
* [`cuff`](https://github.com/loiccoyle/cuff)
* [`jq`](https://github.com/stedolan/jq)

Of course you'll also need access to a `Jackett` server.

### Manual

You'll need to git clone this repository and place the script somwhere in your `$PATH`.
```
git clone https://github.com/loiccoyle/rofi-cuff
cd rofi-cuff
cp rofi-cuff /somewhere/in/your/PATH/
```

# Usage

`rofi-cuff` is just wrapping [`cuff`](https://github.com/loiccoyle/cuff), any options will be passed on to `cuff`.

```
$ rofi-cuff -h
Use "-" to pipe read the json Jackett response from stdin.
Otherwise, rofi-cuff passes any provided options to the main cuff command.

Query the Jackett search API from the command line.

Usage:
    cuff [OPTIONS] {search, config, indexers, categories, open}
        -h                        Show this message and exit.
        -r                        Raw output, no coloring.
        -v                        Verbosisty, up to -vv.
        -s                        Start Jackett service if not running.
        -k                        Stop Jackett service before exiting.
        -u JACKETT_URL            Jackett URL.
        -a API_KEY                Jackett API key, will query Jackett if not provided.
        -p PASSWORD               Jackett password.
```
You can also just pipe a json API response straight into `rofi-cuff` by using the '-' as the argument:
```
cuff search big buck bunny | rofi-cuff -
```
