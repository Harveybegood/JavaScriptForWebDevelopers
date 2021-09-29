# JavaScriptForWebDevelopers
Create a new Repository on the command line
- echo "# Javascript for web developers" >> readme.md
- git init 
- git add readme.md
- git commit -m "first commit"
- git remote add origin https://github.com/Harveybegood/javascriptfordevelopers.git
- or git remote add origin git@github.com:harveybegood/javascriptfordevelopers.git
- git push -u origin master

Push an existing reposiroty from the command line
- git remote add origin https://github.com/harveybegood/javascriptfordevelopers.git
- or git remote add origin git@github.com:harveybegood/javascriptfordevelopers.git
- git push -u origin master

Support for password authentication was remove since August/13/20221. git operations has to use personal access token instead.
- git remote set-url origin https://<githubtoken>@github.com/<username>/<repositoryname>.git
