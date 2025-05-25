## DeepDocs: Update your docs with AI on every pull request ([Install](https://github.com/marketplace/deepdocsai))
<!--  -->
DeepDocs is a LLM-powered app that keeps your GitHub documentation—like READMEs, API references, SDK guides, wikis, tutorials etc. up-to-date with your changing codebase, eliminating manual effort.


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
[Install](https://github.com/marketplace/deepdocsai) it in your source code repo. If docs are in a separate repo, install it there too.

2. **Add `deepdocs.yml`**  
In the `main` branch, place a `deepdocs.yml` file at the root of your source code repo. This file should specify the GitHub URLs of the doc files to be updated — all URLs must point to files that exist on the `main` branch.

**Option 1: A single repo or sub-folder**
Use this when you want DeepDocs to decide which docs to update within a folder or entire repo.
```yaml
target_repo:
  - url: "https://github.com/user/repo/tree/main/docs"
```
In Option 1, committing `deepdocs.yml` triggers DeepDocs to sync your code and docs, and comment on the commit when done. You’re all set for step 3.


**Option 2: Up-to 5 Individual files in the source code repo or external repo**
Use this when you want to update specific doc files only.
```yaml
target_files:
  - url: "https://github.com/user/repo/blob/main/path/to/doc.md"
```


3. **Create a PR**
Make a code change and open a pull request. DeepDocs will update the relevant docs in a new commit and add it to the same PR. If your docs are in a separate repo, it will open a PR there instead.

## Credit usage
<!-- -->
Each doc update consumes 1 credit, regardless of the number of code changes. If no update is needed, 0.5 credits are used for analysis.

## More
<!-- -->
- [Best Practices](https://github.com/DeepDocsAI/Deep-docs/blob/main/Best_Practices.md)
- [Report an issue](https://github.com/DeepDocsAI/Deep-docs/issues)
- [Changelog](https://github.com/DeepDocsAI/Deep-docs/blob/main/Changelog.md)
