---
title: Copy String to Clipboard
date: 2021-07-06 10:08:00 -500
categories: [javascript]
tags: [javascript]
---
Function to put string argument onto one's clipboard
```javascript
const copyStringToClipboard = (str) => {
  // Create new element
  const el = document.createElement('textarea')
  // Set value (string to be copied)
  el.value = str
  // Set non-editable to avoid focus and move outside of view
  el.setAttribute('readonly', '')
  el.style = { position: 'absolute', left: '-9999px' }
  document.body.appendChild(el)
  // Select text inside element
  el.select()
  // Copy text to clipboard
  document.execCommand('copy')
}
```
