# Expo Speech Bug on web 

Get a Speech.speak() error in Expo 51 when running a simple speak on web:

```
   import * as Speech from "expo-speech";

   //...//

   const thingToSay = "1";
   Speech.speak(thingToSay);
```

This error is present in `expo-speech@12.0.1`, but not in `expo-speech@11.7.0`

The error:

```
entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:114830 Uncaught TypeError: _ExponentSpeech.default.listenerCount is not a function
    at setSpeakingListener (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:114830:51)
    at _registerListenersIfNeeded (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:114715:5)
    at Object.speak (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:114778:5)
    at speak (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:114636:14)
    at onClick (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:52793:15)
    at HTMLUnknownElement.callCallback (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:14462:20)
    at Object.invokeGuardedCallbackDev (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:14506:22)
    at invokeGuardedCallback (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:14563:37)
    at invokeGuardedCallbackAndCatchFirstError (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:14577:31)
    at executeDispatch (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18720:9)
    at processDispatchQueueItemsInOrder (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18746:13)
    at processDispatchQueue (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18757:11)
    at dispatchEventsForPlugins (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18766:9)
    at entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18926:18
    at batchedUpdates$1 (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:33315:18)
    at batchedUpdates (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:14310:18)
    at dispatchEventForPluginEventSystem (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:18925:9)
    at dispatchEventWithEnableCapturePhaseSelectiveHydrationWithoutDiscreteEventReplay (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:16432:11)
    at dispatchEvent (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:16426:11)
    at dispatchDiscreteEvent (entry.bundle?platform=web&dev=true&hot=false&lazy=true&transform.routerRoot=app&resolver.environment=client&transform.environment=client:16403:11)
```

## Reproduce

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
    npx expo start
   ```
3. Open on web, tap button to play sound.

## Note
