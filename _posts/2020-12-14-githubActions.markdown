---
layout: post
title: How to Set Up CI/CD With GitHub Actions for Jekyll
---
GitHub Actions makes it easy to automate all your software workflows, with world-class CI/CD. Build, test, and deploy your code right from GitHub. 

**Continuous Integration (CI)**<br>
Continuous integration (CI) allows different developers to upload and merge code changes in the same repository branch on a frequent basis.

**Continuous Deployment (CD)**<br>
In continuous deployment (CD), the new code that’s been introduced and that’s passed the CI process is automatically implemented in production.

First and foremost we need a Jekyll project hosted on GitHub preferably on the master branch. When the Action builds your site, the contents of the destination directory will be automatically pushed to the `gh-pages` branch with a commit, ready to be published.

> The Action we’re using here will create a gh-pages branch on every successful deploy.

**Setting up the Action**<br>
GitHub Actions are registered for a repository by using a `YAML` file inside the directory path `.github/workflows`. 

> note the dot at the start `.github/workflows`. 

Create a YAML workflow file called `github-pages.yml` in the workflow directory. These are the contents of the file:

{% highlight ruby %}
name: Build and deploy Jekyll site to GitHub Pages

on:
  push:
    branches:
      - master

jobs:
  github-pages:
    runs-on: ubuntu-16.04
    steps:
      - uses: actions/checkout@v2
      - uses: helaili/jekyll-action@2.0.1
        env:
          JEKYLL_PAT: ${{ secrets.JEKYLL_PAT }}

{% endhighlight %}

* The build is triggered using `on,push` condition to the master branch only preventing the Action from overwriting the gh-pages branch.
* The name of the job matches our YAML filename: `github-pages`.
* The checkout action takes care of cloning your repository.
* `helaili/jekyll-action@2.0.0.` specifies action and version number that handles the build and deploy.
* set a reference to a secret environment variable for the action to use: `JEKYLL_PAT`.

**Permission to push to gh-pages**

Providing permissions to push to gh-pages branch.You need to create a GitHub authentication token on your GitHub profile, then set it as an environment variable in your build using Secrets.<br>

Create authentication token: -

1. On your GitHub profile, under Settings.
2. go to Developer settings. 
3. Select Personal Access Tokens.
4. Generate new token. 
5. Give the token a name like "GitHub Actions".
6. Check `repo` checkbox to give access to the entire repository scope.(necessary for the action to commit to the gh-pages branch).
7. Generate token and copy the token.
8. Go to your `repository’s Settings` and then the `Secrets` tab.
9. Select new repository secret. 
10. Create a token named JEKYLL_PAT.
11. Paste the token(copied earlier) and save.

On pushing any local changes onto master, the action will be triggered and the build will start.To watch the progress and see any build errors, check on the build status using the `Action` tab on your repository.

If all goes well, all steps will be green and the built assets will now exist on the gh-pages branch. n a successful build, GitHub Pages will publish the site stored on the repository gh-pages branch.

> you do not need to setup a gh-pages branch or enable GitHub Pages, as the action will take care of this for you. `For private repositories, you’ll have to upgrade to a paid plan`.

When you need to make further changes to the site, commit to master and push. The workflow will build and deploy your site again.

> **`Do not to edit the gh-pages branch directly, as any changes will be lost on the next successful deploy from the Action`**.


