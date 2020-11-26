We have been using one template to cover what are effectively 3 different review processes:
- Over-the-shoulder review + regular code review
- Two regular code reviews
- Nearly rubber-stamp approvals for merging release branches

All of these have their place, but none are suitable for all PRs:
- OTS is more in-depth and thorough, but is time consuming and requires interrupting another person.
- Regular code reviews are asynchronous and thus less disruptive to other team members, but provide less assurance.
- Release branch process is basically 'could someone click the approve button?'

The trouble is that it's hard to acommodate all review processes in one template. Notably, for the 'two regular reviews' process to continue to work with low friction both reviewers must have the same review scope - else it will inevitably lead to confusion about who needs to cover what. It's not a problem with OTS as it is synchronous. When a colleague asks for an OTSR, it takes precedence over most tasks and thus the reviewer roles are decided quickly and publicly.

Github supports having multiple PR templates, but offers no UI for choosing one when creating a PR - instead one has to append a `template=my_template.md` query parameter. Until they grace us with a dropdown I have approximated a 'UI' here by having the default template load only a bit of content to help choose the right query parameter.

To try it out go ahead and create a PR:
- click the pencil icon in the upper right corner of this readme
- make a change
- choose to create a new branch in the bottom
- choose a template and paste appropriate query parameter string in the address bar
- the PR description text area should now be populated with the contents of the template.
- to try another one, just click back and choose another template.

Obviously it's not frictionless. Github also tries real hard not to forget what you entered in the text area, which might at times get in the way. Please voice your opinions - it's our process, it should work for us.
