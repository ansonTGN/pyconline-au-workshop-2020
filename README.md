# pyconline-au-workshop-2020

### Note that these instructions changed late on the 4th of April, 2022, due to challenges using Prophet and Pystan in 2022. 

## For everyone:

You'll need to make sure you've signed up at https://trial.snowflake.com for an account. For best results, you should use at least an Enterprise account in AWS AP-Southeast-2, but any region should work.

## For Windows Users, or Mac users who prefer Docker:

The easiest way to get everything running tomorrow will be to use the Snowtire Docker Container:
- Download and unzip into a folder the Zip file at https://github.com/zoharsan/snowtire/archive/master.zip
- Download and install Docker Desktop from https://www.docker.com/products/docker-desktop, if you don't already have it installed. **Note: As of January 2022, Docker Desktop requires a paid license for commercial use - if that affects you, use the instructions for Anaconda below**
- Configure Docker Desktop to use at least 4GB of RAM - see https://docs.docker.com/docker-for-windows/.
- At the command line, navigate to the folder you unzipped the Zip file to
- Run `docker build --pull -t snowtire .`
- Run `docker run -p 8888:8888 --name spare-0 snowtire:latest`
- Copy and paste the 127.0.0.1 URL it supplies into your browser

If this successfully loads a Jupyter notebook, you're ready to go!

## For any Windows users that don't want to use Docker:

Please download and install the Anaconda Python (https://www.anaconda.com/products/individual#windows) distribution on your local machine. If you're familiar with Conda environments, please set one up and get it ready for use in a Jupyter notebook. 

Then, please install a number of packages on the command line as follows:
```
conda install libpython m2w64-toolchain -c msys2
conda install numpy cython -c conda-forge
conda install matplotlib scipy pandas -c conda-forge
pip install ipython-sql
pip install snowflake-connector-python[pandas]
pip install --upgrade snowflake-sqlalchemy
conda install pystan==2.19.1.1
conda install -c conda-forge prophet
```

## For Mac / Linux users:
As of April 2022, installing fbprophet can be quite a bit more difficult, as it doesn't support PyStan version 3, and older PyStan versions can be quite tricky with newer versions of Python (or, at least, I think that's the issue). As a result, I now recommend Anaconda for these platforms also:
```
pip install jupyter
pip install ipython-sql
pip install snowflake-connector-python[pandas]
pip install --upgrade snowflake-sqlalchemy
conda install pystan==2.19.1.1
conda install -c conda-forge prophet
```

## For Linux users that prefer Docker:
Please follow the instructions above for Windows users, but you'll have to go without the fancy Docker Desktop GUI. If this is your preferred method, I'm going to assume that you're technical enough to do it already, but please email me with any problems.
