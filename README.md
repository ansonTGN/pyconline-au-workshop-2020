# pyconline-au-workshop-2020

## For everyone:

You'll need to make sure you've signed up at https://trial.snowflake.com for an account. For best results, you should use at least an Enterprise account in AWS AP-Southeast-2, but any region should work.

## For Windows Users, or Mac users who prefer Docker:

The easiest way to get everything running tomorrow will be to use the Snowtire Docker Container:
- Download and unzip into a folder the Zip file at https://github.com/zoharsan/snowtire/archive/master.zip
- Download and install Docker Desktop from https://www.docker.com/products/docker-desktop, if you don't already have it installed.
- Configure Docker Desktop to use at least 4GB of RAM - see https://docs.docker.com/docker-for-windows/.
- At the command line, navigate to the folder you unzipped the Zip file to
- Run `docker build --pull -t snowtire .`
- Run `docker run -p 8888:8888 --name spare-0 snowtire:latest`
- Copy and paste the 127.0.0.1 URL it supplies into your browser

If this successfully loads a Jupyter notebook, you're ready to go!

## For any Windows users that don't want to use Docker:

Please download and install the Anaconda Python 3.8 (https://www.anaconda.com/products/individual#windows) distribution on your local machine. If you're familiar with Conda environments, please set one up and get it ready for use in a Jupyter notebook. 

Then, please install a number of packages on the command line as follows:
```
conda install libpython m2w64-toolchain -c msys2
conda install numpy cython -c conda-forge
conda install matplotlib scipy pandas -c conda-forgepip install ipython-sql
pip install snowflake-connector-python[pandas]
pip install --upgrade snowflake-sqlalchemy
pip install pystan
pip install fbprophet
```

## For Mac / Linux users:
Ensure you have Python 3.6 or above installed and set up a virtualenv if you prefer. You'll also want Jupyter. Then, install as follows:
```
pip install jupyter
pip install ipython-sql
pip install snowflake-connector-python[pandas]
pip install --upgrade snowflake-sqlalchemy
pip install pystan
pip install fbprophet
```
