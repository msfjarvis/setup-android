# [DEPRECATED] Android build container for GitHub Actions

**Deprecated**: Since this action's inception, GitHub Actions has grown by leaps and bounds and now it is possible to build Android apps without this image. Due to this, I am electing to deprecate setup-android and have submitted PRs to active projects that were using it, removing their use of setup-android.

This Action lets you build Android apps in an Android SDK environment with nearly everything from the SDK packages list, already installed. If you find something missing, please start an issue here so that I can fix it for you.

[Use this Action](https://github.com/marketplace/actions/setup-android)

## Contents

- [Usage](#usage)
- [Changelog](#changelog)

## Usage

```yml
- name: "Run test suite"
  uses: msfjarvis/setup-android@1.0
  with:
    entrypoint: ./gradlew
    args: dependencies spotlessApply detekt assembleDebug
```

With this configuration the container will run `./gradlew dependencies spotlessApply detekt assembleDebug` as a build step.

## Changelog

### 1.0

- Allow running arbitrary tasks with `run: <commands>`.

### 0.2

- Switch to Ubuntu-based flavor of base image. This is useful to get the version of `patch(1)` that I require
  in my projects.

### 0.1

- Initial release
