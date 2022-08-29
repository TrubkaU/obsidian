Looks like [[Flank]] already included to the Firebase.
At least I faced with that:
```

gcloud firebase test android run \
--project locuslabs-android-sdk \
--app app/build/outputs/apk/debug/app-debug.apk \
--test app/build/outputs/apk/androidTest/debug/app-debug-androidTest.apk \
--device model=walleye,version=28,locale=en_US,orientation=portrait \
--test-targets "class com.locuslabs.android.sdk.TestUITest" \
--use-orchestrator \
--num-flaky-test-attempts 10 \
--timeout 30m \
--environment-variables numShards=10,shardIndex=2 \
--verbosity debug


