# @shipmyform/svelte

Svelte bindings for [ShipMyForm](https://shipmyform.com).

```sh
npm i @shipmyform/svelte
```

## Store

```svelte
<script lang="ts">
  import { createSubmit } from '@shipmyform/svelte'
  const { submit, submitting, succeeded, error } = createSubmit({ formId: 'YOUR_FORM_ID' })
</script>

{#if $succeeded}
  <p>Thanks!</p>
{:else}
  <form on:submit|preventDefault={(e) => submit(e.currentTarget)}>
    <input name="email" type="email" required />
    <button disabled={$submitting}>Send</button>
    {#if $error}<p role="alert">{$error.message}</p>{/if}
  </form>
{/if}
```

## Action

Progressive enhancement — the form still posts natively without JavaScript.

```svelte
<script lang="ts">
  import { shipmyform } from '@shipmyform/svelte'
</script>

<form use:shipmyform={{ formId: 'YOUR_FORM_ID', onSuccess: () => alert('Thanks!') }}>
  <input name="email" type="email" required />
  <button>Send</button>
</form>
```

## Get a form endpoint

Point the client at a ShipMyForm form and submissions are stored, spam-filtered,
and routed to email, Slack, Google Sheets and 20+ other tools — no server.

The free plan covers 100 submissions a month with the full spam pipeline, and
needs no credit card. [Create a form](https://shipmyform.com/login) ·
[Docs](https://shipmyform.com/docs/sveltekit) · [shipmyform.com](https://shipmyform.com)
