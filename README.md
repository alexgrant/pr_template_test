We have been using one template to cover what are effectively 3 different review processes:
- Over-the-shoulder review + regular code review
- Two regular code reviews
- Nearly rubber-stamp approvals for merging release branches

All of these have their place, but none are suitable for every task:
- OTS is more in-depth and thorough, but is time consuming and requires interrupting another person.
- Regular code reviews are asynchronous and thus less disruptive to other team members, but provide less assurance.
- Release branch process is basically 'could someone click the approve button?'

The trouble is that it's hard to acommodate all review processes in one template. Github supports having multiple PR templates, but offers no UI for choosing one when creating a PR - instead one has to append a `template=my_template.md` query parameter. Until they grace us with a dropdown I have approximated a 'UI' here by having the default template load only a bit of content to help choose the right query parameter.

For the 'two regular reviews' process to continue to work with low friction both reviewers must have the same review scope - else it will inevitably lead to confusion about who needs to cover what. This is why the async template proposed here has both reviewers check acceptance criteria is met - the expectation being that for small tickets that should not add much work.

OTS is a different story as it is synchronous. When a colleague asks for an OTSR, it takes precedence over most other tasks and thus the reviewer roles are quickly decided in public. The assumption here is that ensuring Acceptance Criteria is fully met will take a while, hence only the OTS reviewer is required to do that. 
Alex pointed out that this feels wrong - two AC reviewers for less complex tasks, and only one for more complex tasks. I agree, but I think this is less bad than requiring two checks for acceptance criteria - it can be an exhausting task.



To try it out go ahead and create a PR:
- open the [readme](https://github.com/seminolas/pr_template_test/blob/main/README.md) file
- click the pencil icon in the upper right corner
- make a change, click 'propose' to create a new branch and a PR
- in the 'create PR' screen click the 'preview' tab, choose a template and paste appropriate query parameter string in the address bar; click enter
- the PR description text area should now be populated with the contents of the chosen template.
- to try another one, just click back and choose another template.

Obviously it's not frictionless. To make it less annoying you could create simple bookmarklets with URLs like 
```
javascript:void(let url = new URL(window.location.href); url.searchParams.set('template', 'ost.md'); window.location.href=url;)
```
Github also tries real hard not to forget what you entered in the text area, which might at times get in the way.
Please voice your opinions in slack - it's our process, it should work for us.

Test change
