## react-router-modal

A simple way to handle showing modals with react-router version 4.

### Installation

Install using yarn or npm.

`npm install react-router-modal --save`
`yarn add react-router-modal`

#### peerDependencies

`react-router-modal` requires:

`react-router-dom` *version 4*
`react` & `react-dom`, version 15

### Components

#### ModalContainer

ModalContainer contains all modals that are shown. Typically you will want to mount this just before your closing `</body>` tag.
Nothing will be rendered into the dom if no modals are current shown.

##### props

* `bodyModalOpenClassName`

Class name to set on the `<body>` when a modal is mounted. Typically used to prevent default scroll behavior, etc.
Defaults to `react-router-modal__modal-open`

* `containerClassName`
Class name for the modal container element. Note that this element is only rendered when at least one modal is shown.

Defaults to `react-router-modal__modal-container`

* `backdropClassName`
Class name for the modal backdrop element(s) that are show behind each modal.
Defaults to `react-router-modal__modal-backdrop`

* `modalClassName`
Class name for the modal element(s) that wrap the modal content. Can be overridden by the `className` property on `<ModalRoute />` or `<Modal />`

Defaults to `react-router-modal__modal`

#### ModalRoute

ModalRoute attaches a component to a route.

##### props

* path

The path to match. See react-router docs.

* component

The component to render inside the modal when the path is matched.

* exact

Only match on exact route match. See react-router docs.

* props

Properties to be passed to the component when the route is matched.
The react-router props `location', 'history', and 'match` will also be included.

* className

If set, overrides the `modalClassName` property on the `ModalContainer`

When the route matches, the component will be shown inside a modal.
If multiple routes match, the modals will be stacked based on the length of the path that is matched.

#### Modal

If you want to show a modal without a route, you can use this. Modals shown this way default to stacking on top of modals shown with ModalRoute.

##### props

* component

The component to render inside the modal when the path is matched.

* props

Properties to be passed to the component rendered inside the modal.

* stackOrder

Controls the order the modals are stacked. Higher number means "on top".

* className

If set, overrides the `modalClassName` property on the `ModalContainer`


### CSS

Default css is included in `css/react-router-modal.css`. You can use this as a basis for your own modal styles.
