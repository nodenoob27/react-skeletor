# React-pendifier

![React-pendifier gif](/react-pendifier.gif)

## Skeleton loading for your UI in React.
Immediately show to your user where the content gonna be displayed by first rendering animated grey blocks.

### How it works

First you need the `dummify` high order component which gonna inject some dummy data to your component and set what condition define your loading state accross your components.

Secondly you need either `toglify` or `pendify` to catch the loading state and style your component accordingly.

### How to start

```jsx
import { dummify } from 'react-pendifier';

dummify(
  {
    // Some dummy data, should have the same shape as the data you receive into your component
  },
  // Predicate that specify what make your UI loading
  ({ someProp }) => someProp === something
)(SomeComponent);
```

Later in your lower DOM tree:

```jsx

import { toglify } from 'react-pendifier';

const Title = ({ text, style }) => <h1 style={style}>{ text }</h1>

const SkeletonTitle = toglify(Title);

() => <SkeletonTitle style={titleStyle} text="Some title here"/>
```

## TODO

* Add aria tags
* Add remaining HTML tags
* Add tests
* Add css class based example
* Add documentation
