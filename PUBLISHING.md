##How to Publish a Pattern on SaaSBuilder

---

##How to Publish a Pattern on [SaaSBuilder](https://main.d64uo5pr4i9km.amplifyapp.com/)

To submit a new saas builder pattern, or to make changes to existing code, follow the instructions below.

## Repo Names

* **local:** Your local copy of the forked repository.
* **origin:** Your forked, remote copy of the original repository.
* **upstream:** The original, remote serverless-patterns repository.

## Initial Setup

[Fork and Clone](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo) the serverless-patterns repo.

1. Fork the original saasbuilder-patterns repo to create a copy of the repo in your own GitHub account: https://github.com/swarwick/saasbuilder-patterns
1. Clone your copy of the repo to download it locally: `git clone https://github.com/{your-github-username}/saasbuilder-patterns.git`
1. Change into the new local directory: `cd serverless-patterns`
1. Add the original serverless-patterns repo as another remote repo called "upstream": `git remote add upstream https://github.com/swarwick/saasbuilder-patterns`
1. For verification, display the remote repos: `git remote -v`

   The output should look like this:

    ```
	origin  https://github.com/{your-github-username}/saasbuilder-patterns.git (fetch)
	origin  https://github.com/{your-github-username}/saasbuilder-patterns.git (push)
	upstream        https://github.com/swarwick/saasbuilder-patterns (fetch)
	upstream        https://github.com/swarwick/saasbuilder-patterns (push)
	```

## Create Branch

Create a new local branch for each saas pattern or modification being made. This allows you to create separate pull requests in the upstream repo.

1. Create and checkout a new local branch before making code changes: `git checkout -b {branch-name}`

   Branch name syntax: `{username}-{feature|fix}-{description}`

   Example branch name: `myusername-silo-security-saasbuilder`

1. For verification, display all branches: `git branch -a`

   The output should look like this:

    ```
    * {branch-name}
    main
    remotes/origin/HEAD → origin/main
    remotes/origin/main
    ```

## Your Pattern

Now is the time to create your new saas pattern or modify an existing pattern.

1. If you are creating a new saas pattern, copy the folder named "_pattern-template" to start with a template: `cp -r _pattern-template {new-folder-name}`
1. If you are modifying an existing pattern, make your code changes now.
1. When your pattern is complete, stage the changes to your local branch: `git add .`
1. Commit the changes to your local branch: `git commit -m 'Comment here'`

## Pull Request

Push your code to the remote repos and [create a pull request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).

1. Push the local branch to the remote origin repo: `git push origin {branch-name}`

   If this is the first push to the remote origin repo, you will be asked to Connect to GitHub to authorize the connection. Sometimes the pop-up window appears behind other windows.

1. Go to the [upstream repo](https://github.com/aws-samples/serverless-patterns) in Github and click "Compare & pull request".
    1. Enter an appropriate title:

       Example title: `New serverless pattern - lambda-aurora-serverless`

    1. Add a description of the changes.
    1. Click "Create pull request".
1. Submit a [new issue](https://github.com/aws-samples/serverless-patterns/issues/new?assignees=jbesw&labels=&template=new-serverless-pattern-submission.md&title=New+pattern+submission) to provide the additional details that will be used to build the serverless pattern web page on ServerlessLand.com.
    1. Provide responses to each section (eg: Core Concepts, Key Considerations, Reference, etc.)
    2. Add a link to the pull request in the "GitHub PR for template" section. If you type a hashtag (#), it will display a list of the current pull requests to select from.
    3. Be sure to provide your information in the "Author bio" section.
    4. Click "Submit new issue".
    5. Example issue: https://github.com/swarwick/saasbuilder-patterns/issues/2

## Sync Repos

After your pull request has been accepted into the upstream repo:

1. Switch to your local main branch: `git checkout main`
1. Pull changes that occurred in the upstream repo: `git fetch upstream`
1. Merge the upstream main branch with your local main branch: `git merge upstream/main main`
1. Push changes from you local repo to the remote origin repo: `git push origin main`

## Delete Branches

Delete any unnecessary local and origin branches.

1. Switch to your local main branch: `git checkout main`
1. For verification, display all branches: `git branch -a`
1. Delete any unnecessary local branches: `git branch -d {branch-name}`
1. Delete any unnecessary remote origin branches: `git push origin --delete {branch-name}`

## Helpful Tips

1. When creating a pattern.md file for your saas pattern, place example code and commands within a `code block`.
2. Place any architecture diagrams or related images in the `images` folder in either (PNG, JPEG, or GIF) format
3. Add any reference material related to the saas pattern in the reference section at the bottom

## Example Patterns

1. Full Stack Silo:  [GitHub](https://github.com/swarwick/saasbuilder-patterns/tree/main/FullStackSilo)