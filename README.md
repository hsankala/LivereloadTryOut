# LivereloadTryOut
LivereloadTryOut

I'm trying to get [RickStrahl - Westwind.AspnetCore.LiveReload][1] package to work on a vanilla asp.net solution. I have followed the instructions as the github readme [here][1]

In `Startup.ConfigureServices()` I have added

```
services.AddLiveReload(config =>
{
    // optional - use config instead
    //config.LiveReloadEnabled = true;
    //config.FolderToMonitor = Path.GetFullname(Path.Combine(Env.ContentRootPath,"..")) ;
});
```

In `Startup.Configure()` I have added 

```
app.UseLiveReload();

app.UseStaticFiles();
app.UseMvcWithDefaultRoute();
```

Configuration Settings have been added:
```
{
  "LiveReload": {
    "LiveReloadEnabled": true,
    "ClientFileExtensions": ".cshtml,.css,.js,.htm,.html,.ts,.razor,.custom",
    "ServerRefreshTimeout": 3000,
    "WebSocketUrl": "/__livereload",
    "WebSocketHost": "ws://localhost:5000",
    "FolderToMonitor": "~/"
  }
}
```

I've uploaded a vanilla asp.net core with RickStrahl - Westwind.AspnetCore.LiveReload nuget package and configuration to a public github repo [here][2]

I'm simply running this website in Visual studio IISExpress and updating the CSS file in the wwwroot folder, but the browser does not update with the changes


  [1]: https://github.com/RickStrahl/Westwind.AspnetCore.LiveReload
  [2]: https://github.com/hsankala/LivereloadTryOut
