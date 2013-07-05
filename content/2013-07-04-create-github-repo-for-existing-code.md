Title:  Create GitHub repository for existing source code
Category: github
Tags: github, git
Author: KaChon Lei
Summary:  Notes for creating GitHub repository for existing source code

Here are the steps for creating a GitHub repository for existing source code.

**a.**  Create a repository at GitHub and get the corresponding url for it (i.e. https://github.com/kachon/oauth_example.git)

**b.**  Issue ***git init*** at local directory

**c.**  Issue ***git add .*** at local directory to stage all the files

**d.**  Issue ***git commit -m 'first commit'*** at local directory to commit all the files

**e.**  Issue ***git remote add origin https://github.com/kachon/oauth_example.git*** to attach the local repository to remote repository 

**f.**  Issue ***git pull origin master*** to pull any new files created by GitHub

**g.**  Issue ***git push origin master*** to push all files to GitHub

Done!
