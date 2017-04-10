# React-skeletor

![React-skeletor gif](/react-skeletor.gif)

## Skeleton loading for your UI in React.
Immediately show to your user where the content gonna be displayed by first rendering animated grey blocks.

### Basic usage

1. Wrap your component with the `createSkeletonProvider` high order component. This adds the pending status and style into the context.

```jsx
import { createSkeltonProvider } from 'react-skeletor';

const UserDetailPage = ({ user }) => (
  <div>
    ...
    <NameCard user={user} />
    ...
  </div>
)

export default createSkeltonProvider(
  {
    // Some dummy data with a similar shape to
    firstName: 'Darth',
    lastName: 'Vader'
  },
  // Predicate that specify what make your UI loading
  ({ user }) => user === undefined
)(UserDetailPage);
```

2. Use a skeleton element to magically style your component when data is pending with zero effort!

```jsx

import { elements as sk } from 'react-skeletor';

const NameCard = ({ firstName, lastName }) => (
  <div>
    <sk.h1 style={style}>{ firstName }</sk.h1>
    <sk.h2 style={style}>{ lastName }</sk.h2>
  </div>
)

export default NameCard;

```

## TODO

* Add aria tags
* Add remaining HTML tags
* Add tests
* Add css class based example
* Add documentation
