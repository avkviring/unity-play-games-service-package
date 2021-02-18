# Google Play Games

Unity package для работы с сервисами Google Play Games для Android.
Сделано на основе https://github.com/playgameservices/play-games-plugin-for-unity.

Основные отличия от оригинала:

- упрощен процесс конфигурирования, APP_ID перенесен в настройки проекта Project/Cheetah/
- Unity NPM Package для удобного распространения 

**Пример**
```c#
 var webAppId = "***";
 PlayGamesClientConfiguration config = new PlayGamesClientConfiguration.Builder(webAppId)
    .RequestIdToken()
    .RequestEmail()
    .Build();
 PlayGamesPlatform.InitializeInstance(config);
 PlayGamesPlatform.Activate();

 PlayGamesPlatform.Instance.Authenticate(SignInInteractivity.CanPromptAlways, (result) =>
 {
          Debug.Log("AndroidAuth Authenticate " + result);
          Debug.Log("AndroidAuth Token Id " + PlayGamesPlatform.Instance.GetIdToken());
          Debug.Log("AndroidAuth Token User Id " + PlayGamesPlatform.Instance.GetUserId());
          Debug.Log("AndroidAuth Token Display Name " + PlayGamesPlatform.Instance.GetUserDisplayName());
 });            
```

