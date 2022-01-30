# Plasma

Plasma is a set of mappings for legacy minecraft versions.

To see the current version being targetted, check the branch name!

## Usage
To use plasma-deobfuscated Minecraft for Minecraft modding or as a dependency in a Java project, you can use [loom](https://github.com/chocohead/fabric-loom) Gradle plugin. See [fabric wiki tutorial](https://github.com/minecraft-cursed-legacy/Example-Mod) for more information.

To obtain a deobfuscated Minecraft jar, [`./gradlew mapNamedJar`](#mapNamedJar) will generate a jar named like `<minecraft version>-named.jar`, which can be sent to a decompiler for deobfuscated code.
Alternatively, use the functions provided by enigma to decompile

## Contributing

Please remember that copying and pasting mappings from alternate projects under more restrictive licenses (such as MCP or Pigeon) is **completely forbidden** without explicit permission from the 
owners of said mappings. Additionally, copying from the "BIN Mappings" plasma fork is discouraged due to its not being cleanroom.

When contributing remember to read the conventions (Conventions.md).

To contribute, fork the project and clone it locally, and use enigma to map the jar. Then push to your fork and submit a pull request.

**Anyone** can comment and suggest changes on pull requests. We want to make sure the mappings are the best quality, so make your voice known!
### Getting Started

1. Fork and clone the repo
2. Run `./gradlew plasma` (Linux, macOS) or `.\gradlew plasma` (Windows)
3. Profit

## Gradle
Plasma uses Gradle to provide a number of utility tasks for working with the mappings.

### `plasma`
[`setupPlasma`](#setupPlasma) and download and launch the latest version of Fabric's fork of [Enigma](https://github.com/FabricMC/Enigma)

Compared to launching Enigma externally, the gradle task adds a name guesser plugin that automatically map enums and a few constant field names.

### `build`
Build a GZip'd archive containing a tiny mapping between official (obfuscated), [intermediary](https://github.com/FabricMC/intermediary), and plasma names ("named") and packages enigma mappings into a zip archive..

### `mapNamedJar`
Builds a deobfuscated jar with plasma mappings and automapped fields (enums, etc.).

### `download`
Downloads the client and server Minecraft jars for the current Minecraft version to `.gradle/minecraft`

### `setupPlasma`
[`download`](#download)
