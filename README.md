# data-covid19-sfbayarea
Processes for sourcing data for the Stop COVID-19 SF Bay Area dashboard, which you can find [here](https://stop-covid19-sfbayarea.netlify.com/), or [on GitHub](https://github.com/sfbrigade/stop-covid19-sfbayarea).  
**We are looking for feedback**! Did you come here looking for a data API? Do you have questions, comments, or concerns? Don't leave yet - let us know how you are using this project and what you'd like to see implemented. Please leave us your two cents over in Issues under [#101 Feedback Mega Thread](https://github.com/sfbrigade/data-covid19-sfbayarea/issues/101).

## Installation
This project requires Python 3 to run. It was built specifically with version `3.7.4`, but it may run with other versions. However, it does take advantage of insertion-ordered dictionaries which are only reliable in `3.7+`.
To install this project, you can simply run `./install.sh` in your terminal. This will set up the virtual environment and install all of the dependencies from `requirements.txt` and `requirements-dev.txt`. However, it will not keep the virtual environment running when the script ends. If you want to stay in the virtual environment, you will have to run `source env/bin/activate` separately from the install script.

## Running the scraper
To run the scraper, you can use the run script by typing `sh run_scraper.sh` into your terminal. This will enable the virtual environment and run `scraper.py`. Once again, the virtual environment will not stay active after the script finishes running. If you want to run the scraper without the run script, enable the virtual environment, then run `python3 scraper.py`.

## Data Model
The following sections document the differences between the counties in the common data model (see `data_models` directory) which we will see as we begin to get data from them.

### Ages

Please make sure to use the following age brackets for the different counties. Note that the brackets may also vary by whether you are scraping cases or deaths data:


#### San Francisco
##### Cases
    "age": [
        {"group": "18_and_under", "raw_count": -1 },
        {"group": "18_to_30", "raw_count": -1 },
        {"group": "31_to_40", "raw_count": -1 },
        {"group": "41_to_50", "raw_count": -1 },
        {"group": "51_to_60", "raw_count": -1 },
        {"group": "61_to_70", "raw_count": -1 },
        {"group": "71_to_80", "raw_count": -1 },
        {"group": "81_and_older", "raw_count": -1}
        ]
##### Deaths
Data broken down by gender is not available on the json files, only on the dashboard.


#### Alameda
##### Cases
    "age": [
        {"group": "18_and_under", "raw_count": -1 },
        {"group": "18_to_30", "raw_count": -1 },
        {"group": "31_to_40", "raw_count": -1 },
        {"group": "41_to_50", "raw_count": -1 },
        {"group": "51_to_60", "raw_count": -1 },
        {"group": "61_to_70", "raw_count": -1 },
        {"group": "71_to_80", "raw_count": -1 },
        {"group": "81_and_older", "raw_count": -1 },
        {"group": "Unknown", "raw_count": -1 }
        ]
##### Deaths
Data broken down by gender is not available.


#### Sonoma
##### Cases
    "age": [
        {"group": "0_to_17", "raw_count": -1 },
        {"group": "18_to_49", "raw_count": -1 },
        {"group": "50_to_64", "raw_count": -1 },
        {"group": "65_and_older", "raw_count": -1 },
        {"group": "Unknown", "raw_count": -1 }
        ]
##### Deaths
Data broken down by gender is not available.


#### Santa Clara
##### Cases
    "age": [
        {"group": "20_and_under", "raw_count": -1 },
        {"group": "21_to_30", "raw_count": -1 },
        {"group": "31_to_40", "raw_count": -1 },
        {"group": "41_to_50", "raw_count": -1 },
        {"group": "51_to_60", "raw_count": -1 },
        {"group": "61_to_70", "raw_count": -1 },
        {"group": "71_to_80", "raw_count": -1 },
        {"group": "81_to_90", "raw_count": -1 },
        {"group": "90_and_older", "raw_count": -1 },
        {"group": "Unknown", "raw_count": -1 }
        ]
##### Deaths
    "age": [
        {"group": "20_and_under", "raw_count": -1 },
        {"group": "21_to_30", "raw_count": -1 },
        {"group": "31_to_40", "raw_count": -1 },
        {"group": "41_to_50", "raw_count": -1 },
        {"group": "51_to_60", "raw_count": -1 },
        {"group": "61_to_70", "raw_count": -1 },
        {"group": "71_to_80", "raw_count": -1 },
        {"group": "81_to_90", "raw_count": -1 },
        {"group": "90_and_older", "raw_count": -1 }
        ]        


#### San Mateo
##### Cases
    "age": [
        {"group": "0_to_19", "raw_count": -1 },
        {"group": "20_to_29", "raw_count": -1 },
        {"group": "30_to_39", "raw_count": -1 },
        {"group": "40_to_49", "raw_count": -1 },
        {"group": "50_to_59", "raw_count": -1 },
        {"group": "60_to_69", "raw_count": -1 },
        {"group": "70_to_79", "raw_count": -1 },
        {"group": "80_to_89", "raw_count": -1 },
        {"group": "90_and_older", "raw_count": -1 }
        ]  
##### Deaths
    age": [
        {"group": "0_to_19", "raw_count": -1 },
        {"group": "20_to_29", "raw_count": -1 },
        {"group": "30_to_39", "raw_count": -1 },
        {"group": "40_to_49", "raw_count": -1 },
        {"group": "50_to_59", "raw_count": -1 },
        {"group": "60_to_69", "raw_count": -1 },
        {"group": "70_to_79", "raw_count": -1 },
        {"group": "80_to_89", "raw_count": -1 },
        {"group": "90_and_older", "raw_count": -1 }
        ]  


#### Contra Costa
##### Cases
    age": [
        {"group": "0_to_20", "raw_count": -1 },
        {"group": "21_to_40", "raw_count": -1 },
        {"group": "41_to_60", "raw_count": -1 },
        {"group": "61_to_80", "raw_count": -1 },
        {"group": "81_to_100", "raw_count": -1 }
        ]
