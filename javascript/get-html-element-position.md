# Get HTML element's position

learned this way when I fixed crawler project's bug, though I didn't use it eventually XD.

we can use `getClientRects()` to get the position of the element

- just take GitHub left side button `Edit profile` for example:

```js
document.querySelector(".js-profile-editable-edit-button").getClientRects();
```
