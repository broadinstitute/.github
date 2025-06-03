# Broad Institute default files

Files defined here either propogate or define certain default behavior in all
broadinstitute repositories. See
[the .github documentation](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
for more information.

## Contribution guidelines

Currently, the only feature we are taking community contributions for is
[workflow templates.](https://docs.github.com/en/actions/sharing-automations/creating-workflow-templates-for-your-organization)
We are open to supporting other `.github` features though -- please contact the
devnull team in #github or #team-devnull if there is something you believe the
organization would benefit from.

### Commit guidelines

All commits should follow these abridged standard formatting rules:

* Separate subject from body with a blank line
* Limit the subject line to 50 characters
* Capitalize the subject line
* Do not end the subject line with a period
* Use the imperative mood in the subject line
* Wrap the body at 72 characters
* Use the body to explain what and why vs. how
  *This is the most important rule by far!*

For an in-depth explanation about where these are from and why they're
important, see
[this excellent blog post on Git hygiene.](https://cbea.ms/git-commit/)
These rules are a subset of the patch submission guidelines used
[on the git project itself.](https://github.com/git/git/blob/master/Documentation/SubmittingPatches)
Since they are so common, most text editors will help you out with
automatic formatting and syntax highlighting with minimal configuration.

### Adding a workflow template

We encourage any Broadie to submit a PR to make their template available to the
entire organization if they so choose. When you do, we ask that you follow the
following instructions. In addition to keeping the repo organized, our goal with
these standards is to avoid any workflow appearing prescriptive. Since these
templates are visible to the entire organization, users browsing them should
have clear information about their provenance and be able to choose tools that
fit their needs.

#### Naming conventions

* Namespace your workflows by prefixing the files with your team
  name. e.g. `bits-python-ci.yml`, instead of `python-ci.yml`.
* Use `.yml` as a file extension, not `.yaml`.
* Use `kebab-case` for all file names.
* Have the file name be reasonably
  descriptive. e.g. `bits-markdown-linting.yml`, not `bits-toolbox.yml`.

#### The whole Broad is your audience

When adding a new workflow, keep in mind that it will be visible to all Github
users at the Broad Institute. Most will not know you or be familiar with your
team's tech stack. At the same time, BITS believes that sharing technology at
the Broad benefits everyone and that we should facilitate reuse of common
patterns. To the extent possible, try to make your workflow generalizable:

* Avoid hardcoding your team name in the workflow or referencing nonstandard
  resources without explanation.
* Use comments in the workflow file to document parts that may not be clear
  without context.
* The metadata file should include your team's name in the `name` field.
* Have a verbose description. Do not simply re-phrase the `name` field. e.g.
  instead of "Python linting for BITS", consider "Python static analysis checks.
  Uses ruff for formatting and linting and pyright for type hinting."
* Make use of the `categories` metadata field when possible.

#### Add your files to CODEOWNERS

While we want to keep this repo manageable, we also want to give teams enough
leeway to maintain their own tools without constantly getting in their way. When
adding your workflow template, add both files to
[CODEOWNERS](https://github.com/broadinstitute/.github/blob/main/.github/CODEOWNERS) along with your team. This way, after the
initial PR, teams can update and modify their own workflows without waiting on
review from BITS. More details are available in the CODEOWNERS file.
