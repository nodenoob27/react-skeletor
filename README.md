# React Skeletor

![React-skeletor gif](/react-skeletor.gif)

## Skeleton preview for React components

Display a skeleton preview of your application's content before it's loaded

### Basic usage

1. Install via npm

```
npm install react-skeletor
```

or yarn

```
yarn add react-skeletor
```

2. Wrap your component (often a container) with the `createSkeletonProvider` high order component. This adds the pending status and style into the [context](https://facebook.github.io/react/docs/context.html).

```jsx
// UserDetailPage.js

import { createSkeltonProvider } from 'react-skeletor';

const UserDetailPage = ({ user }) => (
  <div>
    ...
    <NameCard user={user} />
    ...
  </div>
)

export default createSkeltonProvider(
  // Dummy data with a similar shape to your component's data
  {
    firstName: '_____',
    lastName: '________'
  },
  // Predicate specifying whether or not your data is loaded
  ({ user }) => user === undefined
)(UserDetailPage);
```

3. Use a skeleton element to magically style your component when data is pending with zero effort!

```jsx
// NameCard.js

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
