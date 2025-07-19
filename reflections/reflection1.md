# Reflection #1

Pod Members: **Jaqueline Jurado, Nathan Kenmognie, Taliyah Harvey**

## Reflection Questions

* Name at least one successful thing this week.

 We were able to populate repositories with related information from the GitHub API, enriched by Gemini! Additionally, we were able to meet our frontend goals with significant steps to connect the backend (ie Users + their preferences are dynamic!).

* What were some challenges you and/or your group faced this week?

 To start, a challenge we faced encompassed user authentication as far as what are Admin vs User permissions. There was some rendering errors that prevented us from being able to test if preferences were dynamic.

 Secondly, a major challenge we faced and continue to face is regarding the CRON job, which is just a job that populates repos with their relevant information from the GitHub API + Gemini API enrichment. So there were a lot of expected hurdles when integrating both the APIs, solely because our group had never worked with either before - so that looked like activating keys, monitoring token usage, restrictions placed on the key itself, and being able to use the key in our applications. Then there were some specific challenges when it came to enriching the data with Gemini. This job was designed to be very modular in order to keep the main job file simple but also to allow multiple people to work on this major task - that being said, while one person worked on incorporating Gemini, another worked on the overall structure and bringing in GitHub. So when it came to combining them, there was a major learning curve and had to test very thoroughly. 
 
 As of now, the repo database is able to be populated with information like name, description, stars, etc, then also the AI generated summary, tags, and level through this job. However there are some ES module bugs preventing it from running correctly upon npm start (for backend).

* Did you finish all of your tasks in your sprint plan for this week? If you did not finish all of the planned tasks, how would you prioritize the remaining tasks on your list?  (i.e over planned, did not know how to implement certain features, miscommunication from the team, had to pivot from original plans, etc.)

 As a team we agree that we completed a lot more than planned - we were able to nearly complete the front end functionality (minus specific styling), we were able to pretty much finish the cron job that populates the repo database which makes it so all we have to do is show that on the front end, and we were able to get user authentication out of the way! The only things we had left to do is just some front ended things like having a "saved repos" page, and a header/footer component for aestethic. Therefore while we should prioritize these tasks prior to the start of the next sprint because it should be straightforward! For this sprint we felt like populating the repositories would be the key to being able to work with front-end specific tasks so we prioritized those, and should've planned it out like that originally.

* Did the resources provided to you help prepare you in planning and executing your capstone project sprint this week? Be specific, what resources did you find particularly helpful or which tasks did you need more support on?

Yes, as a team we agree that having the instructors and the SITE page push us to plan these sprints out made us feel 10x more excited and prepared for our product! We had a presentation from our lead instructor that helped us understand how we could integrate Jest and SuperTest for unit/integration testing, which aligns with what our mentors/managers highly suggested.

* Which features and user stories would you consider “at risk”? How will you change your plan if those items remain “at risk”?

The main feature currently at risk is the CRON job system responsible for pulling GitHub repo data and enriching it with Gemini-generated tags, summaries, and difficulty levels. While the core functionality is mostly complete, we’re running into ES module resolution errors that prevent it from executing smoothly on npm start. This impacts how confidently we can integrate and test it within the main backend flow, even though the job runs correctly when isolated.

Another feature at risk is dynamic preference rendering and saved repos, which depend on authenticated user context. While we’ve implemented the backend logic, frontend rendering bugs have blocked us from verifying that preferences update and display properly. Until we resolve that, features like personalized repo suggestions and “save this repo” remain unconfirmed.

To address these risks:

    For the CRON job, we’re planning to decouple it from the main application lifecycle, triggering it via a separate CLI or script. This reduces runtime complexity and allows for easier testing.

    We’ll also unit test the Gemini and GitHub integration modules in isolation using Jest, to ensure each step of enrichment behaves as expected.

    On the frontend side, we’ll set up mock user states and seed data to isolate whether rendering bugs are coming from the backend response or the frontend logic itself.

    If these issues persist, we’ll prioritize completing high-impact visual components like saved repos and user dashboards, while pushing stretch goals like "Explain this Repo" or more advanced AI features to the next sprint.

Overall, we’re still in a strong position — the repo data pipeline works in principle, and authentication is mostly solid. The next steps are mostly about stabilizing integration points and ironing out rendering flows so we can confidently demo end-to-end functionality.
