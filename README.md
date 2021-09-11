<div align="center">
  <h1>Active Campaign React</h1>
  <p>Library that helps integrating Active Campaign Forms with React, based on the article - <a href="https://dev.to/saragibby/better-way-to-embed-active-campaign-forms-into-react-n9n">Better Way To Embed Active Campaign Forms Into React</a> by <a href="https://saragibby.com/">Sara Gibbons</a></p>
  <br />
</div>

<div align="center">
  <a href="https://www.npmjs.com/package/active-campaign-react"><img alt="npm version badge" src="https://img.shields.io/npm/v/active-campaign-react"></a>  
  <img alt="npm bundle size" src="https://img.shields.io/bundlephobia/min/active-campaign-react">
  <img alt="license badge" src="https://img.shields.io/npm/l/active-campaign-react">
</div>

<br />

## Installation

```
$ npm i --save active-campaign-react

# or

$ yarn add active-campaign-react
```

## Example usage with react-hook-form

```tsx
import { ActiveCampaignInputs, handleActiveCampaignSubmit } from 'active-campaign-react'
import { useForm } from 'react-hook-form'

export default function ContactForm() {
  const { register, handleSubmit } = useForm()
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
