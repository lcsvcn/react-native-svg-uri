# react-native-svg-uri
Render SVG images in React Native from an URL or a static file

This was tested with RN 60.5 and react-native-svg 9.7.0 (depends on this library)
[react-native-svg](https://github.com/react-native-community/react-native-svg)

This was forked from https://github.com/vault-development/react-native-svg-uri

Not all the svgs can be rendered, if you find problems fill an issue or a PR in
order to contemplate all the cases

Install library from `npm`

```bash
npm install --save lcsvcn/react-native-svg-uri#master
```
<b>From React-Native 0.60.0</b>

Unlink library react-native-svg
```bash
react-native unlink react-native-svg # not react-native-svg-uri !!!
```

<b>Below React-Native 0.60.0</b>

Link library react-native-svg

```bash
react-native link react-native-svg # not react-native-svg-uri !!!
```

## Props

| Prop | Type | Default | Note |
|---|---|---|---|
| `source` | `ImageSource` |  | Same kind of `source` prop that `<Image />` component has
| `svgXmlData` | `String` |  | You can pass the SVG as String directly
| `fill` | `Color` |  | Overrides all fill attributes of the svg file
| `fillAll` | `Boolean` |  Adds the fill color to the entire svg object

## Known Bugs

- [ANDROID] There is a problem with static SVG file on Android,
  Works OK in debug mode but fails to load the file in release mode.
  At the moment the only workaround is to pass the svg content in the svgXmlData prop.
- [ANDROID] There is a problem with URI SVG file on Android,
  Blinking the SVG if need to move image.

## <a name="Usage">Usage</a>

Here's a simple example:

```javascript
import SvgUri from 'react-native-svg-uri';

const TestSvgUri = () => (
  <View style={styles.container}>
    <SvgUri
      width="200"
      height="200"
      source={{uri:'http://thenewcode.com/assets/images/thumbnails/homer-simpson.svg'}}
    />
  </View>
);
```

or a static file

```javascript
<SvgUri width="200" height="200" source={require('./img/homer.svg')} />
```

This will render:

![Component example](./screenshoots/sample.png)

## Testing
1. Make sure you have installed dependencies with `npm i`
2. Run tests with `npm test`
