---
title: Typescript Jest Mocks
date: 2021-12-17 09:53:00 -500
categories: [jest]
tags: [typescript,testing]
---
Using `mocked` to mock out modules:

```typescript
import { mocked } from "ts-jest/utils"
import { useContext } from "preact/hooks"
import { when } from "jest-when"

jest.mock("preact/hooks")

when(mocked(useContext)).calledWith(value).mockImplementation(() => ([{ "HTTP_COOKIE({'cookieKey'})]": "cookie_value"}]))
```

Using `mock` an overloaded functions from class instance:
```typescript
import { MockProxy, mock } from "jest-mock-extended"
import { Clazz } from "dependency"

type ClazzFunc = (args: types) => ReturnType

describe("file", () => {
  let mockClazz: MockProxy<Clazz>

  beforeEach(() => {
    mockClazz = mock<Clazz>()
  })

  it("test", () => {
      ;(mockClazz.func as ClazzFunc) = jest.fn((args: type) => {
        expect(args).toBe(something)
        return returnData as ReturnType
    })
  })
})
```
