A React hook to access data from the [Gravity Sensor API](https://developer.mozilla.org/en-US/docs/Web/API/GravitySensor).

## Installation

Using `npm`:

```sh
npm install --save react-hook-gravity
```

Using `yarn`:

```sh
yarn add react-hook-gravity
```

## Usage

```jsx
import React from 'react'
import useGravitySensor from 'react-hook-gravity'

const ComponentWithAccelerometer = () => {
  const sensor = useGravitySensor()

  return !sensor.error ? (
    <ul>
      <li>X: {sensor.x}</li>
      <li>Y: {sensor.y}</li>
      <li>Z: {sensor.z}</li>
    </ul>
  ) : (
    <p>No gravity, sorry.</p>
  )
}
```

### Using `SensorOptions`

If you want to use this feature, simply provide `useGravitySensor` with a `SensorOptions` object:

```jsx
const sensor = useGravitySensor({
  frequency: 60, // cycles per second
})
```

## Notes

Access to data from the Gravity Light API needs user permission.

## Caveats

Gravity Light API is available only in secure contexts (only using HTTPS).

## Credits

Credit to [Bence A. Tóth](https://github.com/bence-toth) for his original hook code for [Geolocation](https://www.npmjs.com/package/react-hook-geolocation).

## License

LGPL-3.0
