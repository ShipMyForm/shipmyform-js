# @shipmyform/react

React hook for [ShipMyForm](https://shipmyform.com).

```sh
npm i @shipmyform/react
```

```tsx
import { useSubmit } from '@shipmyform/react'

export function Contact() {
  const { submit, submitting, succeeded, error } = useSubmit({ formId: 'YOUR_FORM_ID' })

  if (succeeded) return <p>Thanks!</p>

  return (
    <form
      onSubmit={(e) => {
        e.preventDefault()
        submit(e.currentTarget)
      }}
    >
      <input name="email" type="email" required />
      <textarea name="message" required />
      <button disabled={submitting}>Send</button>
      {error && <p role="alert">{error.message}</p>}
    </form>
  )
}
```

`submit` accepts an object, `FormData`, or the form element, plus optional `{ turnstileToken, subject, redirect, signal }`. See [`@shipmyform/core`](https://www.npmjs.com/package/@shipmyform/core) for details.

## Get a form endpoint

Point the client at a ShipMyForm form and submissions are stored, spam-filtered,
and routed to email, Slack, Google Sheets and 20+ other tools — no server.

The free plan covers 100 submissions a month with the full spam pipeline, and
needs no credit card. [Create a form](https://shipmyform.com/login) ·
[Docs](https://shipmyform.com/docs/react) · [shipmyform.com](https://shipmyform.com)
