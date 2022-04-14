# Deepset Cloud status page

We use cState to communicate the status of deepset Cloud to our customers. If we want to report an issue we need to create a markdown file
within [this](/content/issues/) directory using the name `YEAR-MONTH-DAY-topic.md`. This Markdown must contain a header that contains 
a couple of attributes that are used to render the current status: 

```
---
title: Title of the issue (e.g. Pipeline deployment reports unhealthy states)
date: 2022-04-13 15:30:00 
resolved: false
resolvedWhen: 2022-04-22 14:30:00  # auto resolve at 2022-04-22 14:30:00
severity: disrupted # there are multiple severity states (disrupted, down, ...)
affected:  # this list contains the affected services 
  - API    
section: issue
---
```


You can find a list of available services within the [config.yml](/config.yml) and a list of severitys within the cState docs.

Pushing changes to master will deploy the latest status page.


## Development

### cState Site v5.0.5

This is the default cState status page website directory/folder.

* Example site repository link (you are here): https://github.com/cstate/example
* Main cState source code repository: https://github.com/cstate/cstate

#### Are you updating? Use these commands

Download your site with all the directories. `git clone --recursive <your repo link goes here>`

Update the cState theme submodule. `git submodule foreach git pull origin master`

In the parent directory, type `hugo serve`. Check to see if everything is working.

Then do `git add -A; git commit -m "Update cState"; git push origin <branch, probably main or master>`. Your status page is now updated and uploaded.


#### For maintainers (probably not for you)

Maintainers need to update both cstate/cstate and cstate/example for each new version.

Download this repo with all the directories. `git clone --recursive -b master https://github.com/cstate/example.git`

Add your changes from cstate/cstate's exampleSite folder.

Update the cState theme submodule. `git submodule foreach git pull origin master`

Then push `git add -A; git commit -m "Update cState vX.X.X"; git push origin master`.

#### License

MIT © Mantas Vilčinskas