##### Deaths
Data broken down by gender is not available.


#### Marin
##### Cases and Deaths
    age": [
        {"group": "0_to_18", "raw_count": -1 },
        {"group": "19_to_34", "raw_count": -1 },
        {"group": "35_to_49", "raw_count": -1 },
        {"group": "50_to_64", "raw_count": -1 },
        {"group": "65_and_older", "raw_count": -1 }
        ]



#### Solano
##### Cases and Deaths
    age": [
        {"group": "0_to_18", "raw_count": -1 },
        {"group": "19_to_64", "raw_count": -1 },
        {"group": "65_and_older", "raw_count": -1 }
        ]


#### Napa
##### Cases
    age": [
        {"group": "0_to_17", "raw_count": -1 },
        {"group": "18_to_49", "raw_count": -1 },
        {"group": "50_to_64", "raw_count": -1 },
        {"group": "Over_64", "raw_count": -1 }
        ]
##### Deaths
Data broken down by gender is not available.
## Development

We use CircleCI to lint the code and run tests in this repository, but you can (and should!) also run tests locally.

The commands described below should all be run from within the virtual environment you’ve created for this project. If you used `install.sh` to get set up, you’ll need to activate your virtual environment before running them with the command:

```sh
$ source env/bin/activate
```

If you manage your environments differently (e.g. with Conda or Pyenv-Virtualenv), use whatever method you normally do to set up your environment.

### Tests

You can run tests using `pytest` like so:

```sh
# In the root directory of the project:
$ python -m pytest -v .
```

### Linting and Code Conventions

We use Pyflakes for linting. Many editors have support for running it while you type (either built-in or via a plugin), but you can also run it directly from the command line:

```sh
# In the root directory of the project:
$ pyflakes .
```

We also use type annotations throughout the project. To check their validity with Mypy, run:

```sh
# In the root directory of the project:
$ mypy .
```
