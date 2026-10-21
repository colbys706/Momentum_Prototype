# Momentum

This will be the repository we'll use for our team project in IS401.
Less scrolling, more living. A phone-first web app that helps college students in Provo build better phone habits and replace scrolling with real, in-person activities.

Plain **HTML + CSS + JavaScript**. No frameworks, no build step.

```
momentum/
├── README.md               ← you are here
├── database/
│   ├── schema.sql          ← run in Supabase (24 tables, rules, demo data)
│   └── ERD-GUIDE.md        ← Supabase setup + Lucidchart ERD steps
└── site/                   ← the website (upload this folder to host it)
    ├── index.html          ← sign in / sign up
    ├── home.html  streak.html  activities.html  activity.html  activity-new.html
    ├── calendar.html  lessons.html  lesson.html  social.html  friends.html
    ├── profile.html  settings.html
    ├── css/styles.css      ← ALL styling (colors at the top)
    └── js/
        ├── config.js       ← paste Supabase URL + anon key here
        ├── store.js        ← ALL data: habits, streaks, points, RSVPs, posts, messages
        ├── ui.js           ← shared header, nav, messages panel, pop-ups
        ├── lessons-content.js ← lesson text (edit lessons here)
        ├── pages/*.js      ← one file per page
        └── vendor/         ← Supabase's library (don't edit)

App Summary: Young, isolated college students in Provo spend too much time on their phones rather than forming real connections and do not have effective resources to help them develop better habits and find long-term satisfaction. This increased amount of screen time frequently leads them to feeling alone, worsens their mental health, and makes it more difficult to form real-life social support networks during challenging college years. They need to find meaningful ways to spend their free time, especially in the evenings, to avoid doom scrolling. This website should motivate them to have less desire to unintentionally waste time throughout down time each day. They will be able to RSVP to various activities, post your own, communicate with others who are attending events in Provo, learn more about the effects of social media, and create and apply realistic goals or habits.

Tech Stack: We decided to use HTML/CSS/JavaScript for our front end. Our hosting service is GitHub and as our back end database service we're using Supabase. We decided to go this route for several reasons. The main reason is because these languages and services are the ones we're most familiar with so it will make editing easier. Beyond that, we want to avoid having to pay for AI services and it's very easy to use up free tokens quickly, but we did use Claude to help put it all together with the resources we gave it.

How to get it running (starting with a copy of this repo’s code):

Create a Github repo with the code -Take these files, and upload them onto a fresh git hub repo.
Create an ERD -There is a schema file that you can use to create the supabase tables set up. Open a new project on supabase Go to the query tool, and paste in the schema query (found on github → /database/schema). Run the query. -If you want to view the ERD on Lucid chart, do the following. Open a lucid document Select file → import → ERD → PostgreSQL Copy the presented query, and run it in a new query back on the supabase project. Copy the result as a CSV. Return to Lucid chart. Click next, paste all. Run it, and now you have a field of imported tables. Place all the loaded tables onto the document, and relationships will form automatically.
In the Github repo, you need to connect your supabase. -Open the config.js on Github’ -Go to the supabase project overview → copy, towards the top. -Copy ‘Project URL’ → paste it into the congif.js supabase url. -Copy ‘Publishable key’ → paste it into the config.js supabase anon key -Save those changes
Publish your repo on Github as a page, and voilà!
Verifying the vertical slice:

Open the live site link and enter any email and any text as a password. The log in step is not live right now.
From the home page, click the “Post an Activity” button
Fill in the required information including “Title,” “Activity Type,” “Date,” start and end time and address.
Select “Public” under activity visibility
Verify the information, then click “Post activity”. Doing this will log the activity in the Supabase “activities” table (request to backend, which grabs data and responds back into frontend).
Open the link in a private web browser such as Chrome Incognito and log in. Again, the email and password are meaningless. Do not try to create a real account or use a real username or password.
Click on “Activities” and the activity you created should appear on the list! This occurs because the website pulls all the activities from the activities table in Supabase and displays them on screen.
