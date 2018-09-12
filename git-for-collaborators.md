# super-easy guide to git for whoever must work with a git nerd

if your wo-worker just told you that he has updated the script you need and he uploaded it on his git repository and to "go get the code there". And you don't really understand what is going on and why he could not just give you that script, well, this guide is for you.

## what is git
well, simplifying a lot, **git** is a command line tool, which it is used to do the *version control* of a directory and its content. 

## what does git do?
By *version cotrol* we mean it can be used to keep a very detailed record of all the changes that have been made within a specific folder and the files that are in it (and its subfolders too). Each folder undergoing this process is know as a **repository**.

Basically git is used to keep all the history of one or more files. In this way one can always revert back to previous versions fo the files. 

## ok, but what about my script?
likely your coworker keep its code under a git repository, in this way he can always know which version of the script you are using and go back to a previous version if he need to. So you might now think 

```
"yes very cool he can do whatever with his files, but if the script is on his pc how can I go and get it?"
```

well, the nice part of git is that allows him to sync all the scripts he keep into the repository (the ones on his pc) with a remote **clone** of the repository. 

You are now thinking that is something like dropbox, google drive or any other *cloud* service. Indeed, somehow, this part is very similar: he has **a folder which is synced to a remote folder**. Syncing to something remote is good: if your hard-drive dies you will still have a copy of the files, and beacuse is is a git repository, not only the files will be preserved but also the whole record of changes the files underwent since the creation. He would just need to **clone** back the repo on his new hard drive and he we will be back working on your code in a moment!

Like dropbox, google drive or whatever service you have in mind also git need some kind of remote service that stores the data for you. The most popular is [GitHub](https://github.com/), which offers **unlimited** space for **public** (everybody can see the files you put in there) repositories, but also [GitLab](https://about.gitlab.com/) does exists. 

At this point you likely figure out that the script you were looking for is likely on some remote website/machine. Lets say your coworker has a GitHub account but he did not tell anything more than this. You can proceed like this:
- go to [GitHub](https://github.com/) and create an account if you don't have one (yes yet another account! if this bother you you should start using some password manager e.g. [pass](https://www.passwordstore.org/), which, btw uses a git repository to keep track of your passwords).
- search your collegue on the website. GitHub is Basically a social network for developers so it will be easy. try with his name/surname or ask him his username on github.
- on his profile you can have acces to all his **public** repositories he is keeping on GitHub. Maybe the script you are looking in one of these, you can search or just ask him where it is.
- if you are working on a super-secret science project it is very likely he did not put the script in a **public** repository but rather in a **private** one [1].
- at this point you **must** ask the ownere of the repository you want to have access to to give you the permission. Once that is granted you will be able to see that repository and finallt the script you where looking for.

## Finally, my script
You finally had access to the repository on github and found your script. Now you can easily download it and use it! is this all? 

Yes, if you want... but there is muche more you can do... 

## Getting **all** the code in the repository
Let's say you don't just want a single script but you need the whole repository, which might contains other scripts/other code you need. The operation you need to do is to **clone** the whole repository on your local pc. You can use the **git** command to clone the repository you want, you just need to know the address of the repo which is something like:

```
https://github.com/luca-penasa/git-for-collaborators.git 
```

then you can use git like this
```
git clone  https://github.com/luca-penasa/git-for-collaborators.git 
```

this command will create a clone of the remote repository on your pc (the *working copy*) under the folder *git-for-collaborator*, with all the files and their history.

I know, I've lost you now. git is a command line tool, and maybe you are not very familiar with the command line, you might even don't know what it is. Thats why there are tools that provide a nice interface for git, so you don't need to learn all this stuff at this time:

- if you work on GitHub only try with [GitHubDesktop](https://desktop.github.com/)
- if you want a more generic git client with a nice interface try to use [gitkraken](https://www.gitkraken.com/)



## Why I must do all this?
Short answer: Because in this way you won't piss off your collegue who is writing code for you! If he told you to go get the code on his git repo he is likely to have his own misterious and nerdy reasons. 

The long answer is that you haven't yet scratched the surface of what git can do for you. Let see with a simple example:

Let's say you cloned the repo you needed at this point and you started doing changes to the code, but suddently the code does not work anymore! what to do? You could just send the code back to your collegue and ask him to fix it. But what if the code is made of more than just one file? And you did changes a little here and a little there? You might even not remembering where and how you changed the code!

git will help you in this case:
- you can revert your local directory to the remote version which is know to be working, with a **git reset**
- you can ask git to show the difference of your files from any previous version so to possibly spot the problem
- you can upload (**commit** and **push** in git terminologies) your *modified* code to the remote GitHub repo so that your collaborator will be able to see what you did and try to fix the problem
- once your collegue has fixed the bug and he has committed and pushed to the remote version of the repo on github you can now update the local repo to the latest version (**pull** in git terms) 

This workflow allows many different persons to work on the same code in a robust way. If you want to know more about this have a look at [this guide](http://rogerdudler.github.io/git-guide/).


## Notes

[1] Github gives you free private repositories  if you are a researcher! you just need to follow [this](https://help.github.com/articles/applying-for-an-academic-research-discount/) procedure.














