# @shipmyform/vue

Vue 3 composable for [ShipMyForm](https://shipmyform.com).

```sh
npm i @shipmyform/vue
```

```vue
<script setup lang="ts">
import { useSubmit } from '@shipmyform/vue'

const { submit, submitting, succeeded, error } = useSubmit({ formId: 'YOUR_FORM_ID' })
</script>

<template>
  <p v-if="succeeded">Thanks!</p>
  <form v-else @submit.prevent="submit($event.target as HTMLFormElement)">
    <input name="email" type="email" required />
    <textarea name="message" required />
    <button :disabled="submitting">Send</button>
    <p v-if="error" role="alert">{{ error.message }}</p>
  </form>
</template>
```

See [`@shipmyform/core`](https://www.npmjs.com/package/@shipmyform/core) for options and result types.

## Get a form endpoint

Point the client at a ShipMyForm form and submissions are stored, spam-filtered,
and routed to email, Slack, Google Sheets and 20+ other tools — no server.

The free plan covers 100 submissions a month with the full spam pipeline, and
needs no credit card. [Create a form](https://shipmyform.com/login) ·
[Docs](https://shipmyform.com/docs/vue) · [shipmyform.com](https://shipmyform.com)
