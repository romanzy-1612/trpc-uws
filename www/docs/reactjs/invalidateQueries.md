---
id: invalidateQueries
title: invalidateQueries
sidebar_label: invalidateQueries()
slug: /invalidateQueries
---


A typesafe wrapper around calling `queryClient.invalidateQueries()`, all it does is to call `queryClient.invalidateQueries()` with the passed args. [See react-query docs](https://react-query.tanstack.com/guides/query-invalidation) if you want more fine-grained control.



## Example code

```tsx
import { trpc } from '../utils/trpc'


// In component:
const utils = trpc.useContext();

const mutation = trpc.proxy.post.edit.useMutation({
  onSuccess(input) {
    utils.invalidateQueries(['post.all']);
    utils.invalidateQueries(['post.byId', input.id]);
  },
})
```
