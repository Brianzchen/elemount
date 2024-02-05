# elemount

As much as we'd like to run a single frontend framework for our applications many company's do not have such a luxury. They come with deadlines over many years which usually results in technical debt.

But everyone wants to be coding in the latest and greatest be it React, Vue, or Svelte.

`elemount` is a library that takes the pressure off compability between the two frameworks and lets you focus on each separately.

All you need to do is provide the library an identifier to find the element and a function to mount your secondary framework.

```js
import { render } from 'react-dom';
import { mount } from 'elemount';

mount(
  () => document.getElementById('my-component'),
  (element: HTMLElement) => {
    const mounted = render(
      <div>hello world</div>,
      element,
    );

    return mounted.unmount;
  },
);
```

Unmounting occurs when ...
