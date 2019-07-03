# MCPmf :: Minecraft Cursed POMF (privately offered mapping files)

Minecraft Cursed POMF is a set of client mappings for legacy minecraft versions.

The gradle used for this is mostly still based of yarn's, so improvements to the gradle tasks are welcome.

To see the current version being targetted, check the branch name!

## Usage
To use yarn-deobfuscated Minecraft for Minecraft modding or as a dependency in a Java project, you can use [loom](https://github.com/fabricmc/fabric-loom) Gradle plugin. See [fabric wiki tutorial](https://fabricmc.net/wiki/tutorial:setup) for more information.

To obtain a deobfuscated Minecraft jar, [`./gradlew mapNamedJar`](#mapNamedJar) will generate a jar named like `<minecraft version>-named.jar`, which can be sent to a decompiler for deobfuscated code.
Alternatively, use the functions provided by enigma to decompile

## Contributing

Please remember that copying and pasting mappings from alternate projects under more restrictive licenses (such as the real MCP) is **completely forbidden** without explicit permission from the 
owners of said mappings.

When contributing remember to read the conventions (Conventions.md).

To contribute, fork the project and clone it locally, and use enigma to map the jar. Then push to your fork and submit a pull request.

**Anyone** can comment and suggest changes on pull requests. We want to make sure the mappings are the best quality, so make your voice known!
### Getting Started

MCPomf started as a yarn fork, so tasks currently still reference yarn.

1. Fork and clone the repo
2. Run `./gradlew yarn` (Linux, macOS) or `gradlew yarn` (Windows)
3. Profit

## Gradle
MCPomf uses Gradle to provide a number of utility tasks for working with the mappings.

### `yarn`
[`setupYarn`](#setupYarn) and download and launch the latest version of Fabric's fork of [Enigma](https://github.com/FabricMC/Enigma)

Compared to launching Enigma externally, the gradle task adds a name guesser plugin that automatically map enums and a few constant field names.

### `build`
Build a GZip'd archive containing a tiny mapping between official (obfuscated), [intermediary](https://github.com/FabricMC/intermediary), and MCPomf names ("named") and packages enigma mappings into a zip archive..

### `mapNamedJar`
Builds a deobfuscated jar with yarn mappings and automapped fields (enums, etc.).

### `download`
Downloads the client and server Minecraft jars for the current Minecraft version to `.gradle/minecraft`

### `setupYarn`
[`download`](#download)
