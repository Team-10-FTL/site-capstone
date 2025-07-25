# Reflection #2

Pod Members: **Jaqueline Jurado, Nathan Kenmongie, Taliyah Harvey**

## Reflection Questions

* Name at least one successful thing this week.

We were able to get a depoloyed versino of our site up and running! We also were able to get a recommendation algorithm working that takes right and left swipes, with left swipes associated with negative feedback for the algorith. It now accurately suggests repositories to the user based on their preferences AND feedback. 

* What were some challenges you and/or your group faced this week?
Some challenges we faced heavily regarded deployment early this week where Render had less support for an application that used Clerk for authentication. Therefore we had to buy a domain for our application and make sure routes were accessible to different public users. Another challenge regarded the recommendation algorithm itself - we had planned out to use very specific technologies to built the recommendation functions but we later found out they couldn't work across different languages (ie were mismatched with no good way to have them communicate data) and what we wanted to do required multiple users to recommend trending type of topics and repositories with the same preferences. We ended up having to move away from that and to a simpler algorithm. We now wait to have a certain amount of users to incorporate trending topics/repos.

* Did you finish all of your tasks in your sprint plan for this week? If you did not finish all of the planned tasks, how would you prioritize the remaining tasks on your list?  (i.e over planned, did not know how to implement certain features, miscommunication from the team, had to pivot from original plans, etc.)
We did finish all our tasks planned for our sprint, concluding our MVP. If anything, we had certain UI tweaks we could've gotten to, but that was outside of the logic we wanted to complete for MVP. For the remaining tasks, we have labeled those in part to the upcoming stretch feature week. The only major pivot we had was regarding the UI and the recommendation algorithm as previously mentioned, but we were still able to get MVP-level accomplishments.

* Did the resources provided to you help prepare you in planning and executing your capstone project sprint this week? Be specific, what resources did you find particularly helpful or which tasks did you need more support on?

The instructors and code snippets for connecting front end to backend were consistently really helpful! Even though our application veered from the applications taught to us during the first couple of weeks, we were able build upon what we knew. The documentation for the deployment site, for the recommendation algorithm functions, for Materials UI library, and for useEffect-useState/React in general were all extremely intuitive and helpful.

* Which features and user stories would you consider “at risk”? How will you change your plan if those items remain “at risk”?

The deployed version of the site still doesnt allow certain logins using Clerk which doesn't allow them to progress through the pages. Before next week's Bug Bash event across the class, we will try to improve this and the amount of rendering that potentially might slow down our application. 
