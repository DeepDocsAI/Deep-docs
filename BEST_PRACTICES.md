# Best Practices for Using DeepDocs

DeepDocs is designed to help you keep your documentation up-to-date by automatically syncing it with your code changes. To get the most out of DeepDocs and avoid surprises, follow these best practices.

---

## 1. Understand What DeepDocs Is (and Isn’t) Good At

DeepDocs excels at **modifying existing documentation** to reflect code changes. It is **not designed to create documentation from scratch**.

- In `target_files` mode, DeepDocs can only **modify** or **delete** the specified files.
- If you want to **add** new documentation, consider writing the first version manually.

---

## 2. Choose the Right Sync Mode

DeepDocs supports two modes, each suited for different use cases:

### `target_files` Mode
- You provide specific documentation files to be updated.
- DeepDocs will only **modify** or **delete** those files—**no new files will be created**.

### `target_repo` Mode
- You provide a repository (or subfolder) as the documentation destination.
- DeepDocs can **add**, **modify**, **delete**, or leave documentation **unchanged**, depending on the detected code changes.

---

## 3. Know the Possible Update States

Each documentation update is categorized into one of four statuses:
- `unchanged`: No relevant code change detected.
- `added`: A new file is created (only in `target_repo` mode).
- `modified`: An existing file is updated.
- `deleted`: A file is removed based on code changes.

---

## 4. Kickstart New Docs Manually for Better Results

If you’ve written new code that isn’t yet documented:
- DeepDocs may try to **append** that content to an existing doc rather than creating a new file.
- To guide DeepDocs, **create an initial version of the intended doc file** yourself.
  - Include even a short placeholder version that reflects the new logic.
  - DeepDocs will then reliably update this file as the code evolves.

---

## 5. Always Use the `main` Branch as the Source of Truth

DeepDocs uses the `main` branch of your repo to determine the latest version of your documentation. All comparisons and updates are made against the `main` branch.

- Make sure your `main` branch always reflects your latest published documentation.

---

## 6. Review Doc Updates in Pull Requests

When a pull request is created:
- DeepDocs will generate a documentation update **commit** and **attach it to the same PR**, if the documentation lives in the same repo.
- If your documentation lives in an external repo, DeepDocs will open a **new PR** in that repo.

**Important:** Reviewers should always:
- Examine the AI-generated documentation updates.
- Make manual corrections if needed.
- Avoid approving doc updates blindly.

---

## 7. Use Clear and Modular Code

Well-structured, clearly named functions and modules lead to more accurate doc updates.

- Avoid overly long functions or unclear naming.
- Group related logic into reusable, understandable components.

---

## 8. Validate Your Configuration

Make sure your `deepdocs.yml` is:
- Committed to the `main` branch.
- Correctly specifies `source_globs` and either `target_files` or `target_repo`.

Improper or missing configuration will result in skipped updates or errors.

---

## 9. Monitor for Unexpected Updates

Although DeepDocs aims for precision, it's still an AI-based tool:
- Monitor diffs for hallucinations, especially in newly added sections.
- You can always manually revert or edit the suggested changes.

---

## 10. Encourage Contributor Awareness

Educate your contributors:
- Let them know DeepDocs may update documentation on their PRs.
- Ask them to **review documentation changes** as seriously as they review code.

---

By following these practices, you'll get the most reliable, transparent, and maintainable results from DeepDocs.

