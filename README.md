## DeepDocs: Update Your Docs Automatically With AI
<!--  -->
DeepDocs is a LLM-powered GitHub app that keeps your documentation—like READMEs, Wikis, API references, SDK guides, tutorials etc. up-to-date with your changing repo, eliminating manual effort.
[Installation link](https://github.com/marketplace/deepdocsai)

## How it works
<!--  -->
1. In your main code repository (repo), specify the path to your documentation (doc) files.
2. Whenever a Pull Request (PR) is opened, DeepDocs analyses the repo context, as well as code changes and automatically updates the relevant documentation.
  

## Capabilities
<!--  -->
- Automatically updates docs with every PR
- Preserves your existing doc format and structure without rewriting from scratch 
- Works across monorepos and external doc repos
- Integrates seamlessly into your GitHub workflow  


## Benefits
<!--  -->
- **Up-to-date docs**: Your docs stay updated with every code change
- **Zero manual effort**: No need to write docstrings, copy-paste snippets, or manually maintain docs
- **Seamless integration**: Works smoothly with popular doc hosting platforms like Mintlify and others


## Setup
<!--  -->
1. **Install DeepDocs**  
[Install DeepDocs](https://github.com/marketplace/deepdocsai) in the repo with your source code and docs. If docs are in a separate repo, install it there too.

2. **Add `deepdocs.yml`**  
In the source repo’s `main` branch, add a `deepdocs.yml` file specifying which doc files to update. You can use one of two formats:

**Option 1: Individual files (up to 5 files)**
```yaml
target_files:
  - url: "https://github.com/user/repo/blob/main/path/to/doc.md"
```


**Option 2: Repo or folder in a repo (only 1 allowed)**
```yaml
target_repo:
  - url: "https://github.com/user/repo/tree/main/docs"
```

**Note**:
- The urls must point to a `main` branch
- All `target_files` must belong to the same docs repo
- `target_files` take precedence if `target_repo` is also defined

3. **Create a PR**
Make a code change and open a PR. DeepDocs will update the relevant doc files automatically in a commit and add it to same PR.


## Credit usage
<!-- -->
Each doc update consumes 1 credit, regardless of the number of code changes. If no update is needed, 0.5 credits are used for analysis — this also applies when using `target_repo` and no relevant files are changed.
