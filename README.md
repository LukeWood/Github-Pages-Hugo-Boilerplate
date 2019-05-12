# Github-Pages-Hugo-Boilerplate
Github-Pages-Hugo-Boilerplate is a repository dedicated to making the deployment of
static webpages built using [Hugo](https://gohugo.io).

## Preliminary Setup
### Create a git repository to host the site from
Github pages are hosted at a url depending on the name of the repo unless you use a custom domain.
E.x. creating a repo with the name "HugoPageDemo" will lead to the url => "YourUsername.github.io/HugoPageDemo"

The only exception to this is creating a repository with the exact name "YourUsername.github.io" which will be hosted at that url. 

See [LukeWood.github.io](https://github.com/LukeWood/LukeWood.github.io) as an example (hosted on a custom domain).

[You can create a new repo here.](https://github.com/new)
### Install Hugo
You will need to have [hugo](https://gohugo.io/getting-started/quick-start/) installed to generate and deploy
a hugo based website.

### Export Your Github Username as An Environment Variable
If you are using bash as your shell you can just add the following line to your .${SHELL}rc

```
EXPORT USERNAME={Your_Github_Username}
```

## Initial Setup of Your Repo
### Clone your repo locally
Make sure you have a local working copy of your repo before continuing.

```
git clone https://github.com/${USERNAME}/${USERNAME}.github.io
```

### Adding the setup and deployment script to your repo
Now that you have an empty repository you need to add this repository's files into the your empty repo.
You can do this by setting this repository as an upstream to your empty repository.

```
git remote add upstream https://github.com/LukeWood/Github-Pages-Hugo-Boilerplate.git
``` 

Next pull this repo into your repo.

```
git pull https://github.com/LukeWood/Github-Pages-Hugo-Boilerplate.git
```

You will now have the _setup.sh_ and _deploy.sh_ scripts.
*Existing repos will need to be rebased in order to pull this repo.*

Credit to [Jente Hidskes](https://www.hjdskes.nl/blog/update-deploying-hugo-on-personal-gh-pages/) for these scripts.
### Setting the default development branch
Github pages serves from the master branch but we will want a separate branch to develop content on.
In order to solve this you should change your default branch from master to something else (I just use hugo as the branch name).

[Instructions to do so can be found here.](https://help.github.com/en/articles/setting-the-default-branch)

### Setup Github Pages
For this setup you'll want to use the "Serve from master" setting. 

[Full steps for Github Pages setup can be found here](https://github.com/pandao/editor.md/archive/master.zip)

### Initialize your repo as a hugo project
Make sure you are on the hugo branch
```
git checkout hugo
```

Now create your hugo site in your github repo.  The force flag is required as we already have the setup and deploy scripts.

```
hugo new site . --force
```

### Run the setup script
Run the setup script *once*.

```
./setup.sh
```

Your repo is now all setup as a hugo project!

## Adding content/themes
After you add content and themes, simply run the deploy.sh script to update your website.

```
./deploy.sh
```

Make sure to checkout [hugo's docs](https://gohugo.io/getting-started/quick-start/) to get started!  Happy hacking!
