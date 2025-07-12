# Project Plan

Pod Members: **Jaqueline Jurado, Nathan Kenmognie, Taliyah Harvey**

## Problem Statement and Description

University students pursuing Computer Science often want to contribute to open-source software (OSS) to gain real-world experience and apply course concepts. However, existing tools require users to sift through long lists or read unfamiliar codebases, making it difficult to evaluate whether a project aligns with their coursework or skill level. There is currently no engaging, intuitive discovery experience tailored to students still exploring their interests or developing their technical confidence.

Our project, **branchout**, creates an engaging, swipe-based interface for CS students to explore open-source repositories one card at a time. It uses LLMs to generate easy-to-understand summaries and tags tied to coursework and skill level. Students select interests from common CS topics and receive personalized project recommendations. Feedback through swiping helps improve suggestions by filtering out projects that are too advanced or off-topic.



## User Roles and Personas

USER ROLES
A university-level computer science student who wants to explore and contribute to open-source projects based on their course knowledge and comfort level.
Faculty or teaching assistants who want to recommend OSS opportunities to students based on class content.

USER PERSONAS
Persona 1: Maya Delgado
Background: 19-year-old first-year CS major at a public university in California
Tech Access: Mostly uses her phone, occasionally a Chromebook
Motivation: Wants to get involved in CS communities early and build her GitHub profile
Pain Points: Gets overwhelmed by GitHub UI, doesn’t know which projects are beginner-friendly or relevant to her Intro to CS course

Person 2: Marcus Liu
Background: 21-year-old junior at an East Coast university studying CS and Cognitive Science
Tech Access: Uses a MacBook and GitHub regularly for coursework
Motivation: Looking for OSS projects related to AI and social impact to align with his electives and potential senior thesis
Pain Points: Finds it hard to tell if a repo is still active or worth contributing to; annoyed by vague READMEs

Persona 3: Elio Rune
Background: 22-year-old transfer student in her final year of undergrad
Tech Access: Comfortable with Git, uses laptop regularly
Motivation: Wants to boost her resume before applying to jobs, looking for frontend projects tied to full stack web development classes
Pain Points: Struggles to identify which OSS projects have good documentation or mentors willing to help new contributors.
Persona 4: Aisha Bennett
Background: 20-year-old sophomore at a HBCU in Georgia
Tech Access: Mainly uses phone for browsing and laptop for coursework
Motivation: Exploring various tech domains, still unsure about a specialization
Pain Points: Hasn’t contributed to OSS yet, feels most projects assume too much background knowledge

## User Stories

As a student contributor, I want to select my interests and skill level during onboarding, so that I receive OSS suggestions that align with what I want to learn and already know.

As a student exploring different CS paths, I want to browse OSS projects in a fun, swipe-based format, so that I can discover opportunities without feeling overwhelmed.

As a first-year or unsure student, I want to see simplified project summaries and course-aligned tags such as “Intro to Python basics” so that I can quickly understand what a project is about and how it connects to my classes.

As a student contributor, I want to view OSS projects with a visible star count and languages, so that I can gauge a project’s popularity and relevance.

As a confident or advanced student, I want recommendations that still challenge me but remain approachable, so that I stay engaged and continue growing as a future dev.

As a student building my resume, I want to find projects with active maintainers and good first issues, so that I can genuinely learn and develop technical skills that stick.

As a student with a rough experience prior, I want indicators that a project is beginner-friendly and welcoming, so that I feel safe trying again.

As a TA or instructor, I want to recommend OSS projects that align with our course material, so that students can apply what they learn in class to real-world code.

As a SWE professional, I want students to easily understand my project’s purpose and contribution pathways, so that contributing feels less “scary.”

As a student contributor, I want to filter out OSS projects that are “too advanced” or unrelated to course materials, so that future suggestions are more tailored to my needs.


## Pages/Screens

User Account Verification (with option to login/sign-up via Clerk)
- Sign-Up Page
- Login Page
Menu Drop-Down Modal
Discovery Page
Selected Repo Modal
Saved Repos Page
Profile Page
Preferences Page
About Page
Settings Page
- Change Password Modal
- Display Mode Modal (dark/light)
- Help Documentation Page
- Privacy Policy Documentation Page


## Data Model


## Endpoints

GET
/repo/
Get all repos
POST
/repo/
Insert new repo (from cron job or admin)
PUT
/repo/:id
Updates repo metadata 
GET
/repo/:id
Get repo by id
DELETE
/repo/:id
Delete a specific repo by its id
GET
/repo/filter
Get filtered repo list based on filters like skill level, languages, and tags that were chosen by the user. Multiple filter values are separated by “+”
GET
/repo/search?query=...
(STRETCH) (from api doc) For natural language search in stretch goals
POST
/repo/explain
(STRETCH) “Explain this repo to me” prompt via LLM 
GET
/user/:id
(admin only) Get current user info in a structured way, so a users skill level, languages, and tags
PUT
/user/:id
(admin only) Update info about user including skill level, languages, and tags
PUT
/user/password
(for any user, they get their own logged in info) Changes password if user doesn’t use Clerk UI
PUT
/user/profile
Adjust profile page information
GET
/user/profile
Displays user profile page
GET
/user/saved
Get all saved repos from a user
DELETE
/user/saved/:repoId
Unsave Repo
GET
/user/:repoId/feedback
Pulls users feedback
GET
/user/:id/discovery
Returns recommended repos based on user preferences, skill level, and past feedback
POST
/auth/signup
Used to create new user account
POST
/auth/login
Used to authenticate user account
POST
/auth/createAdmin
Used to create a new admin account
POST
/auth/clerkSync
Used by backend to communicate with clerk



***Don't forget to set up your Issues, Milestones, and Project Board!***
