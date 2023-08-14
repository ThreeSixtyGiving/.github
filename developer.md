# Development on 360Giving software products

## Contributing 

[More information about contributing to 360Giving software](https://www.threesixtygiving.org/data/using-the-data/technical-users/#Contributing_to_360Giving_software)

## Workflow
Generalised workflow for making a change in a 360Giving software repository

1. Git clone (`git clone`) or update existing repository (`git pull`)
2. Create new branch (`git checkout -b initials/new_branch_topic`)
3. Make changes
4. Commit changes to branch
5. Push changes to github
6. Create pull request
7. If CI tests pass and pull request is ready - assign reviewers to review pull request. If not ready set pull request as draft. If webfront end changes make sure 360Giving have approved.
8. After pull request approved merge
9. Deploy to live

## Git branch names
If sole collaborator prefix the git topic branch name using your initials (or other known identifier) and a forward slash, for example `mw/fix_issue_102` . This helps to make sure ownership and uniqueness is communicated (especially when checking out branches locally/outside of github).

## Git commits guide

### Commit size
Commits are made as small as is reasonable to encapsulate a single change.

Git Commits are [atomic](https://en.wikipedia.org/wiki/Atomic_commit#Revision_control), each commit is self contained such that someone can check out a repository at any commit and have a working system, this allows easier testing of changes, the use of Git Bisect and makes it easier to relate the log message and the code changes.

### Log message
In the subject line of log messages the name of the logical units of the code or module is added before a summary seperated by a colon, use existing names where possible. A longer description is then added below if needed. This helps when scanning down the git log to see what changes to which units/modules were made.

If an issue is related to the commit use the full URL of issues, so that if commits are moved around between repositories, the links will not be broken and the unique URIs are created.

Example:

```
tests: Add test blah to make sure blah-de blah doesn't regress

This adds a test case to prevent the regression in the blah module loader by loading some sample data.
Fixes: https://github.com/example/issue/123
```

## Code style guide

To create consistent and readable code please follow the guides:

### Python
- Before committing new python code make sure to run python-black via `$ black` , also check the github actions for per-project python linting, e.g. flake8 
- Style:
```python

# Underscores in variables:
variable_names = "things"

# Camel case in class names:
class ClassNames(object):
    pass

# Underscores in function names
def function_names():
    return 1
```

### HTML
- Indent with 2 spaces
- Style:
```html
<div>
  <p>Hi</p>
</div>
```

### JS
- Indent with 2 spaces
- variables and function names camelCase
- line endings using semi colons
- Style:
```js
function abcdAlpha(param){

}

let obj = {
  propertyA: 1,
  propertyB: 2,
};
```

 

