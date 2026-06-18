# life dashboard + week calendar

two linked PWAs for summer 2026 organization — deployable as home screen apps on iOS/Android.

## files

| file | purpose |
|------|---------|
| `life-dashboard.html` | main hub: home calendar, school tab, finances, loan rehab, apartment tracker |
| `calendar-widget.html` | weekly schedule view with per-day checklists |

## installing to home screen (iOS)

1. open the file in Safari (must be Safari for PWA install)
2. tap the **share** icon → **add to home screen**
3. repeat for both files
4. both apps share `localStorage` if opened from the same origin — keep them in the same folder on a local server or deploy together

## deploying locally

any static file server works:

```bash
# python
python3 -m http.server 8080

# node
npx serve .
```

then open `http://localhost:8080/life-dashboard.html` in Safari and install.

## school tab

assignments are hardcoded in the `courses` object in `life-dashboard.html` (search for `// School course data`). update each term by editing the `weeks` arrays per course:

```js
{ name: 'Assignment name', due: 'YYYY-MM-DD', points: 100, type: 'discussion' }
// type options: discussion | quiz | essay | exam | assignment
```

## colors

| course | color |
|--------|-------|
| contract law | `#ff4fa3` |
| critical thinking | `#a06cff` |
| real estate | `#27cdbb` |

## fonts

- display/headers: [Jost](https://fonts.google.com/specimen/Jost) (400–600)
- body: [Outfit](https://fonts.google.com/specimen/Outfit) (300–500)
