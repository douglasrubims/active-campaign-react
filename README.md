# Active Campaign React

Library that helps integrating Active Campaign Forms with React, based on the article - [Better Way To Embed Active Campaign Forms Into React](https://dev.to/saragibby/better-way-to-embed-active-campaign-forms-into-react-n9n) by [Sara Gibbons](https://saragibby.com/)

## Installation

```
$ npm i --save active-campaign-react

# or

$ yarn add active-campaign-react
```

## Example usage with react-hook-form

```tsx
import { ActiveCampaignInputs, handleActiveCampaignSubmit } from 'active-campaign-react'
import { Controller, useForm } from 'react-hook-form'

export default function ContactForm() {
  const { register, handleSubmit, formState, control } = useForm()
  const formId = 'yourFormId'

  const onSubmit = async (data) => {
    handleActiveCampaignSubmit(data, 'yourComapnySubdomain', formId)
  }

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <ActiveCampaignInputs formId={formId} />

      <input name="name" id="name" {...register('name', { required: true })} />
      <input name="email" type="email" id="email" {...register('email', { required: true })} />

      <button type="submit">Submit</button>
    </form>
  )
}
```
