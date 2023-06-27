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

## attr("name", "value")
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

  ```javascript
$("#myDiv").text("Some text").attr("style", "color:red")
  ```
  </div>

 کتابخانه D3 از تکنیک مشابهی برای chain  کردن متد ها استفاده می کند:

<div  dir='ltr'  align='justify'>

  ```javascript
d3.select("body").append("p").text("Hello World!");
  ```
  </div>

 خروجی متد اول به عنوان ورودی متد بعدی وارد آن می شود.



 ما می توانسیتیم D3 code خود را به شکل زیر بنویسیم:

 <div  dir='ltr'  align='justify'>

  ```javascript
var bodyElement = d3.select("body");

var paragraph = bodyElement.append("p");

paragraph.text("Hello World!");
  ```
  </div>


 اما استفاده از method chaining کد ما را کوتاه تر و تمیز تر می کند:

<div  dir='ltr'  align='justify'>

  ```javascript
d3.select("body").append("p").text("Hello World!");
  ```
  </div>


 در کد بالا ```d3.select("body")``` باعث انتخاب شده body element شده و یک رفرنس از آن را برمیگرداند و به متد بعدی می دهد که ```()append``` است.


 حال متد ```append("p")``` رفرنس body element را دریافت کرده و یک ```p>``` element> جدید را ساخته و آن را به element ای که دریافت کرده اضافه می کند و رفرنس این element جدید را به متد بعدی می دهد.


 متد ```text("Hello World!")``` آن paragraph element را از متد قبل دریافت کرده و متن را به آن اضافه می کند.


 دقت کنید می توان chained method ها را در یک فرمت خوانا تر نوشت:

<div  dir='ltr'  align='justify'>

  ```javascript
d3.select("body")
  .append("p")
  .text("Third paragraph");
  ```
  </div>

<br>
<br>

# Function of Data

 در قسمت DOM manipulation با تابع هایی آشنا شدیم . هر کدام از این تابع می توانند به عنوان پارامتر ورودی یک مقدار ثابت یا یک تابع بگیرند. این تابع، تابعی از دیتا است. برای مثال:

<div  dir='ltr'  align='justify'>

  ```javascript
.text(function(d) {
    return d;
});
  ```
  </div>

 در این تابع ورودی می توانیم هر منظقی برای دستکاری دیتا قرار دهیم. این ها anonymous function هستند، یعنی این تابع ها نامی ندارند.

 به غیر از پارامتر data یا (d) دو نوع پارامتر دیگر برای ما فراهم شده است:

<div  dir='ltr'  align='justify'>

  ```javascript
.text(function (d, i) {
    console.log(d); // the data element
    console.log(i); // the index element
    console.log(this); // the current DOM object

    return d;
});
  ```
  </div>


 به مثال زیر دقت کنید:

<div  dir='ltr'  align='justify'>

  ```html
<!doctype html>
<html>
<head>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <p></p>
    <p></p>
    <p></p>

    <script>
        var data = [100, 200, 300];
        var paragraph = d3.select("body")
                .selectAll("p")
                .data(data)
                .text(function (d, i) {
                    console.log("d: " + d);
                    console.log("i: " + i);
                    console.log("this: " + this);

                    return d;
                });
    </script>
</body>
</html>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-16)
  </div>

 در مثال بالا پارامتر "d" به شما data element را می دهد، "i" به شما ایندکس آن را در آرایه می دهد و ```this``` یک رفرنس به DOM element کنونی است که در اینجا یک paragraph element است.

<br>

## Dynamic Properties

همزمان با دستکاری  DOM element شاید بخواهیم ویژگی ها یا attribute های مشخصی را به آن اضافه کنیم.


تابع های دیتا برای مشخص کردن این ویژگی ها به شکل dynamic خوب هستند.

برای مثال اگر می خواهید رنگ پاراگرافتان بر اساس محتوای آن باشد می توانید آن را به صورت زیر انجام دهید:

<div  dir='ltr'  align='justify'>

  ```html
<p>Error: This is error.</p>
<p>Warning:This is warning.</p>

<script>
    d3.selectAll("p").style("color", function(d, i) {
            var text = this.innerText;
        
            if (text.indexOf("Error") >= 0) {
                return "red";
            } else if (text.indexOf("Warning") >= 0) {
                return "yellow";
            }
    });
</script>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-17)
  </div>


در مثال بالا ```d3.selectAll("p")``` همه ```<p>``` را انتخاب کرده و متد ```()style``` به آن ها color attribute بر اساس خروجی تابع دیتا اضافه می کند.

منطق این تابع به این گونه است که هرگاه در element انتخاب شده کلمات کلیدی "Error" یا "Warning" باشد، رنگ قرمز را برمی گرداند در غیر این صورت رنگ زرد را بر می گرداند.

بنابراین تابع های دیتا در D3.js بسیار مهم هستند.


<br>
<br>


# Event Handling

کتابخانه D3 مانند دیگر کتابخانه ها انواع event ها را پشتیبانی می کند. ما می توانیم با استفاده از متد ```()d3.selection.on``` هر یک از DOM element ها را به یک event listener وصل کنیم.


سینتکس آن:

<div  dir='ltr'  align='justify'>

  ```javascript
d3.selection.on(type[, listener[, capture]]);
  ```
  </div>


متد ```()on``` یک event listener  را به همه DOM element های انتخاب شده اضافه می کند. اولین پارامتر event type است مانند "click" یا "mouseover". پارامتر دوم یک تابع است که در زمان اتفاق افتادن event اجرا می شود. 


مثال زیر کنترل کردن event های mouseover یا mouseout را نشان می دهد:

