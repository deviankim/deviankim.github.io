라이브러리 배포시 maven / aar 의 차이점에 대해 알아보자.

# maven vs aar

## required dependencies
##### maven
```
dependencies {
  implementation "com.rsupport.android.remotecall.sdk:remotecall-sdk-core:7.0.2.14"
}
```

##### aar
```

repositories { 
  flatDir { 
    dirs 'libs' 
    // Copy aar files to 'app/libs' folder.
  } 
}

dependencies {
  implementation name: "remotecall-core-7.0.2.14", ext: 'aar'
}
```

## additional dependencies

##### maven
```
dependencies {
  // nothing...
}
```

##### aar
```
dependencies {
  // all dependencies using in library module.
  implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk8:$kotlin_version"
  implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-android:1.4.1'
  implementation 'org.jetbrains.kotlinx:kotlinx-coroutines-core:1.4.1'
  implementation 'io.reactivex.rxjava2:rxandroid:2.1.1'
  implementation 'io.reactivex.rxjava2:rxjava:2.2.10'
  implementation 'io.reactivex.rxjava2:rxkotlin:2.3.0'

  implementation "org.jetbrains.kotlin:kotlin-reflect:$kotlin_version"
  implementation 'com.google.dagger:dagger:2.36'
  implementation 'com.squareup.okhttp3:logging-interceptor:4.4.0'
  implementation 'com.squareup.retrofit2:retrofit:2.9.0'
  implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
  implementation 'com.squareup.retrofit2:adapter-rxjava2:2.9.0'  
}
```

