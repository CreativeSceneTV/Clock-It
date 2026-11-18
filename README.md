# Clock-It

A simple, private work-hours tracker that runs entirely in your browser. Start your day, switch tasks, take timed breaks, and produce a clean PDF time slip for any day or any date range, with full totals.

There is no server, no account and no build step. The whole app is one file: `index.html`.

## Features

- **Day timer.** Give the day an optional title and description and type the time you started (e.g. `08:01:00`). The clock counts from that time. Pressing **Stop day** captures the current time automatically, so the day shows as a range such as `08:01:00 - 17:23:00`.
- **Task switching.** Press **Switch task** to close the current task and open a new one at the current time. Task names are optional (unnamed tasks become "General", "Task 2", "Task 3" and so on). Task durations add up to the day total with no overlap.
- **Timed breaks.** Set a lunch length and two tea-time lengths when you start the day. Each has its own countdown with Start and Stop, so you can pause and resume it whenever you like. Going over the allowance shows as time over. An **Other break** lets you type what you are doing (bathroom, PC down, PC maintenance).
- **Break time is excluded.** Time on a break is left out of the day total and the task totals, and each break is listed on the slip.
- **Exact to the second.** All times and durations show as `HH:MM:SS`.
- **Daily slip.** Every day gets a slip with your name, company, date, title, description, day range, breaks, total worked, a task table, a signature line and a generated-at timestamp.
- **Period slip.** Choose a start date and an end date (or press **This month** / **Last month**) to get one slip covering every finished day in that range, with the full period total, total breaks and hours by task.
- **PDF and print.** Download any slip as a PDF, or print it.
- **Editable after stopping.** Fix the day start and end, task names and times, and break times, or remove a break.
- **Light and dark mode.** A white-and-blue theme with a dark mode toggle. It follows your device setting until you pick one.

## Privacy and data

- Everything is stored in your browser's `localStorage`. Nothing is uploaded or sent anywhere, and nobody else can see your days.
- Each person who opens the site has their own private copy, per browser and per device.
- Days are saved automatically under the browser's date.
- Days older than 3 months are removed automatically whenever the page opens.
- Clearing your browser data also erases saved days. Download the PDF slips you want to keep.

## Using it

1. Open the site and fill in your name, company and the time you started. Title, description and first task are optional.
2. Press **Start day**. Use **Switch task** and the break buttons as you go.
3. Press **Stop day** when you finish. Download or print the slip.
4. Use the date dropdown to look at any saved day, or **Period slip** for a range of days.

## Run locally

Open `index.html` in a browser. That is all.

The PDF library (jsPDF) loads from a CDN, so you need an internet connection for **Download PDF slip**. Printing works without it.

## Deploy

### Netlify

- Drag this folder onto https://app.netlify.com/drop, or
- Connect the GitHub repository in Netlify. Leave the build command empty and set the publish directory to `.` (`netlify.toml` already does this).

### GitHub Pages

1. Push the files to a GitHub repository.
2. Go to **Settings > Pages**.
3. Choose **Deploy from a branch**, pick `main` and `/ (root)`, then save.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (HTML, CSS and JavaScript) |
| `netlify.toml` | Tells Netlify there is no build step |
| `LICENSE` | MIT license |
| `.gitignore` | Files git should ignore |
| `README.md` | This file |

## Limitations

- Data lives in one browser on one device. It does not sync between devices.
- One day is recorded per calendar date, and a day cannot run past midnight.
- Days older than 3 months are deleted. To change this, edit the `purge()` function in `index.html`.
- A day that is still running is not counted in period slips until you stop it.

## Built with

- Plain HTML, CSS and JavaScript, no framework and no build tools
- [jsPDF](https://github.com/parallax/jsPDF) 2.5.1 (MIT) for PDF slips, loaded from cdnjs

## License

Released under the [MIT License](LICENSE).
