python packages that need to be installed
(can be done by typing e.g. 'pip install xarray' in the command line)

xarray
matplotlib
cartopy
numpy



if you want to download and analyse additional data (using '0. download data to file (optional)'),
you need to

1. create a Copernicus account at 
https://cds.climate.copernicus.eu/user/register?destination=%2F%23!%2Fhome

2. go to https://cds.climate.copernicus.eu/api-how-to and copy the key after signing in.
type the following in the command line and insert your key as YOURKEY

{
  echo 'url: https://cds.climate.copernicus.eu/api/v2'
  echo 'key: YOURKEY'
  echo 'verify: 0'
} > ~/.cdsapirc

this creates the file ~/.cdsapirc with your API key, which is necessary to use the CDS API.
you can check if the file is created corretly by using more ~/.cdsapirc
a correct file will look like

url: https://cds.climate.copernicus.eu/api/v2
key: 12345:a99b9c9d-9e99-9999-9999-fg99h9i99j9k
verify: 0

3. install the cdsapi client via
pip install cdsapi 
or
conda install cdsapi

4. now the cdsapi client can be used, i.e. the line
import cdsapi
will work