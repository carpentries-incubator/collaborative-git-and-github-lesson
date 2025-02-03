
---
title: Collaborative Version Control - Distributed
teaching: 10
exercises: 60
---

:::::::::::::::::::::::::::::::::::::::: questions

- How can I use version control to collaborate with external collaborators?

::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::::: objectives

- Understand distributed workflow and when to use it

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: instructor
Teaching is done as a pair of instructors. 
Instructor A acts as the owner of the repository, instructor B as a collaborator (internal or external).

Now we show distributed workflow. All in the browser using Github:

* Instructor A removes instructor B
* Instructor B now submits an issue
* Instructor A responds to issue asking instructor B to pick it up
* Instructor B forks repo, does some changes, and submits PR
* Instructor A reviews the changes
* Instructor B implements the changes
* Instructor A merges the pull request
* Use Github repo’s insights -> network to visualize what just happened 

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: challenge

### Exercise: Working as an external contributor (in pairs)

- PERSON A: Create an issue in Person B's repository
- PERSON A: Fork the repository to their own (= Person A's) account
- PERSON A: Clone the repository, make changes, push them back to the fork
- PERSON A: Submit a Pull Request from the fork to the original repository
- PERSON B: Make a change in the original repository in the same place as person A's proposed changes
- PERSON A: Solve the merge conflict in the Pull Request
- PERSON B: Review/Approve the Pull Request
- PERSON B: merge the Pull Request 
::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::: solution

::::::::::::::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::: keypoints
* Use distributed flow for external collaborations
::::::::::::::::::::::::::::::::::::::::::::::::::