<div  dir='ltr'  align='justify'>

  ```html
<!doctype html>
<html>
<head>
    <style>
        div {
            height: 100px;
            width: 100px;
            background-color: steelblue;
            margin:5px;
        }
    </style>
    <script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
<div> </div>
<script>
    d3.selectAll("div")
      .on("mouseover", function(){
          d3.select(this)
            .style("background-color", "orange");

          // Get current event info
          console.log(d3.event);
          
          // Get x & y co-ordinates
          console.log(d3.mouse(this));
      })
      .on("mouseout", function(){
          d3.select(this)
            .style("background-color", "steelblue")
      });
</script>
</body>
</html>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-18)
  </div>


در مثال بالا دو div element داریم و با استفاده از متد ```selection.on(event)``` برای همه آن ها event های mouseover و mouseout را دریافت می کنیم و تابع های event listener رابه هرکدام اضافه می کنیم. که این تابع ها style را تغییر می دهند.

برای اطلاعات بیشتر در مورد Event handling می توانید [D3 documentation](https://github.com/d3/d3-selection/blob/master/README.md#handling-events) مربوط به آن را بخوانید.

<br>
<br>


# Animation

در این بخش ساختن animation ها را با استفاده از D3 یاد می گیریم.

کتابخانه D3 پروسه ساختن animationها را با استفاده از transitionها ساده می کند. transitionها از DOM selectionها با استفاده از متد ```()selection.transition``` ساخته می شوند.


این animation ها چیزی جز transition از یک فرم به فرم دیگر نیستند. در اینجا یک animation در واقع یک transition از حالت ابتدایی به حالت انتهایی یک DOM element است.

<br>

## transtion()

متد ```()d3.selection.transition``` نشان دهنده شروع transition است و سپس تابع های transition متفاوت می توانند به elementهای انتخاب شده اعمال شوند.

مثال زیر تغییر رنگ بک گراند یک div element را با استفاده از animation ها نشان می دهد:

<div  dir='ltr'  align='justify'>

  ```html
<!doctype html>
<html>
<head>
<style>
    #container {
        height: 100px;
        width: 100px;
        background-color: black;
    }
</style>
<script src="https://d3js.org/d3.v4.min.js"></script>
</head>
<body>
    <div id="container"></div>

    <script>
        d3.select("#container")
          .transition()
          .duration(1000)
          .style("background-color", "red");
    </script>
</body>
</html>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-19)
  </div>

در مثال بالا از تابع ```()transition``` برای ایجاد یک transition استفاده می کنیم که رنگ container' element' را از مشکی به قرمز تغییر می دهد. سپس تابع ```()duration``` را فراخواندیم تا مدت این تغییر را مشخص کنیم.


شما همچنین می توانید یک transition را ساخته و آن را در یک متغیر قرار داده سپس از آن برای اضافه کردن animation  به element های مختلف استفاده کنید.

<div  dir='ltr'  align='justify'>

  ```javascript
var t = d3.transition()
        .duration(500)

    d3.select("#container")
      .transition(t)
      .style("background-color", "red");
  ```
  </div>

<br>

## transition.ease()

تابع ```ease()``` برای مشخص و کنترل کردن جنبش یک transition استفاده می شود.

برای اطلاع از تابع های متفاوت ease می توانید به [اینجا](https://bl.ocks.org/d3noob/1ea51d03775b9650e8dfd03474e202fe) مراجه کنید.

<br>

## transition.delay()

تابع ```()delay``` مدت تاخیر را برای هر کدام از elementهایی که transition روی آن ها اعمال می شود را تعیین می کند. آن transition بعد از مدت مشخص شده شروع می شود.


در مثال زیر دو bar را animate می کنیم. اول، ارتفاع bar اول را از 20px به 100px تغییر می دهیم. سپس با تاخیر 2000 میلی ثانیه برای bar  دوم همین کار را انجام می دهیم.

<div  dir='ltr'  align='justify'>

  ```html
<body>
<script>
    var svg = d3.select("body")
        .append("svg")
        .attr("width", 500)
        .attr("height", 500);


    var bar1 = svg.append("rect")
        .attr("fill", "blue")
        .attr("x", 100)
        .attr("y", 20)
        .attr("height", 20)
        .attr("width", 10)

    var bar2 = svg.append("rect")
        .attr("fill", "blue")
        .attr("x", 120)
        .attr("y", 20)
        .attr("height", 20)
        .attr("width", 10)

    update();

function update() {
    bar1.transition()
        .ease(d3.easeLinear)
        .duration(2000)
        .attr("height",100)

    bar2.transition()
        .ease(d3.easeLinear)
        .duration(2000)
        .delay(2000)
        .attr("height",100)
}
</script>
</body>
  ```
  [امتحان کردن کد](https://www.tutorialsteacher.com/codeeditor?cid=d3-20)
  
  </div>

در کد بالا ابتدا دو مستطیل را به SVG اضافه کردیم. bar اول در مکان [20, 100] قرار گرفته و bar دوم در مکان [20, 120] قرار می گیرد که هر دو دارای ارتفاع 20px و عرض 10px هستند.

در تابع update ابتدا bar اول را با استفاده از linear ease ارتفاعش را به 100px افزایش می دهیم و مدت این animation را برابر با 2000ms قرار می دهیم. همین کار را برای bar دوم هم انجام می دهیم اما این بار با 2000ms تاخیر.

می توانید transition function های فراهم شده در D3 را در [D3 API Documentation](https://github.com/d3/d3/blob/master/API.md#transitions-d3-transition) ببینید.



