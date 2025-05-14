# ExampleMAUIPublishBug
Created to get help debug a maui publish issue

The project runs fine when running with "Create a Windows MSIX package" is unchecked.

When publishing with latest vs2022 stable and trying to publish a win-x64 msix I receive the following error (I partially trimmed the full directory in the error):

Assets file 'ExampleMAUIPublishBug\ExampleLibrary\obj\project.assets.json' doesn't have a target for 'net9.0'. Ensure that restore has run and that you have included 'net9.0' in the TargetFrameworks for your project.

Able to workaround by changing ExampleLibrary's target framework from

<TargetFrameworks>net9.0</TargetFrameworks>

to

<TargetFrameworks>net9.0;net9.0-android;net9.0-ios;net9.0-maccatalyst;net9.0-windows10.0.19041.0</TargetFrameworks>

but not a viable solution for my real world project because it creates build issues for other non maui executables that use it
