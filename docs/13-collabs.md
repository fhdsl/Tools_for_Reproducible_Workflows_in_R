
# Collaborations through GitHub



![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g21a84b32106_0_68.png){width=100%}

## Components of collaborating on GitHub

As noted previously, GitHub is not only great for sharing and version control but, it is also great for collaborating!

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g341dc8b716d_0_6.png){width=100%}

This collaboration can be done through the use of issues and pull requests!

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g341dc8b716d_0_0.png){width=100%}
### Step 1. A problem identified/issue created

[GitHub issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues) are where we can note, plan, and discuss work for a project. It might first be filed by one person but then used for further discussion between multiple people to define a problem or new request. Once the issue is scoped and defined enough it can be assigned to someone to work on it.

### Step 2. Proposing a solution

Creating a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) is proposing a solution that addresses the original issue. The author of the pull request creates a new branch with the necessary changes to address the issue. The pull request description should reference the original issue to explain what problem or request the work is addressing. It should also explain how the work addresses it. Finally, a reviewer can be requested for feedback. 

### Step 3. Reviewer looks at proposed solution

Now the reviewer is given a chance to look at the proposed solution and approve and or otherwise improve it in collaboration with the original author.

### Step 4. Refined solution is deployed

Once both the author and the reviewer agree the work is ready, the changes can  be merged and [deployed to the main branch](https://hutchdatascience.org/Tools_for_Reproducible_Workflows_in_R/using-github-in-a-workflow.html#whats-github)! Yay! Time to celebrate.

:::dictionary
The main branch is the ground truth branch where the final product of the code is created from. Development branches on the other hand, propose changes that can be added to the main branch. 
:::

Now the process can be repeated for the next issue!

## Issues should tell us:
- What the problem is - including examples or screenshots to demonstrate the problem.
- What solution(s) could address the problem?
- Who might be assigned to addressing this problem?
- Potentially what timeline or urgency the problem has.

## Pull Requests should tell us:
- What issue is the work addressing?
- How is it addressing the issue?
- What pitfalls exist?
- What should be looked at and reviewed carefully.

## Engaging in Code Review - as an author

The only way to know if your analysis is truly reproducible is to send it to someone else to reproduce! That sentiment is at the heart of code review.

@Parker2017 describes code review:

> Code review will not guarantee an accurate analysis, but it’s one of the most reliable ways of establishing one that is more accurate than before.

Not only does code review help boost the accuracy and reproducibility of the analysis, it also helps everyone involved in the process learn something new!

An effective code review atmosphere is something that individuals and their team have to _commit_ to (pun intended). Effective code review brings so many benefits not only to your project quality but also to your communication skills through fostering a learning atmosphere!

In this chapter we will discuss the two sides of code review. Code review ideally includes at least two people: the author of the pull request and the reviewer of the pull request. Depending on your job context, we realize that sometimes authors have to become their own reviewers. This might happen if your team is small or the authors are the only people with a particular skill set.

## Author responsibilities in code review

The code review process begins with the creation of a pull request (which we practiced in the [previous chapter](https://hutchdatascience.org/Tools_for_Reproducible_Workflows_in_R/using-github-in-a-workflow.html#opening-a-pr)). Successful and efficient code review is born out of quality communication, which is a skill set on its own. You can set your reviewers (and yourself) up for success by knowing what basic information can help get the code review conversation going.

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2369.png){width=100%}

Even if you end up reviewing your own code, writing the following information out is still very helpful and highly recommended. It can help you spot problems you might not have otherwise seen and generally help you document your code better for future you!

## Characteristics of great pull requests and issues

### There's plenty of context!

What's the story behind the changes you are proposing? Sometimes when we are in the thick of a project we can make the mistake of assuming everyone knows what we know. This can unfortunately leave a huge burden on your reviewer to try  to understand what you are doing.

Before sending off a review request, re-read your PR description and think about the perspective of your reviewer. Err on the side that they have no idea what is happening on the project (because sometimes this is the case!)

Tell a short story to explain what lead to you making these changes including attempting to answer these questions:  

- What is the problem that these changes will solve?
- Do you have any URLs, relevant issues, or files you can share?
- What inspired you to take this approach -- are there other things you tried?
- Are there other pull requests related to this change?


:::notice
You can type the world "resolves" and then include the issue number with a `#` and it will close the issue when you merge the pull request
:::


:::notice
You can type the world "resolves" and then include the issue number with a `#` and it will close the issue when you merge the pull request
:::
### Includes an explicit request for what kind of feedback is needed

What would you like your reviewer to do with this pull request? Stating this explicitly can save both of you time in this code review process.

- Are you still in the early stages and looking for a bigger picture review? Let them know that before they waste their time digging into the code line-by-line.
- Are you in the later stages and looking for a detailed nit-picky review?
- Are you looking for feedback on the results or methods?

### Points out questionable areas that need extra attention

Are there specific areas of the code you are having trouble with or are unsure about? Send a link to the [specific lines in GitHub](https://stackoverflow.com/questions/23821235/how-to-link-to-specific-line-number-on-github) you are asking about. Are there results that are surprising, confusing, or [smell wrong](https://github.com/jennybc/code-smells-and-feels#code-smells-and-feels)?  

Be sure to detail what you have dug into and tried at this point for any problematic points.  This can help the reviewer to avoid suggesting potential solutions that the author has already tried. 

### Are relatively small and focused

Try to make sure your pull requests aren't too long! Code reviewing fatigue is very real. If you send a reviewer thousands of lines of code to review it will be very overwhelming to review or understand.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">10 lines of code = 10 issues.<br><br>500 lines of code = &quot;looks fine.&quot;<br><br>Code reviews.</p>&mdash; I Am Devloper (@iamdevloper) <a href="https://twitter.com/iamdevloper/status/397664295875805184?ref_src=twsrc%5Etfw">November 5, 2013</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Alternatively, when you create a new branch try to set a very intentional (and relatively small) goal you would like to achieve with your upcoming pull request. Keeping your pull requests small and focused on one task at a time will not only help your reviewers but also will help yourself feel more accomplished and organized.

Also recall that incremental changes are good! Perhaps you do have a very large restructuring of your repository you are trying to accomplish, but finding smaller reasonable sets of changes (which would each have their own pull requests) to reach that goal incrementally can help keep things more manageable. This can also be very valuable if you decide that you want to go back to a previous version. It can be easier to tell when a change was introduced if you have smaller pull requests. 

:::notice
If you have changes that might be interdependent, you can make a pull request based on another existing pull request, using something called [stacked pull requests in GitHub](https://blog.logrocket.com/using-stacked-pull-requests-in-github/).
:::

### Don't ask a reviewer to dig through dirty code

Determining when a pull request is fully cooked and ready for review is a skill in itself. Pull requests that haven't had enough time to be polished can put an unnecessarily large burden on the reviewer. On the other hand, pull requests that have been hashed and rehashed in a silo might have benefitted from big picture feedback at an earlier stage of the code. This balance is something that you and your team can figure out in time using lots of communication!

This being said, the first reviewer of your code should always be yourself! Take time to review your own changes by clicking on the `Files Changed` tab and going over that section carefully.

- Are all the changes included that you were expecting?
- Are there any changes you didn't expect that are showing up? These can be symptomatic of a deeper problem. Definitely dig into anything that is not what you expected.
- Set aside your changes and return them in a few hours, or the next day. Looking at your changes with fresh eyes may also allow you to find things you didn't notice before.

Additional tip, if you don't want others to look at your pull request yet because you are still working on reviewing it, you can change it to [a draft pull request](https://github.blog/2019-02-14-introducing-draft-pull-requests/) so no one reviews it before you are ready. This can also be a handy tactic to use if you just want to ask for big picture feedback from someone but want to make it clear that the pull request is not anywhere near ready for merging to main.


![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2555.png){width=100%}

### Pull Request Templates

Add a [pull request template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository) to your repository! This will help initiate consistent and clear communication around the pull requests in your repository.

Pull request templates are a way to give yourself and other contributors prompts when starting a new pull request. See below for an example. The comments between `<!--` and `-->` are html comments that will not show up so you don't need to delete them if you don't want to. On the right side, it shows how this template looks when it's rendered. You can see this at any time by clicking `Preview` -- this is true in other places in GitHub.

![](resources/images/13-collabs_files/figure-docx//1IJ_uFxJud7OdIAr6p8ZOzvYs-SGDqa7g4cUHtUld03I_gfa97af8537_0_0.png){width=100%}


![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2614.png){width=100%}

### Preparing for the return of your review

As you wait for your reviewer to get back to you, it can be helpful to remind yourself what the purpose of code review is to get yourself in a positive mindset. You've given your reviewer information to help them help you and now is the time to wait.

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2614.png){width=100%}

First of all, you should pat yourself on the back for engaging in code review. It does require more time and sometimes that can feel scary with looming deadlines, but kudos for being able to prioritize your commitment to creating increasingly more reproducible analyses! Furthermore, it can ultimately save you time over more extensive projects by keeping everyone up-to-date!

Remember that you are not your code and mistakes are all a part of the process! Putting your project out there can feel a tad vulnerable. You may have felt the impulse to keep your code's problems buried under a rug, but you pushed past that and are making your analyses transparent! Remember that hidden problems don't get solved, but known problems are opportunities for reaching an even better end result!

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2625.png){width=100%}

When you receive a review back remember that you and the reviewer are on the same team and both want the best end result feasible for this project! They may suggest ideas that you love and can't wait to implement. They also might suggest ideas you don't agree with. Do your best to take all their comments as positive learning opportunities and look for ways to compromise and determine solutions collaboratively.

## Engaging in Code Review - as a reviewer

When reviewing a pull request, you take on responsibility to ensure that the pull request is getting the project to a better state than before.

There are three aspects to reviewing we will focus on:  

1. Identify areas in the code and documentation that are opportunities for improvement.
2. Communicate your questions and concerns effectively and in a way that creates a positive atmosphere.
3. Determine solutions collaboratively in a way that allows for learning as well as a long-term improved product.

### What to look for!

Depending on the goals of the project, and pull request there can be a lot to keep an eye out for. There are [many articles out there about what to look for in a code review](https://github.com/joho/awesome-code-review#articles).

_Here's some general points:_  

- Does the analysis answer the question it's asking? Are the methods it uses to do so appropriate?
- Is the code clear and readable? Does it contain a healthy amount of comments and documentation for individuals not familiar with the project to understand generally what is going on?
- Is the code efficient with computational resources? (Are there areas that are a bit too greedy with memory usage?)
- Does the code stick to the style and conventions of this project?
- Are there alternate scenarios where the current strategy might fail? (depending on the likelihood, this may be an instance for a new issue and another pull request).

### How to communicate it

The pull request may be the author’s precious bundle. Try to be empathetic to the learning process! You are both working on this project together -- assume you both want the best out of this project. If something seems wrong, work together to find a solution, don't ever waste time on placing blame.

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2647.png){width=100%}

Remember that everything sounds harsher when you don't have in-person cues! In this example, Avi may be stating factual things, but without his pleasant and reassuring disposition, it can feel super harsh.

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2653.png){width=100%}

If Avi had reframed his comments, they might be more effective in this collaboration. @Babatunde2018 suggests framing [review comments in three ways to help communication: questions, suggestions, and appreciations](https://medium.com/@otarutunde/comments-during-code-reviews-2cb7791e1ac7).

#### Questions

_For example:_  

> What happens if this doesn’t get saved? Does it throw an exception or fail silently?

The key is to be specific with the questions. Mention exact file names. Put comments on the line you are referring to. Explain what you think is happening and ask them to explain if that is correct.  

#### Suggestions

_For example:_  

> I suggest you use an ArrayHelper getValue method here because of its error handling capability instead of accessing the value directly
You could even go further by giving an example:
$a = $b[‘key’]; would raise an error if key is not set but $a = ArrayHelper::getValue($b, ‘key’); would return a null value if key is not set.

Giving suggestions and explaining not only how to implement them but why they might be preferred in this scenario is a great learning process both for the author and yourself.

#### Appreciations

Start every review comment with appreciation for the hard work completed! This goes a long way for creating a positive atmosphere.

_For example:_  

> Nice Job! Alice. I suggest we create an interface for this service so other substitute services can implement the interface as well, this would enable us change to a different service with very minimal efforts when the need arises. What do you think?

Let's see how Avi's message could have been reworked to give a more effective review:  

![](resources/images/13-collabs_files/figure-docx//1MNHf8JpolaEP_vQ_kB-1xRBF9wo3haCArRu117hBoHA_g33bf0789107_300_2679.png){width=100%}

This interaction reminds us that effective code review is steeped in empathy from both sides. Authors need to appreciate the time and effort the reviewer is spending to help them; while reviewers need to be sensitive to the amount of effort put in by the author already.

#### Recommended reading about code review

- [Why code reviews matter (and actually save time!)](https://www.atlassian.com/agile/software-development/code-reviews) by @Radigan2021.
- [Pull request descriptions](https://www.pullrequest.com/blog/writing-a-great-pull-request-description/) by @Banuelos2020.
- [A zen manifesto for effective code reviews](https://www.freecodecamp.org/news/a-zen-manifesto-for-effective-code-reviews-e30b5c95204a/) by @Fabre2019.
- [Best practices for Code Review](https://smartbear.com/en/learn/code-review/best-practices-for-peer-code-review/) by @Smartbear2021.
- [Comments during Code Reviews](https://medium.com/@otarutunde/comments-during-code-reviews-2cb7791e1ac7) by @Babatunde2018
- [On Empathy and Pull Requests](https://slack.engineering/on-empathy-pull-requests/) by @Hirpa2016.
- [Code Review Guidelines for Humans](https://phauer.com/2018/code-review-guidelines/) by @Hauer2018.
- [Your Code Sucks! – Code Review Best Practices](https://quickbirdstudios.com/blog/code-review-best-practices-guidelines/) by @Hildebr2020.
- An even longer list of [readings about code review](https://github.com/joho/awesome-code-review)
