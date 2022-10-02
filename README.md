# :ship: Titanic Model

[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-360/)


## :memo: Description

Just having fun with the [Titanic Kaggle competition](https://www.kaggle.com/competitions/titanic)!

The model aims to predict the survival probability of the Titanic passengers.

Using GitHub Actions, the model is then uploaded on [Gemfury](https://fury.co/) to be latter used by a web service app.

There are four steps for this repo:

* Fetch the data: we download the Titanic competition data from [Kaggle](https://www.kaggle.com/).
* Train the model: we then train the model to prediction survivability of the different passengers.
* Test the model: we run several unit tests to ensure the model is predicting the way we want.
* Build & publish the model: we then build a Python package that we publish on a private repository in Gemfury.

## :computer: How to run it locally

I ran this code using `python 3.10.7`. To install it on your computer and manage several versions of python I recommend using [pyenv](https://github.com/pyenv/pyenv).

You can check this [tutorial](https://realpython.com/intro-to-pyenv/) over pyenv.

Once the installation process is over, simply run:

```
pyenv install 3.10.7
```

Then use the `global` command to make it available anywhere on you machine:

```
pyenv global 3.10.7
```

You can then use the `venv` python virtual environment function to create a `venv` in this folder:

```
python -m venv .venv/name-of-your-venv
```

That you can activate using:
```
source .venv/name-of-your-venv/bin/activate
```
Then you can install [tox](https://tox.wiki/en/latest/index.html#) by running:
```
pip install tox
```
The different steps explained in the description are then performed by different tox commands.
But first you need to set up three `environment variables`:
```
export KAGGLE_USERNAME=your-kaggle-username
export KAGGLE_KEY=your-kaggle-key
export GEMFURY_PUSH_URL=your-gemfury-url
```
For the record, here is the format of you Gemfury URL:
```
https://TOKEN@push.fury.io/your-profile-name/
```
For the Kaggle credentials you can also download a `kaggle.json` file from your profile that you can put in a `~/.kaggle` directory.
