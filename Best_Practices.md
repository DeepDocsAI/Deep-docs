# Best Practices for Using DeepDocs

DeepDocs helps keep your documentation up-to-date by automatically syncing it with your code changes. To get the most out of DeepDocs, follow these best practices.

## 1. Know What DeepDocs Does Best

DeepDocs excels at **updating existing documentation** to reflect code changes. It is **not designed to create docs from scratch**.

- To document new logic, manually create an initial version of the doc.
- DeepDocs works best when docs are directly tied to code—such as:
  - API references
  - SDK guides
  - Tutorials
  - Configuration or setup instructions
  - Component or module-level docs

## 2. Choose the Right Sync Mode

DeepDocs supports two modes:

### `target_files` Mode
- Provide up to 5 specific files from the same repo
- Use this option when you want to update specific doc files only.

### `target_repo` Mode
- Provide a repo or subfolder as the target.
- Use this when you want DeepDocs to decide which docs to update within a folder or entire repo.

Refer the [README](https://github.com/DeepDocsAI/DeepDocsAI/blob/main/README.md) on how to define these.

## 3. Understand Update Statuses

Each documentation update is marked with one of the following statuses:

- `unchanged`: No changes
- `modified`: Existing file updated
- Files marked for deletion are returned with empty content and the status `modified`
- Files marked for addition are appended to an existing file and also returned with the status `modified`


## 4. Write New Docs Manually

If you’ve added new logic that isn't documented yet:
- DeepDocs may try to append content to existing files.
- Instead, **create a short placeholder file with description**—DeepDocs will then try to update it.

## 5. Use `main` as the Source of Truth

DeepDocs compares against the `main` branch to determine changes.

- Ensure your `main` branch reflects the latest code and docs.
- `deepdocs.yml` must be committed to the `main` branch.

## 6. Review Updates in Pull Requests

When a PR is opened:

- If docs are in the same repo, DeepDocs adds a commit to the same PR.
- If docs are in an external repo, a new PR is opened there.

**Always review the doc updates**:
- Check for relevance and accuracy
- Don’t approve blindly—treat docs like code

## 7. Write Clear, Modular Code

Well-structured code leads to better doc updates.

- Use descriptive function and variable names
- Keep functions focused and short
- Break logic into reusable modules

## 8. Validate Your Config

Make sure your `deepdocs.yml` is:

- Committed to the `main` branch
- Correctly specifies `source_globs` and either `target_files` or `target_repo`

Improper or missing configuration will result in skipped updates.

## 9. Monitor for Unexpected Changes

DeepDocs uses AI—while often accurate, it may:

- Misinterpret intent or context
- Hallucinate content in rare cases

**Always review diffs** before merging.

## 10. Keep Your Team Informed

Let contributors know:

- DeepDocs may update docs in their PRs
- They’re responsible for reviewing those changes

---

By following these practices, you’ll get reliable, accurate, and maintainable documentation updates with every PR.
