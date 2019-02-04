# Unity Package Example
A simple example showing how to create a custom package for use with the Unity Package Manager introduced in 2018.1

## Requirements
* Unity 2018.3 or later.
* Git executable installed on your machine ([Windows](https://gitforwindows.org/), [Mac](https://git-scm.com/download/mac)).
* Git executable path listed in the PATH system environment variable.
* Package contents and package.json file must be located in the root of the repository.
* Must add an [Assembly Definition](https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html) file to the package since it lives outside any Assets folder.
* More information and further discussions can be found [here](https://forum.unity.com/threads/git-support-on-package-manager.573673/#post-3819487).

## Installing the Package
Simply add the name of the package (found in package.json) followed by the repository URL to your Unity project's manifest.json. Supported schemes/protocols include: git, ssh, https, http and more.

```json
{
  "dependencies": {
    "example.package": "https://github.com/IsaiahKelly/UnityPackageExample.git",
}
```

## Useful Notes:
Taken from [this thread](https://forum.unity.com/threads/git-support-on-package-manager.573673/#post-3819487).

* Big repositories can take a long time to clone. We don't cache the repository so if you change revision, the repository will be cloned again.

* The only way to update a Git package to the latest version is to remove the lock attribute from the project manifest or manually update the revision suffix.

* Since the Package Manager uses the Git executable installed on your machine. Any global or system configuration or environment variable will be picked up. These settings may affect the behaviour of the system.

* Some package managers offer a shorthand version of their supported URL schemes. For example, npm support short URLs like these: <github user>/<repository>, gitlab:<gitlab user>/<repository>. We don't support these syntaxes for the moment.
