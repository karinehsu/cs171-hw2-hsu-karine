1) Contributors to a repository

Audience: project manager, contributor, and visitor. The visualization graph on the top shows the number of commits, excluding merge commits (as well as the ability filter to see only additions and deletions) each contributor contributes in relation to time for the entire repository. Below, the visualization shows the number of commits per user and ranks them from highest to lowest number of commits. 

Data used: username contributor logins, number of commits/additions/deletions, time series data

GitHub API:
GET /repos/:owner/:repo/stats/contributors
GET /repos/:owner/:repo/stats/commit_activity

If a contributor pushed many commits in a short time interval, the graph on the top would show a sudden peak in number of commits to master. This would be misleading because it would seem like many commits were made to master on average, but in reality, one contributor skewed the graph to create a large peak. This issue is addressed by denoting how many commits are actually pushed by each contributor, but I might also add in a hover function on the above graph to view the number of people who contributed to the graph during a certain peak.

Interactivity could have made it more fun so we could drag the timeline and "zoom in" but it definitely isn't necessary. The readability wouldn't be affected because more boxes are just added for each contributor.

2) Commits Activity 

Audience: project manager and contributor. The visualization graph on the top shows number of commits relative to time/date. 

Data used: number of commits/additions/deletions, time series data

GitHub API:
GET /repos/:owner/:repo/stats/contributors
GET /repos/:owner/:repo/stats/commit_activity

If a sole contributor pushed many commits in a short time interval, the graph on the top would show a sudden large bar on one of the dates. This would be misleading because it would seem like many commits were made to master on average, but in reality, one contributor skewed the graph to create a large peak. The issue of not being able to find outliers is not really addressed so it might be helpful to add in a hover function on the above graph to view the number of contributors who contributed to the graph during a certain peak.

Again, interactivity could have made it more fun so we could drag the timeline and "zoom in" but it definitely isn't necessary and works as a static graph. The readability might be affected because the more data that is put into the bar chart, the more the scale will have to change. 

3) Code Frequency

Audience: project manager, contributor, visitor. This visualization graph show additions above the center x-axis  and deletions to the repository as below the center x-axis. 

Data used: additions, deletions, frequency

GET /repos/:owner/:repo/stats/commit_activity
GET /repos/:owner/:repo/stats/code_frequency

If a contributor pushes many commits in a short time interval, either additions or deletions, the graph will show two equally sized peaks moving in opposite directions. To address this issue, we could set a hover function that showed what the peak of commits really is and also how many users contributed to the additions/deletions peaks in a certain day. 

I think in this case interactivity would have made it better so that we could drag the timeline and "zoom in". The static graph doesn't work as much here. The readability might be affected because the more data that is put into the bar chart, the more the scale will have to change. 

4) Punchcard

Audience: project manager. This visualization shows the daily and hourly number of commits. 

Data used: Number of commits/day, time series data
GET /repos/:owner/:repo/stats/punch_card

If a contributor pushes many commits in a short time interval, the circle will increase in size. However, the circle is limited to a certain size in the punch card visualization, so we might have to denote even bigger increases in commits by changing the color tints of circles to darker to relate to more activity. 

5) Pulse of a repository

Audience: Project manager and visitor. This visualization shows us the number of pull requests, commits, how many files have changed, and issues that need to be addressed/have been addressed. 

Data used: Contributors, timeline of commit/edit 

GET /repos/:owner/:repo/stats/commit_activity

If a contributor pushes many commits in a short time interval, the bar chart will show larger bars, and the number of authors/commits will change. The color scale that shows number of pull requests and active issues also addresses the issues by changing the size dynamically based on percentage of requests. 

Interactivity could have worked here to show more than just a weekly time interval. If we had interactivity we could show a monthly time interval and more. Readability will be affected here so we should scale the cirlces accordingly. 

6) GitHub Network Graph: 
Audience: Project user or visitor or contributor. This visualization shows the relationships between users, branches, commits, and merges. 

Data used: master branches, number of forks/merges

Github API:
GET /repos/:owner/:repo/forks
GET /repos/:owner/:repo/stats/commit_activity
GET /repos/:owner/:repo/stats/contributors

Role of interaction is to see how the network of a repository looks like in terms of how many forks/commits/merges were created and when. The interaction allows you to move the timeline and also see the different versions. If many developers suddenly joined the project and pushed commits, there would be more nodes and new branches created. Currently, the graph's readability is preserved by changing the time scale so the nodes are spread further apart. Alternatively, the nodes could be clumped together into one node so size indicates amount of activity, or the nodes could be a different shade of whatever color the branch is.

7) Calendar map 

Audience: Project user or visitor. This shows relative activity based on how much an individual contributes or works on their github account.

Data used: univariate time series data

GET /repos/:owner/:repo/stats/commit_activity

The colors of activity become darker green to demonstrate higher levels of activity. It changes relative to what has been done before. I think changing the color scale is a good way to address the issue. 

The interactivity of the graph makes it nice to zoom into a specific area of a graph and then also move the graph to see the bigger timeline. 


