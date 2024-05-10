# Expo Speech Bug on web 

On web, the `onDone` event does not fire in expo-speech `12.0.2`, but fires correctly in `11.7.0`. Tested in Chrome Version 124.0.6367.156 (Official Build) (arm64):

```
   import * as Speech from "expo-speech";

   //...//

   const thingToSay = "This is a test of the onDone event.";

   const options = {
      onDone: () => {
        console.log("End of speech");
      },
   };

   Speech.speak(thingToSay, options);
```

In `11.7.0` the `onDone` event fires the function above, but not in `12.0.2`.

## Reproduce

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
    npx expo start
   ```
3. Open on web, tap button to play sound, inspect console log.
