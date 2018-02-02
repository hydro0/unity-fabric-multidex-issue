# Why this exists

I faced an issue using `Fabric SDK` on Android when I reached the 65k method references issue. So, the issue is that both problems need the same solution: override base application class in `AndroidMainfest.xml`. But you can override it only with one of both - `FabricApplication` or `MultiDexApplication`. To make this possible, add this small `jar` file to your `Assets/Plugins/Android` directory and in your `AndroidManifest.xml` file add `android:name="io.fabric.unity.android.MultiDexFabricApplication"` to your `<application>` tag. 

# How it works
It simply extends `FabricApplication` class and add `MultiDex.install(this)` to the `attachBaseContext` method. That's how you have both `multidex` and `fabric` working together for the majesty of your application! 
