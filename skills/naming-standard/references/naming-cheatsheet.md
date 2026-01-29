# Naming cheatsheet (reference)

This file captures the essential guidance from the original naming cheatsheet.

## English language

Use English language when naming variables and functions.

```js
/* Bad */
const primerNombre = 'Gustavo'
const amigos = ['Kate', 'John']

/* Good */
const firstName = 'Gustavo'
const friends = ['Kate', 'John']
```

## Naming convention

Pick one naming convention and follow it consistently.

```js
/* Bad */
const page_count = 5
const shouldUpdate = true

/* Good */
const pageCount = 5
const shouldUpdate = true
```

## S-I-D

A name must be short, intuitive, and descriptive.

```js
/* Bad */
const a = 5
const isPaginatable = a > 10
const shouldPaginatize = a > 10

/* Good */
const postCount = 5
const hasPagination = postCount > 10
const shouldPaginate = postCount > 10
```

## Avoid contractions

Do not use contractions.

```js
/* Bad */
const onItmClk = () => {}

/* Good */
const onItemClick = () => {}
```

## Avoid context duplication

Avoid duplicating the context in which a name is defined.

```js
class MenuItem {
  handleMenuItemClick = (event) => { /* ... */ }
  handleClick = (event) => { /* ... */ }
}
```

## Reflect the expected result

Let the name reflect the expected result in usage.

```jsx
/* Bad */
const isEnabled = itemCount > 3
return <Button disabled={!isEnabled} />

/* Good */
const isDisabled = itemCount <= 3
return <Button disabled={isDisabled} />
```

## Naming functions: A/HC/LC

Pattern:

prefix? + action (A) + high context (HC) + low context? (LC)

Examples:

| Name                   | Prefix   | Action | High context | Low context |
| ---------------------- | -------- | ------ | ------------ | ----------- |
| `getUser`              |          | get    | User         |             |
| `getUserMessages`      |          | get    | User         | Messages    |
| `handleClickOutside`   |          | handle | Click        | Outside     |
| `shouldDisplayMessage` | should   | Display| Message      |             |

Note: context order changes meaning (high context emphasizes meaning).

## Actions (common verbs)

### get

Accesses data immediately (including async retrieval).

### set

Sets a value in a declarative way (A → B).

### reset

Sets a value back to its initial value or state.

### remove

Removes something from somewhere (paired with add).

### delete

Erases something completely (paired with create).

### compose

Creates new data from existing data.

### handle

Handles an action; often used for callbacks.

## Prefixes

### is

Characteristic or state (boolean).

### has

Possession/existence (boolean).

### should

Positive conditional statement + action (boolean).

### min/max

Boundaries/limits.

### prev/next

Previous/next state (state transition).

## Singular and plurals

Use singular for a single value, plural for multiple values.

```js
/* Bad */
const friends = 'Bob'
const friend = ['Bob', 'Tony', 'Tanya']

/* Good */
const friend = 'Bob'
const friends = ['Bob', 'Tony', 'Tanya']
```

