# ACME incident report page

A static, self-contained page (`index.html`, no external scripts or fonts) that looks like an internal incident submission form at a company called ACME. It has no backend: submitting validates the fields in the browser and shows a confirmation with a generated reference number.

## The fields and their ids

| Field | Element | `id` | `name` |
|---|---|---|---|
| Customer name | `<input type="text">` | `incident-customer-name` | `customer_name` |
| Customer email | `<input type="text">` | `incident-customer-email` | `customer_email` |
| Restaurant name | `<input type="text">` | `incident-restaurant-name` | `restaurant_name` |
| Restaurant email | `<input type="text">` | `incident-restaurant-email` | `restaurant_email` |
| Date of the incident | `<input type="text">`, placeholder `MM/DD/YYYY` | `incident-date` | `incident_date` |
| Summary of the incident | `<textarea>` | `incident-summary` | `incident_summary` |
| Steps taken | `<textarea>` | `incident-steps-taken` | `incident_steps_taken` |

Also addressable: the form `#incident-report-form`, the buttons `#incident-submit-button` and `#incident-clear-button`, the banners `#incident-submit-success` and `#incident-submit-error`, and the sections `#incident-section-customer`, `#incident-section-restaurant`, `#incident-section-details`.

Every field is a plain text control, so a selector like `#incident-customer-email` reaches the element directly; the form has `autocomplete="off"`, so the browser's own autofill doesn't interfere with text typed into it. All fields except the restaurant email are required; the two email fields and the date are format-checked on submit.

## Publish it on GitHub Pages

1. Create a repository (public, or private on a plan that allows Pages) and put `index.html` at its root (this folder's contents are the repository's contents).
2. Commit and push to the default branch.
3. In the repository: Settings → Pages → Build and deployment → Source "Deploy from a branch", branch `main`, folder `/ (root)`. Save.
4. The page appears within a minute at `https://<user>.github.io/<repository>/`.

Any later change is a push away. To test locally before pushing, open `index.html` in a browser, or run `python3 -m http.server 8080` in this folder and open `http://localhost:8080/`.
