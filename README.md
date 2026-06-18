# Plant Forecast Viewer — Interview Task

## The task

You're building a small internal tool for a grid operations analyst. We track
three renewable power plants. When the analyst picks one and clicks
"Load Forecast," the page should show the next 24 hours of weather data for
that plant in a table.

## Req: user can click one of three plants (list of plants) and the 'Load forecast' button shows 24 hours of weather data for THAT plant in a TABLE.

## Plants: 1. Austin TX, 2. NYC, 3. Los Angeles

# need a list of plants (dropdown)

# need a button to load forcast

# need a output table of plant chosen

The scaffold (`index.html`) contains a comment block with the plant info and the
Open Meteo API endpoint. Use plain HTML, CSS, and JavaScript — no framework.
Tailwind via CDN is fine if you want styling help, but it's not required.

## The AI rule

**You get ONE — and only ONE — prompt to an AI assistant.** Whatever code it
produces, you take from there. After that initial prompt:

- No follow-ups to the AI
- No "fix this for me"
- No "rewrite this function"
- You can use the browser console, network tab, MDN, and the Open Meteo docs
  freely

Use whichever AI you're comfortable with (Claude, ChatGPT, Copilot, etc.).

## Suggested timing (~25 minutes coding)

- **~3 min** — write your prompt (you can revise it before you send)
- **~2 min** — let the AI respond, paste the result into `index.html`
- **~20 min** — read what the AI gave you and improve it manually

We'll then spend about 25 minutes discussing what you changed and why.

## Git workflow — important

This folder is a git repository. As you work, **commit each meaningful change
as a separate commit**, with a short message explaining _why_ you made the
change (the "what" is already in the diff).

**Step 1.** After you paste the AI output, commit it EXACTLY as the AI returned
it — before fixing anything:

```
git add .
git commit -m "AI baseline, unedited"
```

**Step 2.** Then, for each improvement you make, commit it separately:

```
git add .
git commit -m "Replace innerHTML with textContent — prevent XSS"
```

Good commit messages explain _why_:

- `"Replace innerHTML with textContent — prevent XSS"`
- `"Connect label to select via for/id for screen readers"`
- `"Extract rowsFromForecast as a pure function for testability"`
- `"Disable button while request is in flight"`
- `"Check res.ok so non-2xx responses surface as errors"`

Avoid generic messages like `"updates"`, `"fix"`, or `"more stuff"`.

## How to run the page

Double-click `index.html` and it opens in your browser. Open Meteo allows
cross-origin requests from any origin so `fetch()` works directly from
`file://`.

If `file://` misbehaves, run a local server from this folder:

```
python -m http.server 8000
```

Then open <http://localhost:8000>.

## What "done" looks like

A working app where:

- A dropdown lists the three plants
- A button fetches and displays the 24-hour forecast in a table
- A loading state is visible while the request is in flight
- Network errors are visible to the user (not just in the console)

Anything beyond that is bonus and grist for discussion.

## Stretch goals (if you have time)

- Show only the relevant field per plant type
  (wind speed for the wind farm, solar radiation for solar)
- Format timestamps as human-readable local time
- Add an empty state when the page first loads
- Anything else you'd want in a small internal tool
