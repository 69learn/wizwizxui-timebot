# ویزویز
![](https://img.shields.io/github/v/release/wizwizdev/wizwizxui-timebot.svg)
![](https://visitor-badge.glitch.me/badge?page_id=wizwizdev.wizwizdev)
![Downloads](https://img.shields.io/github/downloads/wizwizdev/wizwizxui-timebot/total.svg)



<br>


## نصب 

- هاست cpanel یا سرور لیونکس 
- دامنه + ssl

<br>



<br>

## تنظیمات پیشفرض

- پورت پنل و هاست یا سرور باید 80 - 8080 - 54321 باشد 
- در صورت مواجه با پیغام زیر یا ثبت نشدن سرور داخل ربات لطفا به هاستینگ برای باز کردن پورت های مدنظر تیکت بدید

```` 
Failed to connect to yourdomain.com port 80 after 340 ms: Couldn't connect to server
````

این خطا به معنی این است که پورت 8080 پنل شما روی هاست یا سرور باز نیست و باید باز کنید 


<br>

## نصب 

```` 
https://github.com/wizwizdev/wizwizxui-timebot/archive/refs/heads/main.zip
````


> **نکته مهم: بعد از اکسترک کردن کل پروژه را از پوشه اصلی ربات wizwizxui-timebot-main خارج و مستقیم داخل public_html آپلود کنید** 

<br>


### تنظیم فایل baseInfo.php   



 ```` 
error_reporting(0);
$botToken = ''; //توکن ربات را جایگزین کنید
$dbUserName = ''; //نام کاربری دیتابیس را جایگزین کنید
$dbPassword = ''; //پسورد دیتابیس را جایگزین کنید
$dbName = ''; //نام دیتابیس را وارد کنید
$admin = ;  //آیدی عددی یا شناسه کاربری اکانت ادمین را از این ربات بگیرید و جایگزین کنید get_id_bot
$channelLock = ""; //آیدی کانال برای قفل اجباری همراه با @ جایگزین کنید
$botUrl = "https://yourdomain.com/"; //دامنه خود را جایگزین کنید
$walletwizwiz = ""; //شماره کارت یا کیف پول خود را جایگزین کنید
````

- برای ایجاد ربات و دریافت توکن از طریق ربات @bothfather یک ربات ایجاد کنید و توکن را جایگزین کنید 
- برای دریافت آیدی عددی از ربات @chatIDrobot دریافت کنید و سپس جایگزین کنید
- برای کانال لطفا آیدی کانال همراه با @ جایگزین کنید ( حتما ربات مدیر کانال باشد جهت قفل کانال )
- دامنه خود را نیز جایگزین yourdomain.com کنید
- و شماره کارت یا کیف پول ولت خود را نیز میتوانید داخل "" قرار دهید



<br>

### تنظیم کرون جاب:


- در قسمت Common Settings حالت Once Per Minute(* * * * *) را انتخاب کنید
- در قسمت Command لطفا ادرس زیر را وارد کنید:
````
/usr/bin/php -q address1 >/dev/null 2>&1
````
- به جای addres1 باید آدرس فایل messagewizwiz.php را قرار دهید و ذخیره کنید مثال:
````
/usr/bin/php -q /home/yourfolder/public_html/yordomain.com/messagewizwiz.php >/dev/null 2>&1
````
or
````
/usr/bin/php -q /home/yourfolder/public_html/messagewizwiz.php >/dev/null 2>&1
````

<br>


- همین مراحل را برای فایل warnUsage.php تکرار کنید:

````
/usr/bin/php -q address2 >/dev/null 2>&1
````
- به جای addres2 باید آدرس فایل warnUsage.php را قرار دهید و ذخیره کنید مثال:
````
/usr/bin/php -q /home/yourfolder/public_html/yordomain.com/warnUsage.php >/dev/null 2>&1
````
or
````
/usr/bin/php -q /home/yourfolder/public_html/warnUsage.php >/dev/null 2>&1
````

<br>


### تنظیم ست وبهوک 


````
https://api.telegram.org/bot1/setWebhook?url=2/bot.php
````
به جای 1 باید توکن ربات را جایگزین کنید و به جای 2 آدرس پروژه را وارد کنید : مثال
````
https://api.telegram.org/bot365447414:AAFjkjKJHoLKJIOJKLK89jklYwuCU_1IzzCsKJHKQvv/setWebhook?url=https://yordomain.com/wizwizxui-timebot-main/bot.php
````

- اگر در خروجی متن زیر نمایش داد یعنی تبریک میگم شما به درستی ربات را اجرا کردید

````
{"ok":true,"result":true,"description":"Webhook was set"}
````


<br>

## تنظیم فایل htaccess برای بالا بردن امنیت  

- بعد از Extract کردن فایل های پروژه احتمالا فایل htaccess برای شما قابل دیدن نباشد ابتدا گوشه سمت راست بالا بر روی Settings کلیک کنید
- در پنجره باز شده تیک گزینه Show Hidden Files (dotfiles) را فعال کنید و سپس save را بزنید
- در آخر فایل .htaccess را از پوشه بات خارج کنید و مستقیم در public_html قرار دهید


<br>

## نکات مهم بعد از نصب:

- برای قفل اجباری ربات باید حتما ادمین کانال باشد
- لوکیش هاست یا سرور باید خارج از ایران باشد
- اگر از پروتکل تروجان استفاده می کنید ( پنل باید قابلیت ساخت تروجان را داشته باشد در غیر اینصورت به مشکل بر میخورید )
- اعتبار اعلان بعد از 2 روز صفر می شود ( بعد از دو روز اگر مجدد حجم یا زمان کم باشه ارسال می شود )
- اگر موقع تنظیم کرون جاب پیام همگانی یا اعلان ارسال نشد ( هنگام تنظیم کرون جاب فقط ادرس دامنه را از داخل command پاک کنید )
- برای ایجاد کانفیگ تست قیمت را 0 قرار دهید ( هر اکانت فقط یک بار میتواند اکانت تست رایگان استفاده کند 


<br>


## پشتیبانی از پنل های زیر:



- ( سنایی ) تک پورتی ، چند پورتی
```` 
https://github.com/MHSanaei/3x-ui
```` 
- ( علیرضا ) تک پورتی ، چند پورتی
```` 
https://github.com/alireza0/x-ui
```` 
- ( وکسیلو ) فقط تک پورتی
```` 
https://github.com/vaxilu/x-ui
```` 
- ( اسدی ) تک پورتی ، چند پورتی
```` 
https://github.com/HexaSoftwareTech/x-ui
````
- ( نیدوکا کالانکا ) تک پورتی ، چند پورتی
```` 
https://github.com/NidukaAkalanka/x-ui-english
```` 


<br>


### هنگام اضافه کردن سرور به ربات لطفا به صورت زیر آدرس وارد کنید
````
https://youdomain.com:8080
````

````
https://youdomain.com:8080/path
````

````
http://192.180.125:8080
````


#### آدرس زیر اشتباه می باشد

````
https://youdomain.com:8080/xui/inbounds
````

````
https://youdomain.com:8080/
````


<br>

### تنظیم سرتیفیکیت داخل ربات

````
{"serverName": "","certificates": [{"certificateFile": "","keyFile": ""}]}
````

- serverName: yourdomain
- certificateFile: /root/cert.crt
- keyFile: /root/private.key

<br>



### امکانات ویزویز


- فروش خودکار vless - vmess - trojan
- تنظیم و ایجاد کانفیگ با قابلیت:
- ( حجم - روز - شبکه - پروتکل - تک کاربره {بستگی به پنل دارد } )
- ایجاد سرور  و مدیریت:
- ( نام - پرچم - ریمارک - ظرفیت - header - request - request - tls - sni - ip )
- ایجاد دسته و مدیریت آن
- ایجاد پلن و مدیریت آن
- ایجاد کانفیگ پورت اشتراکی و پورت اختصاصی
- ایجاد کانفیگ تست برای کاربران ( قبل از خرید )
- قابلیت کارت به کارت جهت پرداخت ( تایید توسط مدیر )
- ارسال خودکار کانفیگ به همراه لینک + نام کانفیگ + qrcode برای کاربر
- مشاهده مشخصات کامل کانفیگ خریداری شده
- نمایش اکانت های فروخته شده هر پلن
- بخش سیستم تیکت پیشرفته ( تیکت طور )
- قابلیت نمایش ( لینک نرم افزارها )
- ارسال پیام همگانی با کرون جاب 
- فعال یا غیرفعال کردن ( فروش - مشخصات کانفیگ یا هردو باهم )
- اعلان اتمام حجم و زمان کانفیگ ( فقط به کاربر )
- اینلاین شدن ( مشخصات کانفیگ )
- قفل اجباری کانال
- پشتیبانی پنل سنایی 
- پشتیبانی پنل علیرضا 
- پشتیبانی پنل وکسیلو
- پشتیبانی پنل اسدی
- پشتیبانی پنل نیدوکا 
- امکان اضافه کردن حساب توسط کاربر
- امکان مدیریت و حذف حساب توسط کاربر
- امکان ثبت کانفیگ به vless - vmess - uuid ( تروجان به خوبی پشتیبانی نمی کند )
- دریافت اطلاعات کانفیگ ( برای تک پورت و چند پورت )
- نمایش نام اکانت
- نمایش کلید ورودی  
- نمایش وضعیت
- نمایش حجم کلی
- نمایش مصرف دانلود
- نمایش مصرف آپلود 
- نمایش استفاده حجم کلی
- نمایش حجم باقیمانده
- نمایش تعداد روزهای باقی مانده
- نمایش تاریخ اتمام اشتراک

<br>

حتما داخل گروه جوین شین و از ما حمایت کنید 👇

## Contact Developer
💎 Group: https://t.me/wizwizdev
