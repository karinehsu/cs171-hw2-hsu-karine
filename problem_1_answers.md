1. Calendar map 

Audience: Who is the audience? Project user (e.g. project manager, contributor, project user, visitor, etc.)
Audience: Project user or visitor. This shows relative activity based on how much an individual contributes or works on their github account.

Data used: univariate time series data

How can you get the data using the GitHub API? (Note that it can be the combination of multiple queries and their processing).

Those visualizations are updated over time. What happens if suddenly a contributor pushes many commits in a short time interval? How would you address this particular issue?

The colors of activity become darker green to demonstrate higher levels of activity. It changes relative to what has been done before. 

2. Contributors to a repository

Audience: project manager, contributor, and visitor. 

Data used: GET /repos/:owner/:repo/stats/contributors
GET /repos/:owner/:repo/stats/commit_activity

How can you get the data using the GitHub API? (Note that it can be the combination of multiple queries and their processing).
GET /repos/:owner/:repo/contributors

Those visualizations are updated over time. What happens if suddenly a contributor pushes many commits in a short time interval? How would you address this particular issue? This issue is addressed by incrementing the number of commits...? 

3. Commits Activity 

Data used: GET /repos/:owner/:repo/contributors
GET /repos/:owner/:repo/stats/contributors
GET /repos/:owner/:repo/stats/commit_activity

4. Code Frequency

Data used: GET /repos/:owner/:repo/contributors
GET /repos/:owner/:repo/stats/contributors

5. Punchcard

Audience: project manager 
Data used: GET /repos/:owner/:repo/stats/punch_card

Daily and hourly number of commits 


6. Pulse of a repository

Audience: Project manager and visitor

Data used: Contributors, timeline of commit/edit 

GET /repos/:owner/:repo/stats/commit_activity

7. GitHub Network Graph: 
Audience: project manager and visitor 

Data used: master branches, number of forks/merges

Github API:
GET /repos/:owner/:repo/forks

Role of interaction is to see how the network of a repository looks like in terms of how many forks/commits/merges were created and when. The interaction allows you to move the timeline and also see the different versions. If many developers suddenly joined the project and pushed commits, there would be more nodes and new branches created. Currently, the graph's readability is preserved by changing the time scale so the nodes are spread further apart. Alternatively, the nodes could be clumped together into one node so size indicates amount of activity, or the nodes could be a different shade of whatever color the branch is.