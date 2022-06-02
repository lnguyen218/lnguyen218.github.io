---
title: Ampersand Substitution
date: 2021-09-15 14:13:00 -500
categories: [vim]
tags: [vim,substitution]
---
Ampersand represents entire matched regex value, so wrapping elements in parentheses is simple
`s/\v\w+/(&)/g`

Or adding conditional logic to JS objects. For example:
```javascript
{
  foo: bar
}
```
becomes:
```javascript
{
  ...(bar && { foo: bar })
}
```

Substitute command:
```
s/\v\w+:\s(\w+)/...(\1 \&\& { & })/
```
