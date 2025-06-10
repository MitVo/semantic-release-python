# Custom Semantic Release for Python

A customized GitHub Action to automate semantic versioning and changelog generation for Python projects using [semantic-release](https://github.com/semantic-release/semantic-release) and [gitmoji](https://github.com/carloscuesta/gitmoji).

## 🚀 Features

- Automated semantic versioning based on commit messages (supports gitmoji).
- Generates and updates changelogs using custom Handlebars templates.
- Supports both standard and prerelease workflows.
- Customizable for cloud function modules.

## 📦 Usage

Add this action to your workflow:

```yaml
- name: Run Custom Semantic Release
  uses: ./  # or use your repository path
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}

```

## 🔧 Inputs    
| Name	| Description	| Required	| Default |
|-------|------|------|------|
| github_token	| GitHub token for authentication	| Yes	| |
| release_branch	| Branch to perform the release from	| No	| master |


## 📤 Outputs
| Name	| Description |
|-------|---------|
| release_version |	The version of the release created |

## 📝 Configuration
- The action copies .releaserc.js, .prerelease-releaserc.js, package.json, and Handlebars templates to the workspace.
- Uses semantic-release-gitmoji for commit parsing.
- Custom changelog templates are in the templates/ directory.

## 🛠️ Development
- Node.js 20 is required.
- Installs all dependencies at runtime.
- See action.yml for the full workflow.

## 🚨 Prerequisites
- The image use to run the workflow must have installed Python with the dependencies `build twine bump2version` before execute the semantic release action.
- The Python project needs to have a `.bumpversion.cfg` file configured with the specification of the project, see an example in [here](https://pypi.org/project/bump2version/) .


## 📄 Sources
- [Bump2version Tool](https://pypi.org/project/bump2version/) 
- [semantic-release tool](https://github.com/semantic-release/semantic-release)
- [semantic-release configuration file](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md)
- [gitmoji plugin](https://github.com/momocow/semantic-release-gitmoji)
- [Handleebars](https://handlebarsjs.com/)
- [Github Actions Guide](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)