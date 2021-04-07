### Scenario: launch player, go to Pip, dismiss Pip (dragging to the bottom)

##### Android 10
```
2021-04-07 14:22:35.434 18884-18884/com.example.android.pictureinpicture D/MainActivity: onActivityStarted: [isInPictureInPictureMode=false]
2021-04-07 14:22:35.438 18884-18884/com.example.android.pictureinpicture D/MainActivity: onActivityResumed: [isInPictureInPictureMode=false]
2021-04-07 14:22:59.436 18884-18884/com.example.android.pictureinpicture D/MainActivity: onActivityPaused: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:23:04.868 18884-18884/com.example.android.pictureinpicture D/MainActivity: onActivityStopped: [isInPictureInPictureMode=false] [isFinishing=false]
2021-04-07 14:23:04.898 18884-18884/com.example.android.pictureinpicture D/MainActivity: onActivitySaveInstanceState: [isInPictureInPictureMode=false]
```

##### Android 11

```
2021-04-07 14:24:22.956 10452-10452/com.example.android.pictureinpicture D/MainActivity: onActivityStarted: [isInPictureInPictureMode=false]
2021-04-07 14:24:22.959 10452-10452/com.example.android.pictureinpicture D/MainActivity: onActivityResumed: [isInPictureInPictureMode=false]
2021-04-07 14:24:34.530 10452-10452/com.example.android.pictureinpicture D/MainActivity: onActivityPaused: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:24:38.336 10452-10452/com.example.android.pictureinpicture D/MainActivity: onActivityStopped: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:24:38.337 10452-10452/com.example.android.pictureinpicture D/MainActivity: onActivitySaveInstanceState: [isInPictureInPictureMode=true]
```

##### Observations:
- in onStop, Android10 reports isInPictureInPictureMode=false whereas Android 11 reports isInPictureInPictureMode=true


### Scenario: launch player, go to Pip, close Pip (with the x button) 
Same logs and results from previous scenario.

### Scenario: launch player, go to Pip, lock the device

##### Android 10
```
2021-04-07 14:54:48.415 23945-23945/com.example.android.pictureinpicture D/MainActivity: onActivityStarted: [isInPictureInPictureMode=false]
2021-04-07 14:54:48.416 23945-23945/com.example.android.pictureinpicture D/MainActivity: onActivityResumed: [isInPictureInPictureMode=false]
2021-04-07 14:54:50.705 23945-23945/com.example.android.pictureinpicture D/MainActivity: onActivityPaused: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:54:55.116 23945-23945/com.example.android.pictureinpicture D/MainActivity: onActivityStopped: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:54:55.117 23945-23945/com.example.android.pictureinpicture D/MainActivity: onActivitySaveInstanceState: [isInPictureInPictureMode=true]
```

#####  Android 11

```
2021-04-07 14:59:01.788 8046-8046/com.example.android.pictureinpicture D/MainActivity: onActivityStarted: [isInPictureInPictureMode=false]
2021-04-07 14:59:01.790 8046-8046/com.example.android.pictureinpicture D/MainActivity: onActivityResumed: [isInPictureInPictureMode=false]
2021-04-07 14:59:04.876 8046-8046/com.example.android.pictureinpicture D/MainActivity: onActivityPaused: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:59:09.917 8046-8046/com.example.android.pictureinpicture D/MainActivity: onActivityStopped: [isInPictureInPictureMode=true] [isFinishing=false]
2021-04-07 14:59:09.919 8046-8046/com.example.android.pictureinpicture D/MainActivity: onActivitySaveInstanceState: [isInPictureInPictureMode=true]
```

##### Observations:
- no differences between Android 10 and Android 11
- in onStop, Android 10 reports isInPictureInPictureMode=true, but in the scenario where the Pip is dismissed or closed, it returns isInPictureInPictureMode=false in onStop