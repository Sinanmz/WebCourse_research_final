<div dir='rtl' align='justify'>
<p align="center"><img src="https://gobuffalo.io/images/logo.svg"/></p>
  
<p align="center">
    گردآوردندگان:  سینا نمازی، امیرحسین اکبری، محمد معین صمدی آزاد  
</p>
 


  # عناوین

- [What is D3.js](#what-is-d3.js)

- [Web Standards: HTML, CSS, JavaScript](#web-standards:-html,-css,-javascript)
 
- [Install D3.js](#install-d3js)

- [Select DOM Element](#select-dom-element)

- [DOM Manipulation](#dom-manipulation)

- [Method Chaining](#method-chaining)

- [Function of Data](#function-of-data)

- [Event Handling](#event-handling)

- [Animation](#animation)

- [Data Binding](#data-binding)

- [Load Data from File](#load-data-from-file)

- [Create SVG Elements](#create-svg-elements)

- [Create SVG Chart](#create-svg-chart)

- [Scales](#scales)

- [Axes](#axes)

- [Create Bar Chart](#create-bar-chart)

- [Create Animated Bar Chart](#create-animated-bar-chart)

- [Learning Resources](#learning-resources)


  
# What is D3.js


# Web Standards: HTML, CSS, JavaScript


# Install D3.js


# Select DOM Element


# DOM Manipulation


در بخش های قبل یاد گرفتیم چگونه DOM elementها را با استفاده از D3 انتخاب کنیم. در این بخش یاد خواهیم گرفت چگونه DOM elementها را تغییر دهیم.

<div dir='rtl' align='right'>

کتابخانه D3 شیوه های تغییر DOM زیر را شامل می شود، که می توانید بعد از انتخاب کردن elementها با استفاده از ```()d3.select``` یا ```()d3.selectAll``` از آن ها استفاده کنید.
</div>

<br>

## text("content") 
از ```()d3.selection.text``` برای اضافه کردن یا تغییر دادن محتوای یک element انتخاب شده استفاده کنید:
<div  dir='ltr'  align='justify'>

  ```html
<div>
    <p></p>
</div>
<p></p>
<script>
    d3.select("p").text("This is paragraph.")
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-6)
  </div>

  در کد بالا ابتدا با استفاده از ```d3.select("p")``` اولین ```<p>``` را انتخاب کردیم، سپس```text("This is paragraph.").``` عبارت "This is Parapraph" را به پاراگراف انتخاب شده اضافه می کند.


توجه کنید که اگر از ```()d3.selectall``` استفاده می کردیم، عبارت را به همه عبارت های ```<p>``` اضافه می کرد.

<br>

## append("element name")
 از ```()d3.selection.append``` استفاده کنید تا یک DOM element جدید را ساخته و آن را به انتهای DOM element انتخاب شده استفاده کند.
 <div  dir='ltr'  align='justify'>

  ```html
<p>First paragraph</p>
<p>Second paragraph</p>

<script>
    d3.select("body").append("p");
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-7)
  </div>

  در مثال بالا ```d3.select("body")``` یک body element را برمی گرداند و ```.append("p")``` یک ```<p>``` جدید را ساخته و آن را به انتهای ```<body>``` اضافه می کند.

  شما می توانید به شکل زیر با استفاده از ```()text``` متنی را اضافه کنید.

<div  dir='ltr'  align='justify'>

  ```html
<p>First paragraph</p>
<p>Second paragraph</p>

<script>
    d3.select("body").append("p").text("Third paragraph.");
</script>>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-8)
  </div>

  در مثال بالا D3 یک ```<p>``` جدید را با متن "Third paragraph" ساخته و آن را به انتهای تگ ```<body/>``` اضافه می کند.
<br>

## insert("element name")
با استفاده از ```()d3.selection.insert``` می توانید یک element جدید راساخته و آن را انتهای element انتخاب شده اضافه کنید.
<div  dir='ltr'  align='justify'>

  ```html
<div style="border:1px solid" >
    <p>First paragraph.</p>
</div>

<script>
    d3.select("div").insert("p").text("Second paragraph.");
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-9)
  </div>

  در مثال بالا ```d3.select("div")``` آن div را انتخاب کرده سپس ```insert("p").``` یک ```<p>``` جدید را به انتهای آن اضافه می کند. ```insert("Second paragraph.")``` متن آن را تعیین می کند.

<br>

## remove()
از ```d3.selection.remove()``` برای پاک کردن DOM element های انتخاب شده می توانید استفاده کنید.

<div  dir='ltr'  align='justify'>

  ```html
<p>First paragraph</p>
<p>Second paragraph</p>

<script>
    d3.select("p").remove();
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-10)
  </div>

  در مثال بالا ```d3.select("p")``` اولین ```<p>```  را بر میگرداند و ```()remove.``` آن را پاک می کند.

<br>

## html("content")
 این متد بخش inner html را در element مشخص شده تعیین می کند.

 <div  dir='ltr'  align='justify'>

  ```html
<p>First paragraph</p>
<script>
    d3.select("p").html("<span>This is new inner html.</span>");
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-11)

  </div>

  در مثال بالا ```html(This was added in HTML ").``` عبارت inner html  را در ```<p>``` تغییر می دهد.

<br>

## attr
از این متد برای اضافه کردن attributeها به DOM elementهای مشخص شده می توانید استفاده کنید.

<div  dir='ltr'  align='justify'>

  ```html
<style>
    .error {
        color: red
    }
</style>
<body>
    <p>Error: This is dummy error.</p>
    <script>
        d3.select("p").attr("class","error");
    </script>
</body>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-12)
  </div>

  در مثال بالا ```attr("class", "error").```، باعث اضافه شدن class attribute به ```<p>``` می شود.
  
  <br>

  ## property("name", "value")
در مواردی که نمی شوداز attr استفاده کرد، می توان از این متد استفاده کرد برای اضافه کردن attribute

<div  dir='ltr'  align='justify'>

  ```html
<p>D3</label><input type="checkbox" />
<p>jQuery</label><input type="checkbox" />

<script>
    d3.select("input").property("checked",true);
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-13)
  </div>

در مثال بالا```d3.select("input")``` اولین input را مشخص کرده سپس```property("checked", true)``` مقدار آن را به true تغییر می دهد.

<br>

## style("name", "value")
از این متد می توان برای تغییر استایل یک DOM استفاده کرد.

<div  dir='ltr'  align='justify'>

  ```html
<p>Error: This is dummy error.</p>
<script>
    d3.select("p").style("color", "red")
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-14)
  </div>

  در مثال بالا ```style("color", "red")``` با اضافه شدن رنگ فونت red به ```<p>``` می شود.

<br>

## classed("css class", bool)

 با استفاده از این متد می توان class attribute ها را مشخص کرد.

<div  dir='ltr'  align='justify'>

  ```html
<style>
    .error {
        color: red
    }
</style>
<body>
    <p>This is error.</p>

    <script>
        d3.select("p").classed('error', true);
    </script>
</body>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-15)
  </div>

در مثال بالا ```classed('error', true)``` باعث اضافه شدن کلاس error به ```<p>``` می شود.
ورودی دوم بولین است که اگر true باشد باعث اضافه شدن class شده در غیر این صورت باعث حذف شدن آن می شود.

<br>
<br>

# Method Chaining

 در بخش های قبل تابع های خود را با استفاده از نقطه به هم وصل کردیم، به این کار "chain syntax" گفته می شود. اگر با JQuery آشنا باشید کد زیر برایتان آشناست:

<div  dir='ltr'  align='justify'>

  ```html

  ```
  </div>

 کتابخانه D3 از تکنیک مشابهی برای chain  کردن متد ها استفاده می کند:

<div  dir='ltr'  align='justify'>

  ```html

  ```
  </div>

 خروجی متد اول به عنوان ورودی متد بعدی وارد آن می شود.



 ما می توانسیتیم D3 code خود را به شکل زیر بنویسیم:

 <div  dir='ltr'  align='justify'>

  ```html

  ```
  </div>


 اما استفاده از method chaining کد ما را کوتاه تر و تمیز تر می کند:

<div  dir='ltr'  align='justify'>

  ```html

  ```
  </div>


 در کد بالا ```d3.select("body")``` باعث انتخاب شده body element شده و یک رفرنس از آن را برمیگرداند و به متد بعدی می دهد که ```appent()``` است.


 حال متد ```appent("p")``` رفرنس body element را دریافت کرده و یک ```p>``` element> جدید را ساخته و آن را به element اس که دریافت کرده اضافه می کند و رفرنس این element جدید را به متد بعدی می دهد.


 متد ```text("Hello World!")``` آن paragraph element را از متد قبل دریافت کرده و متن را به آن اضافه می کند.


 دقت کنید می توان chained method ها را در یک فرمت خوانا تر نوشت:

<div  dir='ltr'  align='justify'>

  ```html

  ```
  </div>




<br>
<br>
<br>
<br>### The Root Directory
 نمودار زیر ساختار یک پروژه Buffalo را نشان می دهد:

 <div  dir='ltr'  align='justify'>

  ```
├── .yarn/
├── actions/
│	├── app.go
│	└── render.go
├── assets/
├── cmd/
│	└── app/
│		└── main.go
├── config/
├── fixtures/
├── grifts/
├── models/
├── public/
├── templates/
├── .babelrc
├── .buffalo.dev.yml
├── .codeclimate.yml
├── .docketignore
├── .env
├── .gitignore
├── .pnp.loader.mjs
├── .yarnrc.yml
├── database.yml
├── Dockerfile
├── go.mod
├── go.sum
├── inflections.json
├── package.json
├── postcss.config.js
├── README.md
├── webpack.config.js
└── yarn.lock
  ```
  </div>

<br/>

### actions
در این دایرکتوری بخش Controller  طراحی MVC قرار می گیرد. این دایرکتوری شامل handler ها برای URL است. به علاوه شامل 2 فایل زیر نیز است:
-  فایل app.go که کار برپا کردن برنامه و routeها را انجام می دهد.
- فایل render.go که کار برپا کردن templage engineها را انجام می دهد.
### assets
این دایرکتوری شامل فایل های خام asset است که این فایل ها کامپایل شده و سپس به دایرکتوری public می شند که به آن خواهیم پرداخت.
(این دایرکتوری اجباری نیست برای مثال اگر می خواهیم یک API بنویسیم که فاقد frontend است، می تواند پاک شود.)
### cmd
این دایرکتوری شامل فایل main.go است که کار از ابتدا شروع کردن برنامه یا به اصطلاح bootstrap کردن آن را انجام می دهد.

### grifts
این دایرکتوری شامل task ها است که با کتابخانه grift کنترل می شوند.

(این taskها اسکریپت های کوتاهی هستند معمولا برای راه اندازی یک اپلیکیشن نیاز می شوند. کار هایی که این اسکریپت ها می کنند می تواند database seeding, پارس کردن log file باشد. Buffalo از کتابخانه grift برای آسان کردن نوشتن این اسکریپت ها استفاده می کند.)

(این دایرکتوری اجباری نیست. اگر از task ها استفاده ای نمی کنیم می تواند پاک شود.)

### models
در این دایرکتوری بخش Model از طراحی MVC قرار می گیرد. این دایرکتوری شامل فایل models.go است که وظیفه initialize کردن ارتباط با datasource را انجام می دهد.

(اگر از generator های pop/soda برای generate کردن مدل ها استفاده می کنید در این جا generate می شوند.)

  (این دایرکتوری نیز اختیاری است و اگر از database استفاده نمی کنید می تواند پاک شود.)

### public
این دایرکتوری شامل asset های کامپایل شده است و اگر از webpack استفاده می کنید، asset های خود را در اینجا قرار می دهد.

(محتوای این دایرکتوری به شکل auto-generated هستند.)  
  
  ### templates
  در این دایرکتوری بخش View در طراحی MVC قرار می گیرد. در این دایرکتوری template ها (برای مثال فایل های HTML قرار می گیرند.)

  (این دایرکتوری اجباری نیست برای مثال اگر می خواهیم یک API بنویسیم که فاقد frontend است، می تواند پاک شود.)
  
  ### tmp
  این دایرکتوری توسط دستور Buffalo dev استفاده شده و برای دوباره ساختن پروژه هنگام هر تغییر است.
  (محتوای این دایرکتوری به شکل auto-generated هستند.) 

  ### database.yml
   این دایرکتوری شامل database configuration برای soda/pop است.

   (این دایرکتوری نیز اختیاری است و اگر از database استفاده نمی کنید می تواند پاک شود.)
  
  
<br/>



  # Building an API
  در این بخش قصد داریم برای آشنایی بیشتر با Buffalo به صورت عملی، یک API ساده بنویسیم. این API کار هایی باید در طول روز انجام دهیم را دریافت کرده و آن ها را در یک database ذخیره کرده و به طور کلی یک TODO List درست می کند. در این مسیر با بخش های مختلف یک Buffalo project آشنا می شویم و نحوه ارتباط آن  با database را بررسی می کنیم و نقش Migration را متوجه می شویم.

<br/>

## Starting a Buffalo Project
شروع کردن یک Buffalo project با استفاده از دستور buffalo new انجام می شود. در این جا چون قصد داریم یک API بسازیم به آن --api را اضافه می کنیم.
حال دستور را وارد می کنیم:

<div  dir='ltr'  align='justify'>

  ```bash
  sina@sina-Zephyrus-S-GX531GS-GX531GS:~$ buffalo new project --api
DEBU[2023-06-25T00:56:12+03:30] Step: 93e62b4e
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] Exec: go mod init project
go: creating new go.mod: module project
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/README.md
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/actions/actions_test.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/actions/app.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/actions/home.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/actions/home_test.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/actions/render.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/cmd/app/main.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/.codeclimate.yml
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/.env
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/fixtures/sample.toml
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/grifts/init.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/inflections.json
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/config/buffalo-app.toml
DEBU[2023-06-25T00:56:12+03:30] Step: 84d01f8a
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/Dockerfile
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/.dockerignore
DEBU[2023-06-25T00:56:12+03:30] Step: 993376dd
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/grifts/db.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/models/models.go
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/models/models_test.go
DEBU[2023-06-25T00:56:12+03:30] Step: 4accb71e
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/database.yml
DEBU[2023-06-25T00:56:12+03:30] Step: dca0f905
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] File: /home/sina/project/.buffalo.dev.yml
DEBU[2023-06-25T00:56:12+03:30] Step: 03f3dc0d
DEBU[2023-06-25T00:56:12+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:12+03:30] Exec: go install github.com/gobuffalo/buffalo-pop/v3@latest
DEBU[2023-06-25T00:56:13+03:30] Step: a97717d1
DEBU[2023-06-25T00:56:13+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/config/buffalo-plugins.toml
DEBU[2023-06-25T00:56:13+03:30] Step: 5e64f597
DEBU[2023-06-25T00:56:13+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/actions/app.go
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/actions/home.go
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/actions/home_test.go
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/actions/render.go
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/locales/all.en-us.yaml
DEBU[2023-06-25T00:56:13+03:30] File: /home/sina/project/locales/embed.go
DEBU[2023-06-25T00:56:13+03:30] Step: 54b17c72
DEBU[2023-06-25T00:56:13+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:13+03:30] Exec: go mod tidy
go: finding module for package github.com/gobuffalo/buffalo
go: finding module for package github.com/gobuffalo/grift/grift
go: finding module for package github.com/gobuffalo/buffalo/render
go: finding module for package github.com/gobuffalo/buffalo-pop/v3/pop/popmw
go: finding module for package github.com/gobuffalo/middleware/i18n
go: finding module for package github.com/gobuffalo/middleware/paramlogger
go: finding module for package github.com/gobuffalo/middleware/forcessl
go: finding module for package github.com/rs/cors
go: finding module for package github.com/gobuffalo/middleware/contenttype
go: finding module for package github.com/gobuffalo/envy
go: finding module for package github.com/unrolled/secure
go: finding module for package github.com/gobuffalo/x/sessions
go: finding module for package github.com/gobuffalo/pop/v6
go: finding module for package github.com/gobuffalo/suite/v4
go: found github.com/gobuffalo/buffalo in github.com/gobuffalo/buffalo v1.1.0
go: found github.com/gobuffalo/buffalo-pop/v3/pop/popmw in github.com/gobuffalo/buffalo-pop/v3 v3.0.7
go: found github.com/gobuffalo/buffalo/render in github.com/gobuffalo/buffalo v1.1.0
go: found github.com/gobuffalo/envy in github.com/gobuffalo/envy v1.10.2
go: found github.com/gobuffalo/middleware/contenttype in github.com/gobuffalo/middleware v1.0.0
go: found github.com/gobuffalo/middleware/forcessl in github.com/gobuffalo/middleware v1.0.0
go: found github.com/gobuffalo/middleware/i18n in github.com/gobuffalo/middleware v1.0.0
go: found github.com/gobuffalo/middleware/paramlogger in github.com/gobuffalo/middleware v1.0.0
go: found github.com/gobuffalo/x/sessions in github.com/gobuffalo/x v0.1.0
go: found github.com/rs/cors in github.com/rs/cors v1.9.0
go: found github.com/unrolled/secure in github.com/unrolled/secure v1.13.0
go: found github.com/gobuffalo/grift/grift in github.com/gobuffalo/grift v1.5.2
go: found github.com/gobuffalo/pop/v6 in github.com/gobuffalo/pop/v6 v6.1.1
go: found github.com/gobuffalo/suite/v4 in github.com/gobuffalo/suite/v4 v4.0.4
DEBU[2023-06-25T00:56:20+03:30] Exec: go mod download
DEBU[2023-06-25T00:56:20+03:30] Step: ae497430
DEBU[2023-06-25T00:56:20+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:20+03:30] Step: fde62f00
DEBU[2023-06-25T00:56:20+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:56:20+03:30] File: /home/sina/project/.gitignore
DEBU[2023-06-25T00:56:20+03:30] Exec: git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /home/sina/project/.git/
DEBU[2023-06-25T00:56:20+03:30] Exec: git add .
DEBU[2023-06-25T00:56:20+03:30] Exec: git commit -q -m Initial Commit
INFO[2023-06-25T00:56:20+03:30] Congratulations! Your application, project, has been successfully generated!
INFO[2023-06-25T00:56:20+03:30] You can find your new application at: /home/sina/project
INFO[2023-06-25T00:56:20+03:30] Please read the README.md file in your new application for next steps on running your application.

  ```
  </div>
  اضافه کردن این flag باعث می شود ساختار پروژه ما متفاوت باشد، برای مثال بخش های مربوط به frontend در آن نباشد.
  حال با cd کردن به دایرکتوری پروژه می توانیم موارد اضافه شده را ببینیم:

<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/project_structure.png?raw=true"/></p>  

<br/>

## Database Setup
### Postgres setup
در ابتدا باید database خود را آماده کنیم. اینجا حق انتخاب بین انواع database را داریم اما من database Postgres را به دلیل آشنایی بیشتر با آن انتخاب کردم.
برای راه اندازی  Postgres از Docker استفاده می کنیم. برای این هدف،  یک Dockerfile به شکل زیر می نویسیم:
<div  dir='ltr'  align='justify'>

  ```dockerfile
FROM postgres:latest

ENV POSTGRES_USER test
ENV POSTGRES_PASSWORD test

COPY init.sql /docker-entrypoint-initdb.d/

EXPOSE 5432
  ```
  </div>
 این داکر فایل ابتدا از یک Postgres image شروع کرده و یک user به نام test در آن میسازد که Password آن نیز test است. همچنین فایل init.sql که در همان دایرکتوری قرار دارد را به این image منتقل کرده و محتویان آن اجرا می شود.
 
 
  فایل init.sql:
  <div  dir='ltr'  align='justify'>

  ```sql
CREATE DATABASE project_development;

GRANT ALL PRIVILEGES ON DATABASE project_development TO test;
  ```
  </div>
با اجرا شدن این فایل یک database به نام project_development ساخته شده و به User ما تمام دسترسی ها را در مورد این database می دهد.

حال می توانیم با استفاده از دستور Docker build، این image را بسازیم سپس آن را run کنیم:

 <div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/bufal_postgres$ docker build -t apidb .
[+] Building 0.1s (7/7) FINISHED                                                                                                                                                       
 => [internal] load .dockerignore                                                                                                                                                 0.0s
 => => transferring context: 2B                                                                                                                                                   0.0s
 => [internal] load build definition from Dockerfile                                                                                                                              0.0s
 => => transferring dockerfile: 168B                                                                                                                                              0.0s
 => [internal] load metadata for docker.io/library/postgres:latest                                                                                                                0.0s
 => [internal] load build context                                                                                                                                                 0.0s
 => => transferring context: 29B                                                                                                                                                  0.0s
 => [1/2] FROM docker.io/library/postgres:latest                                                                                                                                  0.0s
 => CACHED [2/2] COPY init.sql /docker-entrypoint-initdb.d/                                                                                                                       0.0s
 => exporting to image                                                                                                                                                            0.0s
 => => exporting layers                                                                                                                                                           0.0s
 => => writing image sha256:5728aacbb7dd52c7c8f96c46c8257b37297d9c5247ca6c07a9d411efff7293be                                                                                      0.0s
 => => naming to docker.io/library/apidb                                                                                                                                          0.0s
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/bufal_postgres$ docker run -d --name apidb -p 5432:5432 apidb
bb483f6eeaa895db1c51afe09e631afc6aa003b58421990d8707eec35180089d
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/bufal_postgres$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                       NAMES
bb483f6eeaa8   apidb     "docker-entrypoint.s…"   7 seconds ago   Up 6 seconds   0.0.0.0:5432->5432/tcp, :::5432->5432/tcp   apidb
  ```
  </div>

<br/>

  ### Configuring database.yml
  فایل database.yml را به گ.نه ای تنظیم کنیم که API ما بتواند با database ای که با کمک Docker به راه انداختیم ارتباط برقرار کند:

  <div  dir='ltr'  align='justify'>

  ```yaml
development:
  dialect: postgres
  database: project_development
  user: test
  password: test
  host: 127.0.0.1
  pool: 5

test:
  url: {{envOr "TEST_DATABASE_URL" "postgres://test:test@127.0.0.1:5432/project_test?sslmode=disable"}}

production:
  url: {{envOr "DATABASE_URL" "postgres://test:test@127.0.0.1:5432/project_production?sslmode=disable"}}
  ```
  </div>
تنظیمات database شما ممکن است متفاوت باشد بنابراین به این نکته توجه داشته باشید.

<br/>

## Migration

در این بخش با استفاده از دستورbuffalo pop generate fizz فایل های migration خود را میسازیم. با این دستور دو فایل در دایرکتوری migrations ایجاد می شود: یکی برای up migration و دیگری برای down migration به زبان ساده این فایل ها برای ایجاد تغییر در ابتدا و انتهای ارتباط با database هستند، در این جا قصد داریم در ابتدا یک table در database ساخته شود و در انتها این table پاک شود. این کار ها را به ترتیب فایل های up migration و down migration انجام می دهند.

(برای اطلاعات بیشتر درمورد database migration  می توانید به [اینجا](https://www.astera.com/type/blog/database-migration-what-it-is-and-how-it-is-done/) مراجعه کنید)

حال دستور خود را اجرا می کنیم:
  <div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/project$ buffalo pop generate fizz create_todos
pop v6.1.1

DEBU[2023-06-25T00:59:42+03:30] Step: 6908e204
DEBU[2023-06-25T00:59:42+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T00:59:42+03:30] File: /home/sina/project/migrations/20230624212942_create_todos.up.fizz
DEBU[2023-06-25T00:59:42+03:30] File: /home/sina/project/migrations/20230624212942_create_todos.down.fizz
  ```
  </div>
  فایل up migration را به شکل زیر تغییر می دهیم:
  <div  dir='ltr'  align='justify'>

  ```
  create_table("todos") {
    t.Column("id", "integer", {primary: true})
    t.Column("item", "string", {"size": 100})
  }
  ```
  </div>

  فایل down migration را به شکل زیر تغییر می دهیم:

    
 <div  dir='ltr'  align='justify'>

  ```
  drop_table("todos")
  ```
  </div>


  فایل up migration ما یک جدول می سازد و فایل down migration آن را پاک می کند.
هر گاه بخواهیم up migration  انجام دهیم از دستور زیر استفاده می کنیم:

<div  dir='ltr'  align='justify'>

  ```bash
buffalo pop migrate
  ```
  </div>

<br/>

## Creating our Model
حال که جدول خود را با استفاده از migration ساختیم، وقت آن است که مد خود را بسازیم تا بتوانیم از آن جدول استفاده کنیم و از ORM استفاده کنیم.
در ابتدا دستور زیر را وارد کنید تا فایل model ما ساخته شود:
<div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/project$ buffalo pop g model todo
pop v6.1.1

DEBU[2023-06-25T01:03:07+03:30] Step: e610c587
DEBU[2023-06-25T01:03:07+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T01:03:07+03:30] File: /home/sina/project/models/todo.go
DEBU[2023-06-25T01:03:07+03:30] File: /home/sina/project/models/todo_test.go
DEBU[2023-06-25T01:03:07+03:30] Step: 67216f4a
DEBU[2023-06-25T01:03:07+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T01:03:07+03:30] Step: ad1ce65d
DEBU[2023-06-25T01:03:07+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T01:03:07+03:30] Exec: go mod tidy
DEBU[2023-06-25T01:03:07+03:30] Step: 4b26eae8
DEBU[2023-06-25T01:03:07+03:30] Chdir: /home/sina/project
DEBU[2023-06-25T01:03:07+03:30] File: /home/sina/project/migrations/20230624213307_create_todoes.up.fizz
DEBU[2023-06-25T01:03:07+03:30] File: /home/sina/project/migrations/20230624213307_create_todoes.down.fizz

  ```
  </div>
سپس فایل ساخته شده را به شکل زیر تغییر می دهیم:



<div  dir='ltr'  align='justify'>

  ```go
package models

import (
    "encoding/json"
    "github.com/gobuffalo/pop/v5"
    "github.com/gobuffalo/validate/v3"
    "github.com/gofrs/uuid"
    "time"
)
// Todo is used by pop to map your todoes database table to your go code.
type Todo struct {
    ID int `json:"id" db:"id"`
    Item string `json:"item" db:"item"`
    CreatedAt time.Time `json:"created_at" db:"created_at"`
    UpdatedAt time.Time `json:"updated_at" db:"updated_at"`
}

// TableName overrides the table name used by Pop.
func (u Todo) TableName() string {
    return "todos"
  }

// String is not required by pop and may be deleted
func (t Todo) String() string {
    jt, _ := json.Marshal(t)
    return string(jt)
}

// Todoes is not required by pop and may be deleted
type Todos []Todo

// String is not required by pop and may be deleted
func (t Todos) String() string {
    jt, _ := json.Marshal(t)
    return string(jt)
}

// Validate gets run every time you call a "pop.Validate*" (pop.ValidateAndSave, pop.ValidateAndCreate, pop.ValidateAndUpdate) method.
// This method is not required and may be deleted.
func (t *Todo) Validate(tx *pop.Connection) (*validate.Errors, error) {
    return validate.NewErrors(), nil
}

// ValidateCreate gets run every time you call "pop.ValidateAndCreate" method.
// This method is not required and may be deleted.
func (t *Todo) ValidateCreate(tx *pop.Connection) (*validate.Errors, error) {
    return validate.NewErrors(), nil
}

// ValidateUpdate gets run every time you call "pop.ValidateAndUpdate" method.
// This method is not required and may be deleted.
func (t *Todo) ValidateUpdate(tx *pop.Connection) (*validate.Errors, error) {
    return validate.NewErrors(), nil
}

  ```
  </div>

(برای اطلاعات بیشتر درمورد ORM  می توانید به [اینجا](https://www.freecodecamp.org/news/what-is-an-orm-the-meaning-of-object-relational-mapping-database-tools/#:~:text=Object%20Relational%20Mapping%20(ORM)%20is,(OOP)%20to%20relational%20databases.) مراجعه کنید)

<br/>

## Building our Actions
حال باید تابع هایی را بنویسیم که کار Controller را در MVC انجام می دهند.
برای generate کردن فایل های آن ها از دستور زیر استفاده می کنیم:


<div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/project$ buffalo g actions todo index show add
  ```
  </div>

این دستور یک فایل todo.go را در دایرکتوری actions درست می کند که دارای تابع های TodoIndex, TodoShow و TodoAdd است.این تابع ها را به شکل زیر تغییر می دهیم:
<div  dir='ltr'  align='justify'>

  ```go
package actions

import (
    "net/http"
    "github.com/gobuffalo/buffalo"
    "project1/models"
)

// TodoIndex default implementation.
func TodoIndex(c buffalo.Context) error {
    // Create an array to receive todos
    todos := []models.Todo{}
    //get all the todos from database
    err := models.DB.All(&todos)
    // handle any error
    if err != nil {
        return c.Render(http.StatusOK, r.JSON(err))
    }
    //return list of todos as json
    return c.Render(http.StatusOK, r.JSON(todos))
}

// TodoShow default implementation.
func TodoShow(c buffalo.Context) error {
    // grab the id url parameter defined in app.go
    id := c.Param("id")
    // create a variable to receive the todo
    todo := models.Todo{}
    // grab the todo from the database
    err := models.DB.Find(&todo, id)
    // handle possible error
    if err != nil {
        return c.Render(http.StatusOK, r.JSON(err))
    }
    //return the data as json
    return c.Render(http.StatusOK, r.JSON(&todo))
}


// TodoAdd default implementation.
func TodoAdd(c buffalo.Context) error {

    //get item from url query
    item := c.Param("item")

    //create new instance of todo
    todo := models.Todo{Item: item}

    // Create a fruit without running validations
    err := models.DB.Create(&todo)

    // handle error
    if err != nil {
        return c.Render(http.StatusOK, r.JSON(err))
    }

    //return new todo as json
    return c.Render(http.StatusOK, r.JSON(todo))
}
  ```
  </div>

<br/>

## Creating the Routes
در مرحله قبل route هایی به فایل actions/app.go اضافه شدند، حال آن ها را به شکل زیر تغییر می دهیم:
<div  dir='ltr'  align='justify'>

  ```go
import (
    "project1/models"
    "github.com/gobuffalo/buffalo"
    "github.com/gobuffalo/envy"
    forcessl "github.com/gobuffalo/mw-forcessl"
    paramlogger "github.com/gobuffalo/mw-paramlogger"
    "github.com/unrolled/secure"
    "github.com/gobuffalo/buffalo-pop/v2/pop/popmw"
    contenttype "github.com/gobuffalo/mw-contenttype"
    "github.com/gobuffalo/x/sessions"
    "github.com/rs/cors"
    "github.com/gobuffalo/packr/v2"
)

// ENV is used to help switch settings based on where the
// application is being run. Default is "development".
var ENV = envy.Get("GO_ENV", "development")
var app *buffalo.App

// App is where all routes and middleware for buffalo
// should be defined. This is the nerve center of your
// application.
//
// Routing, middleware, groups, etc... are declared TOP -> DOWN.
// This means if you add a middleware to `app` *after* declaring a
// group, that group will NOT have that new middleware. The same
// is true of resource declarations as well.
//
// It also means that routes are checked in the order they are declared.
// `ServeFiles` is a CATCH-ALL route, so it should always be
// placed last in the route declarations, as it will prevent routes
// declared after it to never be called.
func App() *buffalo.App {
    if app == nil {
        app = buffalo.New(buffalo.Options{
            Env:          ENV,
            SessionStore: sessions.Null{},
            PreWares: []buffalo.PreWare{
                cors.Default().Handler,
            },
            SessionName: "_project1_session",
        })

        // Automatically redirect to SSL
        app.Use(forceSSL())

        // Log request parameters (filters apply).
        app.Use(paramlogger.ParameterLogger)

        // Set the request content type to JSON
        app.Use(contenttype.Set("application/json"))

        app.GET("/", HomeHandler)
        app.GET("/todo/", TodoIndex)
        app.GET("/todo/add", TodoAdd)
        app.GET("/todo/{id}", TodoShow) // <--- MAKE SURE THIS IS AT BOTTOM OF LIST
    }

    return app
}


// forceSSL will return a middleware that will redirect an incoming request
// if it is not HTTPS. "http://example.com" => "https://example.com".
// This middleware does **not** enable SSL. for your application. To do that
// we recommend using a proxy: https://gobuffalo.io/en/docs/proxy
// for more information: https://github.com/unrolled/secure/
func forceSSL() buffalo.MiddlewareFunc {
    return forcessl.Middleware(secure.Options{
        SSLRedirect:     ENV == "production",
        SSLProxyHeaders: map[string]string{"X-Forwarded-Proto": "https"},
    })
}
  ```
  </div>
 در واقع URL های مورد نظرا به handler های مناسب هرکدام وصل کردیم.

<br/>

 ## Testing
در ابتدا نباید فراموش کنیم که دستور مورد نظر برای up migration  را انجام بدهیم تا بتوانیم از جدول های مورد نظر در database اشتفاده کنیم:
<div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/project$ buffalo pop migrate
pop v6.1.1

[POP] 2023/06/25 01:11:00 info - > create_todoes
[POP] 2023/06/25 01:11:00 info - Successfully applied 1 migrations.
[POP] 2023/06/25 01:11:00 info - 0.0145 seconds
[POP] 2023/06/25 01:11:00 info - dumped schema for project_development
  ```
  </div>
  حال برای بالا آوردن سرور خود از دستور زیر استفاده می کنیم:
  <div  dir='ltr'  align='justify'>

  ```bash
sina@sina-Zephyrus-S-GX531GS-GX531GS:~/project$ buffalo dev
  ```
  </div>
  اکنون اگر به آدرس localhost:3000 در مرورگر خود برویم با صحنه رو به رو مواجه می شویم:
  
  <p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/welcome.png?raw=true"/></p>

تست کردن سرور ما به این گونه است:
- اگر به آدرس "localhost:3000/todo/add?item="something برویم، something به لیست todo اضافه می شود.
- اگر به آدرس /localhost:3000/todo برویم، کل لیست را می توانیم ببینیم.
- اگر به آدرس localhost:3000/todo/1 برویم، فقط ایندکس مشخص شده را می توانیم ببینیم.

برای تست کردن سرور خود ابتدا به breakfast, lunch, meeting, dinner را به لیست اضافه می کنم، سپس کل لیست را مشاهده کرده و در نهایت فقط ایندکس دوم را مشاهده می کنیم:
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/breakfast.png?raw=true"/></p>
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/lunch.png?raw=true"/></p>
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/meeting.png?raw=true"/></p>
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/dinner.png?raw=true"/></p>
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/list.png?raw=true"/></p>
<p align="center"><img src="https://github.com/Sinanmz/Web_research/blob/master/images/index_2.png?raw=true"/></p>
می توان نتیجه گرفت که سرور ما به درستی کار می کند.

<br/>

# Sources
- [gobuffalo.io](https://gobuffalo.io/)


- [dev.to](https://dev.to/alexmercedcoder/api-with-go-buffalo-in-2021-from-zero-to-deploy-5642)



</div>