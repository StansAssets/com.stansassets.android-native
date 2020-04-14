Android Native Pro
-------------------
The asset goal is simple. We want to build the best Android Native plugin on the [Unity Asset Store](https://assetstore.unity.com/packages/tools/integration/android-native-pro-125691). The plugin contains all the Android features you can think of, but in case you miss something, do not hesitate to get in touch. 

[Get from The Asset Store](https://assetstore.unity.com/packages/tools/integration/ios-native-pro-119175) |  [Scripting Reference](https://api.stansassets.com/ios-native/) | [Wiki](https://github.com/StansAssets/com.stansassets.android-native/wiki/) | [Forum](https://forum.unity.com/threads/introducing-ios-native-pro.535120/) | [Support](https://stansassets.com/)

About Us
-------------------
We are committed to developing high quality and engaging entertainment software. Our mission has been to bring a reliable and high-quality Unity Development service to companies and individuals around the globe. 
At Stan's Assets, we make Plugins, SDKs, Games, VR & AR Applications. Do not hesitate do get in touch, whether you have a question, want to build something or just to say hi :) [Let's Talk!](mailto:stan@stansassets.com)

[Website](https://stansassets.com/) | [LinkedIn](https://www.linkedin.com/in/lacost/) | [Youtube](https://www.youtube.com/user/stansassets/videos) | [Github](https://github.com/StansAssets) | [AssetStore](https://assetstore.unity.com/publishers/2256)

Plugin Build principles
-------------------
Apart from all the statements above, the Ultimate Mobile will inherit all the pro-line plugins development principles:

-  **Full Open source.** I believe only open-source products can work for the developer community. If you are a junior developer, we will be happy if you learn something with our code. If you are a senior developer, we do not want you to have a “backbox” in your project, and we are always open to critics and suggestions.
- **Strict code convention.**  We mostly use default the default [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/inside-a-program/coding-conventions), but with few adjustments, we believe would help our users.
   - Filename / Class will contain plugin code prefix, so you will always know where it belongs.
   - Every public API is documented. Check our the [Scripting References](https://api.stansassets.com/ios-native/).
 - **Nice looking and user-friendly settings editor.** Every plugin we make will have one centralized, good-looking, and intuitive settings editor.
 - **Ability to enable/disable modules.** We understand you want to keep your project as clean as possible and application build size as small as possible. With our plugin only feature you use will be included in the project. You also have to enable explicitly enable the module, so you always aware of what exactly included in the build. 
 - **Automatic project configuration.** You do not have to make any additional configuration for your build. If something is missing, the plugin will fix this with the build pre-processing stage. The main goal is to be able to support cloud build services out of the box.
- **Jar Resolver (EDM4U) Support** This is the only proper way to make sure our plugin will play nice will all other 3rd party plugins you may have in your project.

API Convention
-------------------
We do not want you to learn "another 3rd party plugin" API, that's why Android Native plugin API is mirroring the Google official `Java` API in a `CSharp-ish` manner.  As an example see the sample how to share text content.

Google `Java` API.  Sample from [Send text content](https://developer.android.com/training/sharing/send#send-text-content) guide.

```java
Intent sendIntent = new Intent();
sendIntent.setAction(Intent.ACTION_SEND);
sendIntent.putExtra(Intent.EXTRA_TEXT, "This is my text to send.");
sendIntent.setType("text/plain");

Intent shareIntent = Intent.createChooser(sendIntent, null);
startActivity(shareIntent);
```

Android Native plugin (`C#`)
```csharp
using SA.Android.App;
using SA.Android.Content;
...

AN_Intent sendIntent = new AN_Intent();
sendIntent.SetAction(AN_Intent.ACTION_SEND);
sendIntent.PutExtra(AN_Intent.EXTRA_TEXT, "This is my text to send.");
sendIntent.SetType("text/plain");
AN_MainActivity.Instance.StartActivity(sendIntent);
```
