## اسکریپت ربات نمایش مشخصات اشتراک ( پنل  x-ui)  v.2 نسخه بتا

<br>

### امکانات

- ایجاد حساب برای کاربران
- نمایش نوتیفیکیشن هنگام اتمام اشتراک ( به کاربر و ادمین )
- تبدیل لینک به QrCode
- نمایش نام اکانت
- نمایش وضعیت 
- نمایش حجم کلی
- نمایش مصرف دانلود
- نمایش مصرف آپلود 
- نمایش استفاده حجم کلی
- نمایش حجم باقیمانده
- نمایش تعداد روزهای باقی مانده
- نمایش تاریخ اتمام اشتراک
- نمایش کلید ورودی  
- پنل مدیریت حرفه ای
- مدیریت سرور ( ایجاد - حذف - نمایش )
- و ....

<br>

## فقط پشتیبانی از پنل های زیر:

```` 
https://github.com/vaxilu/x-ui
```` 



```` 
https://github.com/HexaSoftwareTech/x-ui
````


```` 
https://github.com/NidukaAkalanka/x-ui-english
```` 

<br>


### پیش نیاز

- هاست خارجی ( cpanel )
- دامنه + ssl



<br>
## نکته مهم در مورد آدرس پنل ورود به xui: 
بدلیل محدودیتی که در بعضی از هاست های اشتراکی هست امکان ارسال درخواست از سمت اسکریپت به پورت های غیر 80 و 443 و 8080 و چند پورت دیگر مخصوص سی پنل که برای http و https هست وجود ندارد
<br>

### آموزش نصب

1. لینک زیر را وارد در مرورگر باز کنید و پروژه رو دانلود کنید
```` 
https://github.com/wizwizdev/wizwizxui-timebot/archive/refs/heads/main.zip
````
2. داخل ربات Bothfather یک ربات ایجاد کنید و توکن را در جایی ذخیره کنید
3. وارد پنل مدیریتی cpanel شوید
4. روی MySQL® Databases کلیک کنید و یک دیتابیس ایجاد کنید
5. سپس یک ناک ربری و پسورد برای دیتابیس انتخاب کنید و در جای ذخیره کنید
6. سپس به صفحه اصلی مدییریتی cpanel برگردید
7. روی File Manager کلیک کنید
8. پروژه ای را که دانلود کردید را آپلود کنید و سپس از حالت اکسترک خارج کنید
9. ادرسی که فایل createDB.php قرار دارد را همراه با دامنه داخل مرورگر وارد کنید و باید صفحه سفید باشد در این صورت دیتابیس شما ساخته می شود:

```` 
https://yordomain.com/wizwizxui-timebot-main/createDB.php
````
یا اگر به صورت ساب دامین هست:
```` 
https://sub.yordomain.com/wizwizxui-timebot-main/createDB.php
````

<br>


#### بعد باز کردن اگر خطای زیر در صفحه بود یعنی ماژول ionbube فعال نیست (در 99درصد هاست های اشتراکی فعال است) برای نصب ماژول مربوطه به هاستینگ تیکت بزنید و بدون مشکل برای شما فعال می کنند. 


![5634](https://user-images.githubusercontent.com/27927279/222905888-cd79782d-dbc3-4301-91b8-abe9eb6fc5c2.JPG)



<br>

10.  فایل config.php را ویرایش کنید اطلاعات دیتابیس ، توکن ربات از Botfather و آیدی عددی خودتون و کانال تلگرامی ( برای ارسال اعلان اتمام حجم کاربر ) از طریق ربات get_id_bot بگیرید و جایگزین کنید:
```` 
$Config = [
    'api_token' => "",
    'admin' => [],
    'report_channel' => -1000000 // -100xxxxxxx
];
$Database = [
    'dbname' => "",
    'username' => "",
    'password' => ''
];
````

12. الان باید وبهوک رو ست کنید، آدرس زیر را ویرایش و اطلاعات توکن و آدرس را جایگزین سپس در مرورگر اجرا کنید:
````
https://api.telegram.org/bot1/setWebhook?url=2/bot.php
````
به جای 1 باید توکن ربات و به جای 2 آدرس را وارد کنید : مثال
````
https://api.telegram.org/botHsMMWOqfNvYwuCU_1IzzCsQ34334/setWebhook?url=https://yordomain.com/wizwizxui-timebot-main/bot.php
````

13. به صفحه اصلی cpanel برگردین و روی دکمه Cron Jobs کلیک کنید:
- در قسمت Common Settings حالت Once Per Minute(* * * * *) را انتخاب کنید
- در قسمت Command لطفا ادرس زیر را وارد کنید:
````
/usr/bin/php -q address1 >/dev/null 2>&1
````
- به جای addres1 باید آدرس فایل serverWarn.php را قرار دهید و ذخیره کنید مثال:
````
/usr/bin/php -q /home/yourfolder/public_html/yordomain.com/wizwizxui-timebot-main/serverWarn.php >/dev/null 2>&1
````
14. همین مراحل را برای فایل warnUsage.php تکرار کنید:
````
/usr/bin/php -q address2 >/dev/null 2>&1
````
- به جای addres2 باید آدرس فایل serverWarn.php را قرار دهید و ذخیره کنید مثال:
````
/usr/bin/php -q /home/yourfolder/public_html/yordomain.com/wizwizxui-timebot-main/warnUsage.php >/dev/null 2>&1
````

15. سپس ربات را استارت کنید و لذت ببرید

<br>
### مهم:
- به هیچ وج اطلاعات دیتابیس ، سی پنل ، و توکن ربات را در اختیار کسی قرار ندید
<br>


حتما داخل گروه جوین شین و از ما حمایت کنید 👇

## Contact Developer
💎 Group: https://t.me/wizwizdev
