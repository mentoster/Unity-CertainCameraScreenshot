# Unity Certain Camera Screenshot

### Установка:
1. Открыть https://github.com/mentoster/Unity-CertainCameraScreenshot/releases
2. Скачать пакет ScrnCameraScript.unitypackage при открытом unity.
3. Разрешить импорт в редакторе unity.
### Использование:
1.  Перетащить скрипт ScreenShot на камеру, с которой необходимо сделать скриншот.
2.  Написать свой скрипть со следующим кодом (в данном примере необходимо нажать пробел для скриншота):
  //суда помещаем нашу камеру, с которой происходит скриншот 
    public ScreenShot ScrnCamera;
    private void Update()
    {
        //Кнопка для нажатия
        if (Input.GetKeyDown(KeyCode.Space))
        {
            //делаем скриншот
            ScrnCamera.MakeScrn();
        }
    }
    или взять готовый скрипт DemoScene и поместить на сцену.
 3. Запустить сцену и нажать необходимую кнопку (пробел по дефолту)
## Ура! Вы сделали скриншот!
  Программа Автоматически  подстраивается под ваш экран.
  Программа Автоматически создаёт папку в вашем проекте под названием Screenshots и кидает туда скриншоты!
  Вы так же можете изменить формат записи имени и путь сохранения скриншотов.
  
### Ошибки на которые стоит наплевать:
1. [Ваши кровные враги](https://yadi.sk/i/GJBnVsEFowxMrQ)
2. Таааак, вот что говорит нам эта зверюга:
* ReadPixels was called to read pixels from system frame buffer, while not inside drawing frame.
* UnityEngine.Texture2D:ReadPixels(Rect, Int32, Int32)
* ScreenShot:LateUpdate() 
3.Перевожу с unityвского - вы воспользововались методом, не предназначенным для делания скриншотов!
* Это возникает из-за того что я использую LateUpdate()
* И скриншоты  работают благодаря ScrnCam.Render();
* Если использовать метод для скриншотов, то скриншот будет браться с основной камеры (больно надо).
4. Я пока не разобрался, как сказать unity перестать отображать ошибку, поэтому пока предлагаю вам с этим смириться.  

