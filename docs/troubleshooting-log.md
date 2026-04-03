Date: 2026-04-01
Lab Day: Setup Phase

Issue:
zsh parse error when running `git remote add origin <repo>`

Error message:
zsh: parse error near `\n`

Root Cause:
The placeholder `<repo>` was interpreted by zsh as input redirection instead of a literal string.

Resolution:
Replace the placeholder with the actual GitHub repository URL.

Correct command example:
git remote add origin https://github.com/carloschongdev/devops-lab-claude.git

Lesson Learned:
Angle brackets in documentation are placeholders and should not be typed literally in shell commands.