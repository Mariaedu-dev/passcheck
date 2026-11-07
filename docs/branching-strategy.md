
# Branching Strategy — PassCheck

## 1. Overview

PassCheck adopts a simplified Git Flow strategy to ensure code quality, traceability, and organized software development.

All changes must be associated with a GitHub Issue and integrated through Pull Requests.

## 2. Branch Structure

### main
- Contains stable, validated versions.
- Receives changes through Pull Requests from `develop`.
- Stable releases are identified using Semantic Versioning.

### develop
- Integrates completed development work.
- Receives changes from feature, chore, documentation, and bugfix branches.
- Serves as the base branch for new development tasks.

### Working Branches
Each Issue must have a dedicated branch.

Naming conventions:

- `feature/issue-X-description`
- `fix/issue-X-description`
- `docs/issue-X-description`
- `chore/issue-X-description`
- `test/issue-X-description`

Example: `chore/issue-1-project-setup`

## 3. Development Workflow

1. Create or select a GitHub Issue.
2. Create a working branch from `develop`.
3. Implement the required changes.
4. Create small, atomic commits.
5. Open a Pull Request targeting `develop`.
6. Review the changes and validate acceptance criteria.
7. Merge the Pull Request after validation.
8. Close the associated Issue.

## 4. Conventional Commits

Commit messages follow the Conventional Commits standard.

Format:

`type(scope): description (#issue)`

Examples:

- `chore: initialize project structure (#1)`
- `docs(requirements): define functional requirements (#4)`
- `feat(password): implement strength validation (#11)`
- `test(password): add unit tests (#14)`
- `fix(validation): handle empty passwords (#12)`

## 5. Semantic Versioning

PassCheck follows Semantic Versioning:

`MAJOR.MINOR.PATCH`

- MAJOR: Incompatible changes.
- MINOR: Backward-compatible functionality.
- PATCH: Backward-compatible fixes.

Initial development versions:

- `v0.1.0` — First functional MVP.
- `v0.2.0` — Additional improvements.

Versions are recorded using annotated Git tags after validating a stable release.

## 6. Pull Request Requirements

Every Pull Request must:

- Reference the corresponding GitHub Issue.
- Describe the implemented changes.
- Target the correct base branch.
- Meet the Issue acceptance criteria.
- Pass available automated tests.

Use `Closes #X` in the Pull Request description to automatically close the related Issue when GitHub's closing conditions are satisfied. Otherwise, close it manually after the merge.

## 7. Quality Principles

- No direct commits to `main`.
- One working branch per Issue.
- Atomic commits.
- Traceable requirements.
- Automated testing whenever applicable.
- Clear and updated documentation.
