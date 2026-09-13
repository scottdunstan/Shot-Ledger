# Shot Ledger

A single-file golf shot quality tracker for GitHub Pages. Grade every shot
(Great → Terrible), tag the cause (contact, course management, direction,
flight), and see where your game leaks strokes.

## Repo layout

```
index.html            the whole app
data/database.json    your database — courses and rounds, committed to Git
```

## Deploy

1. Create a repository (e.g. `shot-ledger`) and upload both `index.html`
   and the `data` folder, keeping the structure above.
2. Repository **Settings → Pages → Source: Deploy from a branch**, pick
   `main` and `/ (root)`, save.
3. Your app is live at `https://<username>.github.io/shot-ledger/`.
   Open it on your phone and use the browser's **Add to Home Screen** for
   one-tap access after a round.

## How the database works

- On load, the app reads `data/database.json` from the repo and merges it
  with anything stored on the device, so every device sees every committed
  round.
- New rounds you enter are saved on the device immediately. The green bar
  under the title tells you how many changes haven't been committed yet.
- To commit them: tap **Download database**, then replace
  `data/database.json` in the repo with the downloaded file (GitHub web:
  open the file → pencil/upload → commit; or use the GitHub mobile app).
  Once Pages redeploys (a minute or so), the bar shows "In sync".
- Deleting a round in the app keeps a note of the deletion on that device
  so the repo copy doesn't reappear; commit the database to make the
  deletion permanent everywhere.

`database.json` is plain JSON — readable, diffable, and easy to back up.

## Notes

- Entry drafts auto-save as you type, so you can grade holes at the bar
  and finish later.
- Par, stroke index, course rating and slope live per tee set under the
  **Courses** tab; add a course once and it's in the dropdown forever.
- Stoke by Nayland (Gainsborough, White tees — par 71, rating 70.8,
  slope 133) is preloaded from the club's published scorecard.
