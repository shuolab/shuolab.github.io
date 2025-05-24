This website is built with [Hugo](https://themes.gohugo.io/).

# General Workflow
- Modify contents and layouts in this repo's `master` branch
  - All contents are inside ./content folder
  - All layouts are inside ./layouts folder
- Compile and publish website using the following commands one by one:
```
hugo --enableGitInfo
cd public
git add .
git commit -m "your commit msg here"
git push origin gh-pages
```
Running `hugo --enableGitInfo` compiles the website locally and saves the compilation result inside the `public` folder.

The public folder is linked to the `gh-pages` branch of this repo. Pushing to gh-pages will automatically trigger a re-deployment of the website with content inside `gh-pages`.


## Adding / modifying members
- Inside ./content/people, create a new folder with the new member's name in the format `firstame-lastname`. 
- The folder should then contain a `_index.md` and a `featuered.jpg` or `png` or any image format as long as the image filename is `featured` (refer to other members' folders)
- Edit the member's info in `_index.md`
  - `title`: the person's full name
  - `user_group`: choose from `"Current Members"`, `"Visiting Scholars"`, or `"Alumni"`. Note this tag must be exactely one of these three. This tag will be checked if you use `list-group` layout for the People page. If you wish to modify / add new tags, remember to modify the layout's searching conditions accordingly in `./layouts/people/list-group.html`, e.g. `{{ if eq .Key "Current Members" }}`. 
  - `role`: the person's degree level. Shown as a subtitle under the person's headshot.
  - `affiliation`: similar to `role`. Shown as a subtitle under the person's headshot.
  - `externalUrl`: if the member has an external url such as LinkedIn or personal website, paste the url here and it will be hyperlinked via the person's name under his headshot.
  - `summary`: no use at this moment.
  - `weight`: to put a member's positioning order on the page. Lower weight indicate higher ranking (Shuo's weight is 1!)




