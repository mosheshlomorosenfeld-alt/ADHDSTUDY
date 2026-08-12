# Focus Calendar

ADHD-friendly calendar organizer with quick-add events, recurring events, day/week views, Apple Calendar/Outlook `.ics` export, Google Calendar event links, PWA installation, offline caching, browser notification permission, and a secure email-reminder API.

## Calendar support

- **Apple Calendar / Outlook / other calendar apps:** use `Apple / Outlook .ics`. Import the file into the calendar app; the reminder is included as a VALARM.
- **Google Calendar:** use `Add to Google Calendar` for a pre-filled event, or import the `.ics` file.
- **Recurring events:** daily, weekdays, weekly, monthly.

## Email reminders

The browser must not contain an email API key. The included `api/reminder.js` is designed for Vercel/serverless deployment.

Set these environment variables in the deployment:

- `RESEND_API_KEY` — your Resend API key
- `REMINDER_FROM` — a verified sender, for example `Focus Calendar <reminders@yourdomain.com>`

The endpoint accepts `{ email, event }` and sends one reminder. For fully automatic scheduled reminders, connect the saved events to a database and invoke this endpoint from a scheduled worker/cron job. Do not put the Resend API key in `app.js`.

## Deploy

The `calendar-organizer` folder can be deployed as a static site. For email API routes, deploy the repository/project with Vercel (or move the API route to another serverless provider) and configure the environment variables above.
