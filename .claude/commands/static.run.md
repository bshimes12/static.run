Takes a page name (an HTML file path relative to this project root) as an argument: $ARGUMENTS

Do the following steps in order:

1. **Pull from GitHub**: Run `git pull origin master --rebase` to sync the latest changes from the remote.

2. **Add the page to index.html**: Open `index.html` at the project root. Find the `<!-- PAGES -->` comment. Add a new tile entry directly BEFORE that comment. The tile should follow this exact format (replace the href and label appropriately):

```html
<a href="PATH_TO_FILE" class="tile"><span class="tile-icon">&#9670;</span><span class="tile-label">PAGE NAME</span></a>
```

- The href should be the relative path to the HTML file as provided in the argument.
- The label should be a human-readable name derived from the filename (strip the .html extension, replace hyphens/underscores with spaces, title-case it). If the file is in a subdirectory, use just the filename for the label, not the full path.
- Do NOT add duplicate entries. If a tile with the same href already exists, skip this step.

3. **Stage and commit**: Stage all changes (including the new/modified HTML files and index.html) and create a git commit with message: "Add PAGE_NAME page"

4. **Push to GitHub**: Run `git push origin master`

5. **Create zip**: Create a zip file called `static-run.zip` in the project root containing everything in the working directory EXCEPT `.git`, `.claude`, `.gitignore`, and `.DS_Store`. Overwrite any existing zip. Use: `cd /Users/bower/code/static.run && zip -r static-run.zip . -x '.git/*' '.claude/*' '.gitignore' '.DS_Store' '*.DS_Store'`

6. **Stage and push the zip**: Stage the zip, commit with message "Update zip", and push to master.

7. **Confirm**: Tell me it's done and show me the list of pages currently in index.html.
