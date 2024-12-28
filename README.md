# راهنمای پروژه 
با چند مقدمه شروع میکنم بعد میریم سر 
<b>اصل ماجرا</b>
## اول بودن یک عدد
### می خوایم یک تابعی داشته باشیم که عددی به عنوان ورودی بگیره و به ما بگه که عدد اول هست یا نه
قبل از شروع بیایم مضارب عدد 12 و 5 رو بررسی کنیم<br>12 = 1 , 2 , 3 , 4 , 6 , 12 <br>
5 = 1 , 5 <br>
می تونیم به این نتیجه برسیم غیر از خود عدد و عدد یک اگر عددی وجود داشته باشه که به عدد ما بخش پذیر باشه پس عدد اول نیست <br>
الگوریتم این کار به این صورت است که در ابتدا یک حلقه داشته باشیم و از عدد 2 تا عدد قبل از اون عدد مثلا اگر عدد مورد نظر 5 باشه تا عدد قبل اون میشه عدد 4 حلقه ما یک شرط خاصی رو بررسی کنه <br> 
<br>
خب اون شرط چیه؟اون شرط اینکه ما زمانی که عدد خودمون رو تقسیم بر اون عددی که از 2 تا 4 میشماریم باقی مانده آن صفر باشه که کد اون میشه
<br><code>input % i == 0</code><br>
پس یعنی ما در اون حالت یک عدد دیگه غیر از 1 و 5 پیدا کردیم پس کافیه بگیم <b>نخیر عدد مورد نظر اول نیست</b>
که اون رو به زبان برنامه نویسی بهش میگیم  <br><code>false</code><br>
حالا همون عدد 5 رو فرض کنیم زمانی که هیچ عددی بعد از پایان حلقه پیدا نکردیم که اتفاق بالا براش بیوفته خب پس بعد حلقه میگیم اگه این اتفاق نیوفتاد پس اون عدد اوله پس در برنامه نویسی بهشم میگیم
<br><code>true</code>

### فقط یک نکته
همونطور که خود فایل گفته عدد 1 نه اول و نه مرکب پس در همین حالت ما قبل از وارد شدن به حلقه بررسی میکنیم اگه عدد اول باشه باید مقدار نادرست بودن رو بگه چون ما فقط دنبال اعداد اول هستیم.
### کد همین حرفام به صورت تابع 
```cpp
#include <iostream>
using namespace std;

//بررسی اول بودن عدد ورودی با استفاده از 
//true - false
bool checkPrime(int input) {
    if (input == 1) 
        return false;
        
        
    for (int i = 2; i < input; i++) {
        if (input % i == 0) {
            return false;
        }
    }
    return true;
}

void main(){
//تابع اصلی اجرای برنامه باید حواسمان باشد که این تابع باید اخرین تابع باشد
}
```

### // -> یعنی کامند و فقط برای توضیحاته
### خب کاربرد این تابع در کد چطوریه
```cpp
for (int i = 100; i < 1000; i++) {
    if (checkPrime(i)) {
        // خب شرط درست بوده و این عدد الان اوله باید یسری کار دیگه روش انجام بدیم
    }
}
```

به این صورت که خود خروجی تابع ما باعث میشه شرط ما در صورت درست بودن اجرا بشه <br>
تو این کد ما اعداد اول رو پیدا می کنیم <b>نه اعداد جان سخت مد نظر پروژه
</b> می تونیم کارهای دیگه روش انجام بدیم <br>

<br> <code>true ---> </code> درست بودن <br>
این کد در کل اعداد اول 100 ت 1000 رو پیدا می کنه 

## نحوه حذف رقم از سمت راست
کافی است عدد را تقسیم بر 10 کنیم 
```cpp
num = num /10;
```


## ورودی N
بحثش اینکه ما عددی به عنوان بهش میدیم تعداد رقم های اعدادی هست که ما بررسی می کنیم
<br>
منظورش این بوده که عدد ما چند رقمی باشه و گفته حتما باید از 1 تا 8 وارد بشه یعنی ما حداکثر میتونمی عدد 8 رقمی بدیم اگه بیشتر شد باید برنامه ما اجرا بشه
<br>
خب می تونیم از این ایده بگیریم که عدد 10 رو به توان تعداد رقم ها برسونیم این مقدار عدد شروع رو به ما میده و یک بار دیگه ها عدد 10 رو به توان (همون تعداد رقم ها + 1) برسونیم که مقدار پایان بازه رو بهمون میده
```cpp
for(int i = شروع ; i < پایان ;i++){
}
```

## اصل ماجرا
ما باید ابتدا بعد از بررسی شروط گفته شده مثل بازه 1 تا 8 رقمی بودن رو بررسی کنیم 
<br>
سپس حلقه رو با توجه به مقدمه بالایی مربوط به ورودی یک حلقه ایجاد کنیم
<br> 
داخل حلقه یک حلقه دیگه داشته باشیم مثلا 
<br>
while(checkPrime(num))
<br>
خب تا اینجا تا زمانی ما هر بلایی سر عدد میاریم هر بار بررسی میشه که اوله یا نه و کار ما اینکه داخل بدنه حلقه دوم هر بار عدد رو یک رقم از سمت راست کم کنیم و یک شرط قبل از حذف رقم هم داشته باشیم که عدد یک رقمی بود مثلا از عدد 10 کمتر بود ، پس عدد جان سخت است<br>
حواستون باشه عدد <br>
<code>i</code>
<br> رو اینجا چاپ می کنیم نه عدد یک رقمی باقی مانده رو 
 و همیچنین بعد از چاپ باید از حلقه دوم خارج بشیم خب چطوری
<code>break;</code>
<br>
موفق باشید
