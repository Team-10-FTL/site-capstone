# Project Plan

Pod Members: **Jaqueline Jurado, Nathan Kenmognie, Taliyah Harvey**

## Problem Statement and Description

University students pursuing Computer Science often want to contribute to open-source software (OSS) to gain real-world experience and apply course concepts. However, existing tools require users to sift through long lists or read unfamiliar codebases, making it difficult to evaluate whether a project aligns with their coursework or skill level. There is currently no engaging, intuitive discovery experience tailored to students still exploring their interests or developing their technical confidence.

Our project, **branchout**, creates an engaging, swipe-based interface for CS students to explore open-source repositories one card at a time. It uses LLMs to generate easy-to-understand summaries and tags tied to coursework and skill level. Students select interests from common CS topics and receive personalized project recommendations. Feedback through swiping helps improve suggestions by filtering out projects that are too advanced or off-topic.



## User Roles and Personas

USER ROLES
  1. A university-level computer science student who wants to explore and contribute to open-source projects based on their course knowledge and comfort level.
  2. Faculty or teaching assistants who want to recommend OSS opportunities to students based on class content.

USER PERSONAS
Persona 1: Maya Delgado
  - Background: 19-year-old first-year CS major at a public university in California
  - Tech Access: Mostly uses her phone, occasionally a Chromebook
  - Motivation: Wants to get involved in CS communities early and build her GitHub profile
  - Pain Points: Gets overwhelmed by GitHub UI, doesn’t know which projects are beginner-friendly or relevant to her Intro to CS course

Person 2: Marcus Liu
  - Background: 21-year-old junior at an East Coast university studying CS and Cognitive Science
  - Tech Access: Uses a MacBook and GitHub regularly for coursework
  - Motivation: Looking for OSS projects related to AI and social impact to align with his electives and potential senior thesis
  - Pain Points: Finds it hard to tell if a repo is still active or worth contributing to; annoyed by vague READMEs

Persona 3: Elio Rune
  - Background: 22-year-old transfer student in her final year of undergrad
  - Tech Access: Comfortable with Git, uses laptop regularly
  - Motivation: Wants to boost her resume before applying to jobs, looking for frontend projects tied to full stack web development classes
  - Pain Points: Struggles to identify which OSS projects have good documentation or mentors willing to help new contributors.
  - Persona 4: Aisha Bennett
  - Background: 20-year-old sophomore at a HBCU in Georgia
  - Tech Access: Mainly uses phone for browsing and laptop for coursework
  - Motivation: Exploring various tech domains, still unsure about a specialization
  - Pain Points: Hasn’t contributed to OSS yet, feels most projects assume too much background knowledge

## User Stories

  1. As a student contributor, I want to select my interests and skill level during onboarding, so that I receive OSS suggestions that align with what I want to learn and already know.

  2. As a student exploring different CS paths, I want to browse OSS projects in a fun, swipe-based format, so that I can discover opportunities without feeling overwhelmed.

  3. As a first-year or unsure student, I want to see simplified project summaries and course-aligned tags such as “Intro to Python basics” so that I can quickly understand what a project is about and how it connects to my classes.

  4. As a student contributor, I want to view OSS projects with a visible star count and languages, so that I can gauge a project’s popularity and relevance.

  5. As a confident or advanced student, I want recommendations that still challenge me but remain approachable, so that I stay engaged and continue growing as a future dev.

  6. As a student building my resume, I want to find projects with active maintainers and good first issues, so that I can genuinely learn and develop technical skills that stick.

  7. As a student with a rough experience prior, I want indicators that a project is beginner-friendly and welcoming, so that I feel safe trying again.

  8. As a TA or instructor, I want to recommend OSS projects that align with our course material, so that students can apply what they learn in class to real-world code.

  9. As a SWE professional, I want students to easily understand my project’s purpose and contribution pathways, so that contributing feels less “scary.”

  10. As a student contributor, I want to filter out OSS projects that are “too advanced” or unrelated to course materials, so that future suggestions are more tailored to my needs.


## Pages/Screens

- User Account Verification (with option to login/sign-up via Clerk)
  - Sign-Up Page
  - Login Page
- Menu Drop-Down Modal
- Discovery Page
- Selected Repo Modal
- Saved Repos Page
- Profile Page
- Preferences Page
- About Page
- Settings Page
  - Change Password Modal
  - Display Mode Modal (dark/light)
  - Help Documentation Page
  - Privacy Policy Documentation Page

<img width="1656" height="1030" alt="discovery" src="https://github.com/user-attachments/assets/107c625f-045f-4b5a-a35d-fe28afd3e3c7" />

<img width="1622" height="1036" alt="about" src="https://github.com/user-attachments/assets/a821e652-2fa2-4a1d-b06e-e4df35fc70ab" />

<img width="1684" height="1062" alt="saved" src="https://github.com/user-attachments/assets/d4a700ee-4e70-40b1-83d6-973605103f83" />

<img width="1634" height="1028" alt="login" src="https://github.com/user-attachments/assets/e5607ac9-3d5e-4a51-8862-465ef688f575" />


## Data Model
<img width="592" height="841" alt="Screenshot 2025-07-11 at 4 24 42 PM" src="https://github.com/user-attachments/assets/5e12ea47-0b7f-4c31-8ef1-c553ea16c489" />


## API Endpoints

### Repositories

| Method | Endpoint                          | Description |
|--------|-----------------------------------|-------------|
| GET    | `/repo/`                          | Get all repos |
| POST   | `/repo/`                          | Insert new repo (from cron job or admin) |
| PUT    | `/repo/:id`                       | Updates repo metadata |
| GET    | `/repo/:id`                       | Get repo by ID |
| DELETE | `/repo/:id`                       | Delete a specific repo by its ID |
| GET    | `/repo/filter`                    | Get filtered repo list based on filters like skill level, languages, and tags (multiple values separated by `+`) |
| GET    | `/repo/search?query=...`          | _(STRETCH)_ Natural language search |
| POST   | `/repo/explain`                   | _(STRETCH)_ “Explain this repo to me” via LLM |

### Users

| Method | Endpoint                          | Description |
|--------|-----------------------------------|-------------|
| GET    | `/user/:id`                       | _(Admin only)_ Get current user info including skill level, languages, and tags |
| PUT    | `/user/:id`                       | _(Admin only)_ Update user info including skill level, languages, and tags |
| PUT    | `/user/password`                  | Changes password (for users not using Clerk UI) |
| PUT    | `/user/profile`                   | Adjust profile page information |
| GET    | `/user/profile`                   | Displays user profile page |
| GET    | `/user/saved`                     | Get all saved repos from a user |
| DELETE | `/user/saved/:repoId`             | Unsave repo |
| GET    | `/user/:repoId/feedback`          | Get user feedback for a specific repo |
| GET    | `/user/:id/discovery`             | Get recommended repos based on preferences, skill level, and feedback |

### Authentication

| Method | Endpoint                          | Description |
|--------|-----------------------------------|-------------|
| POST   | `/auth/signup`                    | Create new user account |
| POST   | `/auth/login`                     | Authenticate user account |
| POST   | `/auth/createAdmin`               | Create a new admin account |
| POST   | `/auth/clerkSync`                 | Backend sync with Clerk |




[Branch Out Presentation ](https://www.canva.com/design/DAGs4Gy9e4g/67NgXn3OTHpVsUIswDA8Lw/edit?utm_content=DAGs4Gy9e4g&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

[Branch Out Kanban Board](https://trello.com/invite/b/686e9a2699035a8f3fa653af/ATTI71692ab09702fccd659c5952aaab45ba1B339F37/branchout)
