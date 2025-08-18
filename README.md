## Ship Shoot - A Godot game hosted on Github Pages
### How was this done?
Partially following [this tutorial](https://www.reddit.com/r/godot/comments/1apc1s2/host_your_game_on_github_pages/) on reddit. Steps are posted below for the sake of a backup.

<details>

>Purpose: This guide assumes your code is hosted on GitHub.com and that builds happen locally (on your machine). When you commit code, the /docs folder will be hosted via GitHub Pages. There are other build+deploy GitHub Actions out there, but this guide covers using coi to get around a couple of errors (Cross Origin Isolation and SharedArrayBuffer) you get when hosting on GitHub Pages.
>
>### Setting Up GitHub Pages
>
>Note: This only needs to be done once.
>
>1. Go to the "Settings" tab of the repo
>
>2. Select "Pages" from left-nav
>
>3. Select main branch and /docs directory, then select "Save"
>
>    1. A GitHub Action will deploy your website when there are changes
>
>4. On the main page of the GitHub repo, click the gear icon next to "About"
>
>5. Select "Use your GitHub Pages website", then select "Save changes"
>
>### Building for Web Using Godot GUI
>
>1. Select "Project" > "Export..."
>
>    1. If you see errors, click the link for "Manage Export Templates" and then click "Download and Install"
>
>2. Select the preset "Web (Runnable)"
>
>3. (One Time Setup) Download [coi.js](https://github.com/gzuidhof/coi-serviceworker/raw/master/coi-serviceworker.js) and add it to the /docs directory
>
>4. (One Time Setup) Enter "Head Include" <script src="coi-serviceworker.js"></script>
>
>5. Select "Export Project..."
>
>6. Select the "docs" folder
>
>    1. The GitHub Pages config points to the main branch and /docs directory
>
>7. Enter index.html
>
>8. Select "Save"
>
>9. Commit the code to trigger a GitHub Pages deployment (above)

</details>

Where this repository differs from the instructions is by following one of the comments on the original reddit post, the `docs` folder in this case is this repository and is added as a submodule to the original project.
Doing it this way lets you export within the project while obfuscating the source code.
