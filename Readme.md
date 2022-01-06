# ElectronNet 實作

## 流程說明

- 目前 `ElectronNET` 僅支援 `.Net 5` 版本

- 建立專案流程
  - `dotnet new webapp`
  - `dotnet restore`
  - `dotnet add package ElectronNET.API`
  - `electronize init`

- 調整 `Program.cs`
  - 加入引用 `using ElectronNET.API;`
  - `CreateHostBuilder()` 在 `UseStartup<Startup>()` 之後加上 `.UseElectron(args)`

- 調整 `Startup.cs`
  - 加入引用 `using ElectronNET.API;`
  - `Configure()` 方法內最後一行加入 `Task.Run(async () => await Electron.WindowManager.CreateWindowAsync());`

- 執行 `ElectronNet`
  - `electronize start`


## 參考資料

- [用 ASP.NET Core 寫桌面 GUI 應用程式 - Electron.NET](https://blog.darkthread.net/blog/electron-net/)
- [Electron.net —— 把網頁包成桌面應用吧](https://igouist.github.io/post/2020/06/electron-net/)
- [.Net 5 轉移至 .Net 6 相關變化說明](https://docs.microsoft.com/en-us/aspnet/core/migration/50-to-60-samples?view=aspnetcore-6.0)