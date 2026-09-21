# @shipmyform/astro

Astro component for [ShipMyForm](https://shipmyform.com). Renders a native form that posts without JavaScript and upgrades to `fetch` on the client.

```sh
npm i @shipmyform/astro
```

```astro
---
import ShipMyForm from '@shipmyform/astro/ShipMyForm.astro'
---

<ShipMyForm formId="YOUR_FORM_ID">
  <input name="email" type="email" required />
  <textarea name="message" required />
  <button>Send</button>
</ShipMyForm>

<script>
  document.addEventListener('shipmyform:success', () => alert('Thanks!'))
  document.addEventListener('shipmyform:error', (e) => console.error(e.detail))
</script>
```

Props: `formId` (required), `endpoint`, `class`.

## Get a form endpoint

Point the client at a ShipMyForm form and submissions are stored, spam-filtered,
and routed to email, Slack, Google Sheets and 20+ other tools — no server.

The free plan covers 100 submissions a month with the full spam pipeline, and
needs no credit card. [Create a form](https://shipmyform.com/login) ·
[Docs](https://shipmyform.com/docs/astro) · [shipmyform.com](https://shipmyform.com)
