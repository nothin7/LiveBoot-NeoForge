# LiveBoot — NeoForge 1.21.1

A small client-side proof-of-concept that displays Minecraft Log4j events in a
LiveBoot-inspired early loading overlay.

## Target
- Minecraft 1.21.1
- NeoForge 21.1.250
- Java 21

## Build
Run `gradle build` with Gradle 8.14 and Java 21, or push this project to a
GitHub repository and run **Actions → Build LiveBoot**. The JAR is uploaded as
a workflow artifact.

## Install
Put the resulting `liveboot-0.1.0.jar` in the client instance's `mods` folder.
This is client-only; do not install it on a dedicated server.

## Important limitations
- The appender is attached when LiveBoot's mod constructor runs. It cannot
  recover log events emitted before that point.
- The mixin replaces the NeoForge loading overlay's render method. This is an
  early-loading integration and must be tested against the exact NeoForge
  build and other loading-screen mods.
- The progress bar is an animated activity indicator, not a true percentage.
  This proof-of-concept does not have a reliable public progress value for all
  loading phases.
- This project has not been compiled or runtime-tested in this environment.
  If it fails, share the GitHub Actions build log and I can correct the source.
