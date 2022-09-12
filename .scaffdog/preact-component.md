---
name: 'preact component'
root: '.'
output: '.'
ignore: []
questions:
  name: 'Please enter component name.'
---

# `src/components/{{ inputs.name | pascal }}/index.tsx`

```tsx
import type { FunctionalComponent, JSX } from 'preact'

// import style from './index.module.scss'

type ContainerProps = {
  class?: string
}

type PresenterProps = ReturnType<typeof Container> & {
  children?: JSX.Element[]
}

const Container = (props: ContainerProps) => {
  /** Logic here */

  const presenterProps = {}
  return { ...props, ...presenterProps }
}

const Presenter: FunctionalComponent<PresenterProps> = ({
  class: className,
}: PresenterProps) => <div className={`${className}`}></div>

export default function Preact(props: ContainerProps) {
  return <Presenter {...Container(props)} />
}
```

# `src/components/{{ inputs.name | pascal }}/index.module.scss`

```scss

```