
https://docs.github.com/en/get-started

---
1 What is GitHub?
2 Creating a repository for your project on GitHub
3 Planning your work
4 Connecting to your code locally
5 Writing and storing your code
6 Reviewing your proposed changes
7 Deploying your website automatically
8 Git and GitHub learning resources
---
# The complete workflow
1 Planned the work with an issue and a project board.
2 Created a branch and built your feature.
3 Opened a pull request.
4 Reviewed your own changes (optionally with help from Copilot).
5 Merged your feature into main.
6 Updated your project board to reflect your progress.
---
# Tutorial

## Planning your work
Before you write code, capture what you want to build and track your progress. Organize your work and track your progress so you always know what to build next.

**Issues** track ideas, tasks, and bugs for your software project. Create one for the first feature you'll build: a list of starred repositories on your web page.
- Adding follow up issues: Create one or more issues to describe ideas and features for your website that you want to work on later.

**Projects** give you visual tables, boards, and roadmaps to organize and track issues for your software projects.
- Moving work across the board: The board's columns represent stages of your work. As you make progress, move each item to show its status.

xxx


### Prompt
Create a starred repositories page for my software project. Add:
- events.json with sample data for a few starred repositories
- style.css to style a simple list
- script.js to fetch events.json and render the list
- an update to index.html that links style.css and script.js

Use the code written in https://docs.github.com/get-started/start-your-journey/creating-and-changing-your-code.

## Building the website's code
Your feature needs a few files: sample data, a stylesheet, a script to display the data, and an updated home page.

You can write these files yourself or ask Copilot to generate them.

Open Copilot Chat in your editor and ask it to create the files with a prompt like the following.

<!-- markdownlint-disable search-replace -->

```text copy
Create a starred repositories page for my software project. Add:
- events.json with sample data for a few starred repositories
- style.css to style a simple list
- script.js to fetch events.json and render the list
- an update to index.html that links style.css and script.js

Use the code written in https://docs.github.com/get-started/start-your-journey/creating-and-changing-your-code.
```

<!-- markdownlint-enable search-replace -->

<a href="vscode://GitHub.Copilot-Chat?ref_product=copilot&ref_type=engagement&ref_style=button" target="_blank" class="btn btn-primary mt-3 mr-3 no-underline" aria-label="Open Copilot Chat in Visual Studio Code">
<span>Open Copilot Chat in VS Code</span> <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-link-external" aria-label="link external icon" role="img"><path d="M3.75 2h3.5a.75.75 0 0 1 0 1.5h-3.5a.25.25 0 0 0-.25.25v8.5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-3.5a.75.75 0 0 1 1.5 0v3.5A1.75 1.75 0 0 1 12.25 14h-8.5A1.75 1.75 0 0 1 2 12.25v-8.5C2 2.784 2.784 2 3.75 2Zm6.854-1h4.146a.25.25 0 0 1 .25.25v4.146a.25.25 0 0 1-.427.177L13.03 4.03 9.28 7.78a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l3.75-3.75-1.543-1.543A.25.25 0 0 1 10.604 1Z"></path></svg>
</a><br><br>

Review what Copilot generates, then adjust the files to match the examples below.

If you didn't use Copilot, use your code editor to create the files below in the `add-starred-list` branch.

1. Create a file named `events.json` with the following sample data. Save the file.

   ```json copy
   [
     { "name": "octocat/Hello-World", "starred": "2024-01-15" },
     { "name": "github/docs", "starred": "2024-02-02" },
     { "name": "octo-org/octo-repo", "starred": "2024-03-21" }
   ]
   ```

2. Create a file named `style.css` with the following styles. Save the file.

   ```scss copy
   body {
     font-family: sans-serif;
     margin: 2rem;
   }

   ul {
     list-style: none;
     padding: 0;
   }

   li {
     padding: 0.5rem 0;
     border-bottom: 1px solid #ddd;
   }
   ```

3. Create a file named `script.js` with the following code. Save the file.

   ```javascript copy
   fetch("events.json")
     .then((response) => response.json())
     .then((events) => {
       const list = document.querySelector("#starred");
       events.forEach((event) => {
         const item = document.createElement("li");
         item.textContent = `${event.name} — starred ${event.starred}`;
         list.appendChild(item);
       });
     });
   ```

4. Update `index.html` to link the new files and hold the list. Save the file.

   ```html copy
   <!DOCTYPE html>
   <html lang="en">
     <head>
       <meta charset="utf-8">
       <title>Stargazers log</title>
       <link rel="stylesheet" href="style.css">
     </head>
     <body>
       <h1>Stargazers log</h1>
       <p>A log of the repositories I've starred.</p>
       <ul id="starred"></ul>
       <script src="script.js"></script>
     </body>
   </html>
   ```

## Creating a branch
branch lets you work on your feature in its own space, without changing the main copy of your code until you're ready.

## Committing and pushing your changes
Committing saves a snapshot of your changes, and pushing sends them to GitHub where they will be stored in your repository.

## Opening a pull request
A pull request proposes your branch's changes for review before they merge into `main`.

---

Review your own pull request before you merge to catch bugs and improve quality, with an optional AI assist from Copilot.

Reviewing your changes in the pull request

- The Files changed tab in a pull request on GitHub shows a diff of everything your branch adds or modifies.
- Click View your pull requests to go to your pull requests inbox on GitHub or navigate to your stargazers-log repository and click the Pull requests tab.
- Click on the title to open your pull request for the add-starred-list branch.
- Click the Files changed tab.
- Read the diff for each file. 
- To note something you want to change, hover over a line, click , type a comment, then click Comment.

## Ai Code Review
You can also ask Copilot Chat in your editor to review the same changes and offer a second perspective.

