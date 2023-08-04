# vs code and git 
### keeping track of vs code and git issues here 

## "Error: connect ECONNREFUSED /run/user/523/vscode-git-37445154a.sock ... etc.'
I got this error when *randomly* trying to push changes to a github repo. I was, 
* ssh'ed into a linux box from a vs code terminal
* previously `git clone`d a github repo which started with `https:`

There were two main problems here. 

### Problem 1. 
There is a setting in VS code you must uncheck, called `Git Terminal Authentication`.
* Go to vs code settings > search Git Authentication, and uncheck the box.\
I found the solution to this problem from here: https://stackoverflow.com/questions/62860280/git-push-missing-or-invalid-credentials-fatal-authentication-failed-for-http![image](https://github.com/cassielumbrazo/linux_survival_guide/assets/40898946/f6ad3f6f-30d7-45f7-89b8-0ba3b4113661)

### Problem 2. 
I needed to create a personal access token from github.
Prior to this experience, I did not know what a personal access token was.\
I guess if you use git clone for a repo which starts with \https (from inside linux box with vs code or other?? I'm not sure) but the linux box connection requires a github "personal access token".\
So, you can create one, then use it to sign into your github account via the command line, in place of a password.
* Go to github settings > Developer Settings > and create a person access token.
* Then, use the person access token (in the place of a password) to sign into your GitHub account via the command line from vs code.

If you want to save the token so that you do not have to add it every time you want to push to your github repo, you can. 
I did it following the instructions here: https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage
but, in short, the line of code to do this is below
> `git config --global credential.helper 'cache --timeout=43200'`

Thank you Michelle Hu. You're truely a great friend and programmer. 
