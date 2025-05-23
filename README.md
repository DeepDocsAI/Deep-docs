## DeepDocs: Update Your Docs Automatically With AI
<!--  -->
DeepDocs is a LLM-powered GitHub app that keeps your documentation—like READMEs, Wikis, API references, SDK guides, tutorials etc. up-to-date with your changing repo, eliminating manual effort.
[Installation link](https://github.com/marketplace/deepdocsai)

## How it works
<!--  -->
1. In your main repo, specify the path to your doc files.
2. When a PR is opened, DeepDocs automatically updates the relevant docs based on code changes.
  

## Features
<!--  -->
- **Continuous Documentation:** Update your docs with every PR with no manual effort
- **Intelligent Updates:** Preserves your existing doc format without rewriting from scratch 
- **Broad support**: Works across mono and external repos
- **Github native**: Integrates smoothly into your dev workflow and with other doc hosting tools like Mintlify


## Setup
<!--  -->
1. **Install DeepDocs**  
Install it in your source code repo. If docs are in a separate repo, install it there too.

3. **Add `deepdocs.yml`**  
In the `main` branch of your source code repo, add a `deepdocs.yml` file specifying the path to doc files. You can use one of two formats:

**Option 1: Up-to 5 Individual files in the source code or external repo**
Use this when you want to update specific doc files only.
```yaml
target_files:
  - url: "https://github.com/user/repo/blob/main/path/to/doc.md"
```


**Option 2: A single repo or sub-folder**
Use this when you want DeepDocs to decide which docs to update within a folder or entire repo.
```yaml
target_repo:
  - url: "https://github.com/user/repo/tree/main/docs"
```
NOTE: 
- All urls must exist on the`main` branch

3. **Create a PR**
Make a code change and open a PR. DeepDocs will update the relevant files in a commit and add it to same PR. If docs are in a separate repo, a PR will be opened there.


## Credit usage
<!-- -->
Each doc update consumes 1 credit, regardless of the number of code changes. If no update is needed, 0.5 credits are used for analysis.