### Prompt
Review my changes for bugs, missing error handling, and accessibility issues.


## Merging the pull request
Once you're satisfied with your changes, merge them into main.
On GitHub, return to your pull request and refresh the page.
Click the Conversation tab.
Click Merge pull request, then click Confirm merge.
Click Delete branch to clean up your add-starred-list branch.

## Checking your progress
Update your project board to reflect the completed work.
Drag the Display a list of starred repositories item from In Progress to Done.
If you have more features to build, create new issues and move them to In Progress when you start the next cycle.

---

https://docs.github.com/en/get-started/start-your-journey/deploying-your-website-automatically

# Deploying your website automatically

Automate your code deployment with GitHub Actions and GitHub Pages to publish updates to a live site with every push to the main branch.

Your feature is merged, so now you can share it. In this tutorial, you'll set up automatic deployment so every push to `main` publishes your software project to a live website.

> [!NOTE]
> The URL of your GitHub Pages site depends on which version of GitHub you use.
>
> * On GitHub.com, your site is published at `YOUR-USERNAME.github.io/REPOSITORY`.
> * If you use GitHub with data residency on GHE.com, your site is published at `pages.SUBDOMAIN.ghe.com/YOUR-USERNAME/REPOSITORY`, where `SUBDOMAIN` is your enterprise's subdomain.
> * On GitHub Enterprise Server, your site is published at `pages.HOSTNAME/YOUR-USERNAME/REPOSITORY`, where `HOSTNAME` is the hostname of your GitHub Enterprise Server instance.

## Prerequisites

* A `stargazers-log` repository with your merged feature. If you haven't merged it yet, see [Reviewing your proposed changes](/en/get-started/start-your-journey/reviewing-your-proposed-changes).

## Enabling GitHub Pages

Set up GitHub Pages to host your site, and use GitHub Actions to build and publish it.

1. On GitHub, navigate to your `stargazers-log` repository.
2. Under your repository name, click **Settings**.
3. In the sidebar, in the "Code and automation" section, click **Pages**.
4. Under "Build and deployment", from the **Source** dropdown, select **GitHub Actions**.

Leave the other settings at their defaults. Next, you'll create **your own workflow** to build and deploy your site automatically.

## Creating a deployment workflow

A workflow is a set of automated steps that GitHub Actions runs for you. Add one that builds and deploys your site whenever you push to `main`.

1. In your repository, create a file named `.github/workflows/deploy.yml`.
   1. On the main page of your `stargazers-log` repository above the list of files, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="plus" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg>**, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="plus" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg> Create new file**.
   2. In the file name field, type `.github/workflows/deploy.yml`.

2. Add the following workflow content.

   ```yaml copy
   name: Deploy to GitHub Pages

   on:
     push:
       branches:
         - main

   permissions:
     contents: read
     pages: write
     id-token: write

   jobs:
     deploy:
       runs-on: ubuntu-latest
       environment:
         name: github-pages
         url: ${{ steps.deployment.outputs.page_url }}
       steps:
         - name: Checkout
           uses: actions/checkout@v6
         - name: Setup Pages
           uses: actions/configure-pages@v5
         - name: Upload artifact
           uses: actions/upload-pages-artifact@v4
           with:
             path: '.'
         - name: Deploy to GitHub Pages
           id: deployment
           uses: actions/deploy-pages@v4
   ```

3. Commit the file directly to the `main` branch.

## Understanding the workflow

Each part of the workflow has a job to do:

* **`on`** tells GitHub Actions to run the workflow on every push to `main`.
* **`permissions`** grant the workflow the access it needs to publish to GitHub Pages.
* **`environment`** connects the job to your GitHub Pages site and exposes the published URL as `${{ steps.deployment.outputs.page_url }}`.
* **`steps`** check out your code, prepare GitHub Pages, upload your files as an artifact, and deploy them to your live site.

## Viewing your live site

After you commit the workflow, GitHub Actions runs it automatically.

1. In your repository, click the **Actions** tab to watch the workflow run.
2. Click the latest workflow run to see a summary of the job details.
3. When the run completes, open your published site at `https://YOUR-USERNAME.github.io/stargazers-log/`. Replace `YOUR-USERNAME` with your username.
   * For example, if your GitHub account username is `octocat`, your site is at `https://octocat.github.io/stargazers-log/`.

From now on, every push to `main` redeploys your site with your latest changes.

## What you built

Across this series, you built a complete software project and practiced the GitHub workflow:

| Stage                          | What you learned                          |
| ------------------------------ | ----------------------------------------- |
| Creating your software project | Repositories, README files                |
| Planning your work             | Issues, Projects (project boards)         |
| Connecting locally             | GitHub Desktop, cloning                   |
| Writing and storing code       | Branches, commits, pull requests, Copilot |
| Reviewing changes              | Pull request reviews, Copilot             |
| Deploying automatically        | GitHub Actions, GitHub Pages              |

## Next steps

* Expand your understanding of Git and GitHub. For more information, see [Git and GitHub learning resources](/en/get-started/start-your-journey/git-and-github-learning-resources).
* Explore Copilot Chat to learn faster and get help as you code. For more information, see [GitHub Copilot on GitHub.com and GitHub Mobile](/en/copilot/concepts/chat).
* Go deeper with AI and learn how agents can act like a practical coding partner by turning ideas into small actionable steps, generating examples, and handling repetitive work. For more information, see [Agent capabilities](/en/copilot/concepts/agent-capabilities).
* Learn more about automating your software projects with GitHub Actions workflows. For more information, see [Understanding GitHub Actions](/en/actions/get-started/understand-github-actions).
* Add a custom domain or explore more ways to publish your website with GitHub Pages. For more information, see [Getting started with GitHub Pages](/en/pages/getting-started-with-github-pages).


