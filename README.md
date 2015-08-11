# gradle-fileupload

[![Build Status](https://travis-ci.org/anshulverma/gradle-fileupload.svg?branch=master)](https://travis-ci.org/anshulverma/gradle-fileupload)

A gradle plugin to upload a file to a remote loacation

## Usage

``` groovy
// first add the maven dependency for the plugin
buildscript {
  repositories {
    mavenCentral()
    jcenter()
    maven {
      url "https://plugins.gradle.org/m2/"
    }
  }
  dependencies {
    classpath 'net.anshulverma.gradle:fileupload:0.0.1'
  }
}

// then apply the plugin
apply plugin: 'fileupload'

// then specify properties for file upload
fileupload {
  url = 'http://upload.file.com/destination'
  file = "$projectDir/build/distributions/my-build-file.tar.gz"
  params.'type' = 'new'
  auth {
    username = 'admin'
    password = 'pass1234'
  }
}
```