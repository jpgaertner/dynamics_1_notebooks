##### How to install python and jupyter notebook: #####

1. Download and install Miniconda from

https://docs.conda.io/en/latest/miniconda.html

and tick the 'add to path' button during the installation.

2. Open the terminal and type

conda install jupyter notebook

3. For running these scripts, you need to have several packages installed.
In your terminal, type

conda install xarray
conda install matplotlib
conda install cartopy



##### How to download this folder: #####

1. Download and install git from

https://git-scm.com/downloads

You have to restart your terminal after installing git to be able to use it from there.

2. Get a github account

3. Set up git by typing

git config --global user.name your_user_name
git config --global user.email your_email

in the terminal (replace your_user_name and your_email with your actual user name and email)

4. In the dynamics_1_notebooks folder on github, click on fork -> create a new fork (button on the top right)

5. The folder is now in your github account. On the top left it should say your_user_name/dynamics_1_notebooks.
Click on code (green button) and copy the https link. In your terminal, type

cd Documents
git clone insert_link_here
cd dynamics_1_notebooks
jupyter notebook

(replace insert_link_here with the link you copied)

Of course you can modify the files locally as you want. However, if you add or change something
and you think it could be useful or interesting to others, it would be nice if you uploaded it.
Here is how you do that:

1. Stage the files you want to upload by typing

git add file

(replace file with the name of the file you want to upload)
You can do this for multiple files.

2. Commit the staged files by typing 

git commit -m "comment"

(replace comment by a short (i.e. 50 charakters or less) description of what you did)
Git commit is for all the files you staged via git add, therefore also your comment is the same
for all the files. If you want to have different comments for different files, you need to individually
stage and commit them one after the other

3. Push the commited files to github by typing 

git push

You will now have to connect to github.

4. On the github website, you should now see 'This branch is 1 commit ahead of jpgaertner:main'.
Click on contribute -> open pull request (right next to it)
Leave a comment on what you did or more importantly why, if it is not obvious (optional)



##### How to download and analyse additional data (optional): #####

1. Create a Copernicus account at 
https://cds.climate.copernicus.eu/user/register?destination=%2F%23!%2Fhome

2. Go to https://cds.climate.copernicus.eu/api-how-to and copy the key after signing in.
type the following in the terminal and insert your key as YOURKEY:

{
  echo 'url: https://cds.climate.copernicus.eu/api/v2'
  echo 'key: YOURKEY'
  echo 'verify: 0'
} > ~/.cdsapirc

This creates the file ~/.cdsapirc with your API key, which is necessary to use the CDS API.
You can check if the file is created corretly by using

more ~/.cdsapirc

A correct file will look like

url: https://cds.climate.copernicus.eu/api/v2
key: 12345:a99b9c9d-9e99-9999-9999-fg99h9i99j9k
verify: 0

3. install the cdsapi client via

pip install cdsapi

4. Now the cdsapi client can be used, i.e. the line
import cdsapi
will work.

5. Use the notebook '0. download data to file (optional)'
