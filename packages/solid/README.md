# @shipmyform/solid

Solid primitive for [ShipMyForm](https://shipmyform.com).

```sh
npm i @shipmyform/solid
```

```tsx
import { createSubmit } from '@shipmyform/solid'

export function Contact() {
  const { submit, submitting, succeeded, error } = createSubmit({ formId: 'YOUR_FORM_ID' })

  return (
    <Show when={!succeeded()} fallback={<p>Thanks!</p>}>
      <form
        onSubmit={(e) => {
          e.preventDefault()
          submit(e.currentTarget)
        }}
      >
        <input name="email" type="email" required />
        <button disabled={submitting()}>Send</button>
        <Show when={error()}>{(e) => <p role="alert">{e().message}</p>}</Show>
      </form>
    </Show>
  )
}
```

See [`@shipmyform/core`](https://www.npmjs.com/package/@shipmyform/core) for options and result types.

## Get a form endpoint

Point the client at a ShipMyForm form and submissions are stored, spam-filtered,
and routed to email, Slack, Google Sheets and 20+ other tools — no server.

The free plan covers 100 submissions a month with the full spam pipeline, and
needs no credit card. [Create a form](https://shipmyform.com/login) ·
[Docs](https://shipmyform.com/docs/sdk) · [shipmyform.com](https://shipmyform.com)
