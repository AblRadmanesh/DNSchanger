
این ریپو به جهت توضیح درباره کد های مربوط به برنامه گذر از تحریم میباشد

اگر شما فردی باشید که برای سیستم عامل اندروید برنامه نویسی کرده باشید حتما به مشکل ارور های معروف عدم دسترسی یا 403 برخورده اید.


<div align="center">
  
<img src="https://github.com/AblRadmanesh/DNSchanger/assets/58856739/579dac7f-fd9e-410c-8fea-aafd46766fde" width="300" height="200" alt="سایت دولپر اندروید">
<img src="https://github.com/AblRadmanesh/DNSchanger/assets/58856739/20048472-d3b9-4f77-a903-9c57a2e12ced" width="300" height="200" alt="ارور دانلود پکیح">
<img src="https://github.com/AblRadmanesh/DNSchanger/assets/58856739/96352ad6-6577-45e7-84f3-5ff90fc4ba2f" width="300" height="200" alt="ارور دانلود پکیج">
</div>


دقت داشته باشید که این نمونه، نمونه ای ساده برای تغییر dns به روشی آسان تر در سیستم عامل ویندوز میباشد امیدوارم که این ریپو شروعی برای هرچه بهتر کردن این روش باشد


| یوتیوب                                 | آپارات                                  | موضوع                               |
|:------:|:----:|:----:|
|[![logo_youtube](./res/drawable/logo_youtube.png)](https://www.youtube.com/watch?v=cIVo5sNkda8)|[![logo](./res/drawable/logo.png)](https://www.aparat.com/v/24qDi)|برنامه مجموعه|


|.exe|.bat|
|-------------------|---------------|
|[دانلود برنامه](https://github.com/AblRadmanesh/Android/files/12138375/LearnDotRoid.zip)|[دانلود فایل اجرایی](https://github.com/AblRadmanesh/DNSchanger/files/12139693/LearnDotRoid.zip)|

```Batch Script 

@echo off
setlocal enabledelayedexpansion

:main


set "INSTALLED_PATH=%~dp0.installed"
set myRandom=%random%

if not exist "%INSTALLED_PATH%" (
    start "LearnDotRoid" "https://LearnDotRoid.com"
    echo installed > "%INSTALLED_PATH%"
)

set "counter=1"

for /f "skip=3 tokens=4" %%a in ('netsh interface show interface') do (
  set "adapter_!counter!=%%a"
  echo !counter!. %%a
  set /a "counter+=1"
)

echo.
set /p option=Enter the adapter number you want to configure DNS for: 

if defined adapter_%option% (
  set "selected_adapter=!adapter_%option%!"
  echo You have selected: !selected_adapter!
) else (
  echo Invalid option selected.
  exit /b 1
)
echo -------------------------
echo Web : LearnDotRoid.com
echo -------------------------
echo selected adapter : !selected_adapter!
echo -------------------------
echo Select DNS:
echo 1) 403.online
echo 2) shekan.ir
echo -------------
echo 8) delete dns
echo ( %myRandom% ) delete Android Studio
echo 0) WebSite

set /p option=Enter option:

    if "%option%"=="1" (
  ipconfig /flushdns
  netsh interface ipv4 set dns "!selected_adapter!" static 10.202.10.202 primary
  netsh interface ipv4 add dns "!selected_adapter!" addr=10.202.10.102 index=2
  echo DNS set to 10.202.10.202
  echo DNS set to 10.202.10.102
  echo Web : LearnDotRoid.com
    )

    if "%option%"=="2" (
  ipconfig /flushdns
  netsh interface ipv4 set dns "!selected_adapter!" static 178.22.122.100 primary
  netsh interface ipv4 add dns "!selected_adapter!" addr=185.51.200.2 index=2
  echo DNS set to 178.22.122.100
  echo DNS set to 185.51.200.2
  echo Web : LearnDotRoid.com
    )

    if "%option%"=="8" (
  ipconfig /flushdns
  netsh interface ipv4 set dns "!selected_adapter!" source=dhcp
  echo DNS Deleted
  echo Web : LearnDotRoid.com
    )
    if "%option%"=="0" (
        start "LearnDotRoid" "https://LearnDotRoid.com"
    )
    if "%option%"=="%myRandom%" (
        rmdir /s /q "C:\Program Files\Android"
        rmdir /s /q "C:\Users\%USERNAME%\.android"
        rmdir /s /q "C:\Users\%USERNAME%\.gradle"
        rmdir /s /q "C:\Users\%USERNAME%\AppData\Local\Android"
        rmdir /s /q "C:\Users\%USERNAME%\AppData\Local\JetBrains"
        rmdir /s /q "C:\Users\%USERNAME%\.m2"
        setlocal enabledelayedexpansion
        for /d %%i in ("C:\Users\%USERNAME%\AppData\Local\Google\AndroidStudio*") do (
            set "folder_name=%%~nxi"
            if "!folder_name:~0,13!" == "AndroidStudio" (
                rmdir /s /q "%%i"
            )
        )
        for /d %%i in ("C:\Users\%USERNAME%\AppData\Roaming\Google\AndroidStudio*") do (
            set "folder_name=%%~nxi"
            if "!folder_name:~0,13!" == "AndroidStudio" (
                rmdir /s /q "%%i"
            )
        )
        echo Deletion completed.
    )

choice /c en /n /m "Do you want to start again? (E)xit / (N)ext:"

if %errorlevel% equ 1 (
    exit /b
)

echo ----------------------------------------------------------------
echo -------------------------- restart ------------------------------
echo ----------------------------------------------------------------
goto main

```
