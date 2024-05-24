## Installation

- npm

```
npm intall react-iframe-wrapper
```

- yarn

```
yarn add react-iframe-wrapper
```

## Usage

Just simply wrap the components you need using Iframe component

```
import { Iframe } from 'react-iframe-wrapper';

const MyComponent = () => {
  return (
    <div>Hello world</div>
  )
}

const App = () => {
  const nodeRef = useRef()

  const head = (
    <>
      <link rel="stylesheet" href="/styles.css" />
      <title>Home</title>
    </>
  )

  return (
    <div className="App">
      <Iframe
        head={head}
        title={'Iframe Title'}
        className={''}
        onMount={() => {}}
        onUpdate={() => {}}
        ref={nodeRef}
      >
        <MyComponent>
      </Iframe>
    </div>
  )
}
```

To access Iframe window or document

```
import { useFrame } from 'react-iframe-wrapper';

const MyComponent = () => {
  const { document: frameDocument, window: frameWindow } = useFrame();
  console.log(frameDocument, frameWindow)

  return (
    <div></div>
  )
}
```

## Documentation

### Props
This component supports all default props of the iframe extends with these below props

| Prop name      | Description                          | Required | Type        | Default                                                  |
| -------------- | ------------------------------------ | -------- | ----------- | -------------------------------------------------------- |
| head           | Components that stay in the head tag | false    | ReactNode   | null                                                     |
| mountTarget    | where the content should stay in     | false    | HTMLElement |                                                          |
| initialContent | default srcDoc                       | true     | string      | `<!DOCTYPE html><html><head></head><body></body></html>` |
| onMount        |                                      | false    |             | () => {}                                                 |
| onUpdate       |                                      | false    |             | () => {}                                                 |

## License

MIT
