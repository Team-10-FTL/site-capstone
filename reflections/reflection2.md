# Reflection #2

**Pod Members:** Jaqueline Jurado, Nathan Kenmongie, Taliyah Harvey

## Reflection Questions

### 1. Name at least one successful thing this week.

We were able to get a deployed version of our site up and running! We also were able to get a recommendation algorithm working that takes right and left swipes, with left swipes associated with negative feedback for the algorithm. It now accurately suggests repositories to the user based on their preferences and feedback.

---

### 2. What were some challenges you and/or your group faced this week?

Some challenges we faced heavily regarded deployment early this week, where **Render** had less support for an application that used **Clerk** for authentication. Therefore, we had to buy a domain for our application and ensure routes were accessible to different public users.

Another challenge was the recommendation algorithm itself — we had planned to use very specific technologies to build the recommendation functions, but later found out they couldn't work across different languages (i.e., they were mismatched with no good way to communicate data). Additionally, what we wanted to do required multiple users to recommend trending topics and repositories with the same preferences. We ended up pivoting to a simpler algorithm. We are now waiting to have a certain amount of users to incorporate trending topics/repos effectively.

---

### 3. Did you finish all of your tasks in your sprint plan for this week?  If you did not finish all of the planned tasks, how would you prioritize the remaining tasks on your list?  (i.e., over-planned, did not know how to implement certain features, miscommunication from the team, had to pivot from original plans, etc.)*

We did finish all our tasks planned for this sprint, concluding our **MVP**. If anything, we had certain UI tweaks we could've gotten to, but that was outside the core logic we wanted to complete for MVP. For the remaining tasks, we have labeled those as part of the upcoming **Stretch Feature Week**.

The only major pivot we had was regarding the **UI** and the **recommendation algorithm**, as previously mentioned, but we were still able to accomplish MVP-level functionality.

---

### 4. Did the resources provided to you help prepare you in planning and executing your capstone project sprint this week?  
Be specific — what resources did you find particularly helpful, or which tasks did you need more support on?

The instructors and code snippets for connecting **frontend to backend** were consistently very helpful! Even though our application veered from the applications taught during the first couple of weeks, we were able to build upon what we learned.

The documentation for:
- Deployment platform (Render),
- Recommendation algorithm functions,
- **Material UI** library,
- React hooks (**useEffect**, **useState**),

were all extremely intuitive and helpful.

---

### 5. Which features and user stories would you consider “at risk”?  
How will you change your plan if those items remain “at risk”?

The deployed version of the site still doesn’t allow certain logins using **Clerk**, preventing users from progressing through the application. Before next week's **Bug Bash** event across the class, we will prioritize fixing this issue.

Additionally, we aim to optimize the rendering performance that could potentially slow down the user experience.
