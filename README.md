# 소개

안녕하세요 웹 개발자 박민지입니다.
2020/04 ~ 2020/09 [NCS]디지털컨버전스 융합 응용SW 개발자 양성 과정을 수료하였으며,
ORACLE, JAVA, Servlet, JSP, JDBC, Spring Framework, Mybatis, Ajax, HTML, CSS, JavaScript 등을 이용하고 활용하여 웹페이지를 제작할 수 있습니다.
API를 연구하고 새로운 것에 흥미가 높아 적응력이 빠릅니다.

포트폴리오는 여기에서 봐주세요. [Portfolio](https://parkminji-m63mini.github.io/parkminji_m63mini.github.io/).

## 프로젝트

SODA(소비를 생각하다)
사용자에게 자신과 비슷한 사람들의 소비패턴을 그래프로 함께 보여주고 비교함으로써 자신의 소비습관을 돌아보고, 여러 카테고리의 커뮤니티를 통해 정보를 얻을 수 있는 웹페이지.


- 소비분석 그래프 : 사용자의 소비를 나이대, 성별, 직업별로 다양하게 비교하여줌으로써 한눈에 소비현황을 알아볼 수 있다. [API : chart.js]
<p align="center">
    <img src="https://user-images.githubusercontent.com/68366848/95024356-7ff0b880-06bd-11eb-940e-466c4c23367d.PNG" />
</p>

```HTML
    <!--1-2 회원 성별 지출 금액 비교 카테고리별로 꺽은선 그래프 2개 (회원, 평균)  -->                                      
      <div class="containera" >
	  <canvas class="graph" id="myChart2" width="400px" height="300px"></canvas> 
	  <p class="text-p">회원 카테고리별 평균 지출 금액(당월)</p>
	    <p id="btn"> <button id="userBtn2"  type="button" class="btn btn-success textBtn">회원</button>
		<button type="button" id="usersBtn"class="btn btn-success textBtn">회원평균</button>
	    </p>
     </div>
                
                 
   <script> 
					 
            // chart colors 
            const colors2 = ['rgb(2, 155, 111)','rgb(245, 242, 161)','rgb(57, 90, 206)','#c3e6cb','#dc3545','#6c757d'];
            var ctx2 = document.getElementById('myChart2'); 
            var chartData2 = { labels: ["식비", "교통비", "통신비",  "기타지출", "저축"], 
          		  
	   //파란선 회원
            datasets: [{ data: [<%=graph12_user.getEat()%> ,<%=graph12_user.getTrans()%> ,<%=graph12_user.getPhone()%> ,
				<%=graph12_user.getEtc()%> ,<%=graph12_user.getSaving()%>], 
            backgroundColor: 'transparent', 
            borderColor: colors2[2], 
            borderWidth: 3, 
            pointBackgroundColor: colors2[0] },
			
             //빨간선
              { data: [<%=graph12_users.getEat()%> ,<%=graph12_users.getTrans()%> ,<%=graph12_users.getPhone()%> ,
			<%=graph12_users.getEtc()%> ,<%=graph12_users.getSaving()%>  	  ], 
              backgroundColor: colors2[1], 
              borderColor: colors2[0], 
              borderWidth: 3,
               pointBackgroundColor: colors2[0] } ] }; 
          
          	var myChart2 = new Chart(ctx2, { 
						      // 챠트 종류를 선택 
						      type: 'line', 
						      // 챠트를 그릴 데이타 
						      data: chartData2, 
						      // 옵션 
						      options: { responsive: false,
								  legend: { display: false } } });

            </script> 
```


<p align="center">
<img src="https://user-images.githubusercontent.com/68366848/95024638-5042b000-06bf-11eb-84e9-911324fa9dfc.png" style="width: 600px;"/>
</p>
- 캡쳐화면 - 코드

- 꿀팁게시판 : 카테고리별로 나누어 글이 작성가능하며 조회도 가능하다. 댓글형식으로 사용되는 게시판
- 캡쳐화면 - 코드

- 관리자 : 사용자의 탈퇴, 정보를 관리하고 게시판의 게시글을 한눈에 관리할 수 있다.
- 캡쳐화면 - 코드

AM(alba management) 
아르바이트생으로만 구성되어있는 소규모 사업자를 위한 인사관리 시스템. 알바생의 인사관리와 스케줄, 급여관리를 빠르고 편리하게 관리 조회가 가능한 그룹웨어 기반 웹페이지.

- 스케쥴 : 사용자의 스케쥴을 한눈에 확인 가능하며, 알바생의 스케쥴을 입력, 수정, 삭제가 가능하다. [API : FullCalrendar]
- 캡쳐화면 - 코드(입력, 수정, 삭제)

- 파트타임 : 사용자가 편리한 스케쥴 입력을 위해 지정한 임의의 시간과 별명. 스케쥴에 사용되거나 조회에 사용된다.
- 캡쳐화면 - 코드(입력, 수정, 삭제)

- 관리자 : 회원의 인증, 정보확인등의 관리기능을 가지고 있다.
- 캡쳐화면 - 코드

## Contents

- [Setup and Configuration](#setup-and-configuration)
    - [Making Edits / Customizing the Template](#making-edits--customizing-the-template)
    - [Using the Template As Is](#using-the-template-as-is)
- [Customization and Editing](#customization-and-editing)
    - [General](#general)
    - [Images](#images)
    - [Header Section](#header-section)
    - [Lead Section](#lead-section)
    - [About Section](#about-section)
    - [Experience Section](#experience-section)
    - [Education Section](#education-section)
    - [Projects Section](#projects-section)
    - [Skills Section](#skills-section)
    - [Contact Section](#contact-section)
    - [Footer Section](#footer-section)
    - [Optional Sections](#optional-sections)
- [Changelog](#changelog)
- [License](#license)

## Setup and Configuration

The setup required can be broken into two types:
1. If you want to make edits or customize the template
2. If you just want to add your information as use as is

### Making Edits / Customizing the Template

To setup, simply fork the repo and run `npm install` in order to get all the Gulp dev dependencies. Next, run `Gulp watch` to compile the Sass and minify the JavaScript. Alternatively, if you don't have Gulp installed globally, you can run the npm script `npm run watch`. Any changes done to the JavaScript (js/scripts.js) or Sass (sass/styles.scss) will be autocompiled and ready to go.

All scripts are within `js/scripts.js` and get minified to `js/scripts.min.js`. All styles are in `sass/styles.scss` and get compiled to `css/styles.css`. Both the minified scripts file and compiled CSS file are what is loaded on the page by default.

At this point, the page is ready to go and you can begin to add your own information and make any needed changes. The sections below  contains a quick breakdown of each of the default sections and how they work.

### Using The Template As Is

If you wish to use the template as is (i.e. how it's seen in the demo), then all that's required is the `css`, `images`, `js`, `libs` folders and the `index.html` file. You would then add your content to `index.html` as needed and you're good to go!

## Customization and Editing

### General

In general, most styles on the page are based off the definitions of variables in the variable section of the style sheet:

```SCSS
// Define base and accent colors
$base-color: #3498db;
$base-color-hover: darken($base-color, 10%);

// Define background colors
$background: #fff;
$background-alt: #f2f2f5;

// Define border colors
$border: #dcd9d9;

// Define text colors
$heading: #374054;
$text: #74808a;
```

If you wish to change the general colour scheme of the page for example, simply change the value of `$base-color`.

There is also a number of default CSS classes that can be applied such as `.shadow`, `.shadow-large`, `.btn-rounded-white`, and various others. These can be found under the General Styles section in the style sheet.

### Images

By default, the template comes with a number of images, some of which can be kept and others which act simply as placeholders and should be switched. The template contains the following:

* Main background (images/lead-bg.jpg) - this is the main background image provided via [Unsplash](https://unsplash.com/). This can be kept or changed easily by replacing `images/lead-bg.jpg` with your new background (recommended size of at least 1920x1080).
* Favicon (/favicon.ico) - this is the favicon used for the page. Similar to the main bg, this can kept or changed easily by replacing the `favicon.ico` with your new one.
* Project image - these are the images associated with the projects under the project section. These are simply placeholders and should either be replaced or removed.

### Header Section

The header section can be found within the `<header>` tag and simply contains an unordered list of anchors to different sections of the page. If you add a new section and want to be able to quickly navigate to it from the top, simply add another list element with an anchor that has the href of the ID of the section. Conversely, if you remove a section, don't forget to remove the associated navigation element.

If you wish to add a header link to an external page, simply add the class `no-scroll` to the anchor. For example:

```HTML
<li>
    <a href="https://google.com" class="no-scroll">Google</a>
</li>
```

If you wish to have a sticky (fixed) header, you simply need to add a class of `sticky` to the main header. For example, that would be accomplished as follows:

```HTML
<header class="sticky">
    <!-- Header content -->
</header>
```

### Lead Section

The Lead section is pretty straightforward, it contains an h1 for your name and an h2 for your title. It also contains a link that can be used to link to your resume should you wish to add it as well.

If you want your resume to automatically download when the button is clicked instead of opening up in another tab (the default behaviour), add the following code (Thanks to jkfran for the suggestion) in the lead:

```HTML
<a href="path/to/resume.pdf" download="resume.pdf" class="btn-rounded-white">Download Resume</a>
```

The href attribute points to where your resume is stored and the download attribute is what triggers the download / provides the name the file will be downloaded as when the user clicks the button (In this case, it will download as resume.pdf).

### About Section

The about section contains a quick about blurb that can be edited by changing the text within the paragraph tags.

### Experience Section

The experience section creates a vertical timeline with all your relevant experience. The code for the timeline creation can be found within `js/scripts.js` and is an adaptaion of [RyanFitzgerald/vertical-timeline](https://github.com/RyanFitzgerald/vertical-timeline).

The default format is as follows:

```HTML
<div id="experience-timeline">
    <div data-date="September 2015 – September 2016">
        <h3>Employer Name</h3>
        <h4>Job Title</h4>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex.
        </p>
    </div>
</div>
```

The data attribute `data-date` is what is used to add a date to the associated timeline point. All that is really required is a wrapping div (i.e. `#experience-timeline`) and nested divs to build the timeline. The h3, h4, and p tags are optional and the contents of the div can be styled however you wish.

To add additional section, simply add additional nested divs under the main wrapping div.

### Education Section

The Education is just a series of `.education-block` classes with some details associated with them. By default, it shows school name, date, degree, and some additional details. For example:

```HTML
<div class="education-block">
    <h3>University of Ottawa</h3>
    <span class="education-date">Sept 2016 - Sept 2017</span>
    <h4>Bachelor of Science in Computer Science</h4>
    <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex.
    </p>
</div>
```

To add additional section, simply add additional `.education-block` elements.

### Projects Section

The Project section contains a number of `.project` elements that represent each of your projects. By default, it contains a 300x300 image under `.project-image` and relevant project information under `.project-info`. An example is as follows:

```HTML
<div class="project">
    <div class="project-image">
        <img src="images/project.jpg" />
    </div>
    <!-- End .project-image -->

    <div class="project-info">
        <h3>Project Name Here</h3>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex.
        </p>
        <a href="#">View Project</a>
    </div>
    <!-- End .project-info -->
</div>
```

If you want to hide some projects by default, you can throw them in an additional row and add the markup for the "Show More" button. This would be done as follows:

```HTML
<!-- Projects Above -->

<a id="view-more-projects" href="#">View More Projects</a>
<div id="more-projects" class="row">
    <div class="project shadow-large">
        <div class="project-image">
            <img src="images/project.jpg" />
        </div>
        <!-- End .project-image -->
        <div class="project-info">
            <h3>Project Name Here</h3>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex. Etiam volutpat laoreet urna. Morbi ut tortor nec nulla commodo malesuada sit amet vel lacus. Fusce eget efficitur libero. Morbi dapibus porta quam laoreet placerat.
            </p>
            <a href="#">View Project</a>
        </div>
        <!-- End .project-info -->
    </div>
    <!-- End .project -->
</div>
```

This will add a link that says "View More Projects" under the current projects and when clicked, all projects in the "More-projects" div will be shown. This is optional functionality and isn't provided by default. It is important that you keep the wrapping div ID intact ("#more-projects") as well as the anchor ID ("#view-more-projects"), however the contents of the div and the anchor text itself can be edited however you like.

#### Projects without images

If you do not wish to have a project image associated with a project, you can simply add `no-image` as an additional class to the project. It would look like the following:

```HTML
<div class="project no-image">
    <div class="project-info">
        <h3>Project Name Here</h3>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex.
        </p>
        <a href="#">View Project</a>
    </div>
    <!-- End .project-info -->
</div>
```

### Skills Section

The Skills section is simply an unordered list that spits out a "Skill Cloud" with all the skills listed. To add / remove skills, simply edit or add list elements, like so:

```HTML
<ul>
    <li>JavaScript</li>
    <li>Python</li>
    <li>Ruby</li>
    <li>Go</li>
    <li>Node.js</li>
</ul>
```

### Contact Section

Since the page is static, I opted to use the awesome Formspree to allow for a contact form without the need for anything else. To use it, you must have the page hosted on a server (loading a basic HTML page won't work) where a referrer header is generated. Also, simply add the email to the action. An example is as follows:

```HTML
<form method="POST" action="https://formspree.io/email@email.com">
    <input type="hidden" name="_subject" value="Contact request from personal website" />
    <input type="email" name="_replyto" placeholder="Your email" required>
    <textarea name="message" placeholder="Your message" required></textarea>
    <button type="submit">Send</button>
</form>
```
For more information on configuration of the contact form or dealing with errors, check out [Formspree](https://formspree.io/).

For a quick tutorial about formspree, check out this [tutsplus tutorial](https://webdesign.tutsplus.com/tutorials/quick-tip-add-a-formspree-form-to-your-static-sites--cms-23870) that covers different aspects and features of the form tool.

### Footer Section

The Footer contains an optional copyright where you can place your name as well as an unordered list of all of your social or coding related profiles. By default it contains Github, Stack Overflow, Facebook, Twitter, and Google Plus. You can add or remove them easily and simply use the Font Awesome icon associated with the social profile you wish to use. For a list of all icons, [click here](http://fontawesome.io/icons/).

### Optional Sections

The template comes with an optional section that can be added to the page markup to list things like Certifications, Hobbies, and more (Note: these are not included by default). The markup for the additional optional section is as follows:

```HTML
<div class="optional-section background-alt">
    <h2 class="heading">Section Name</h2>

    <div class="optional-section-block">
        <h3>Some content title</h3>
        <p>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur in iaculis ex. Etiam volutpat laoreet urna. Morbi ut tortor nec nulla commodo malesuada sit amet vel lacus. Fusce eget efficitur libero. Morbi dapibus porta quam laoreet placerat.
        </p>
        <ul>
            <li>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </li>
            <li>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </li>
            <li>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </li>
        </ul>
    </div>
    <!-- End .optional-section-block -->

</div>
<!-- End .optional-section -->
```

You can copy .optional-section-block for each new item you wish you have in the optional section. Also, the background-alt class may need to be removed depending on where the optional section is placed in your layout as this adds the grey background. If you play it at the bottom after "Skills", it can be used as is. Also, by default the border is applied at the top, but this can also be adjusted as needed.

The optional section blocks have styling for h3 (the block title), h4, p, and ul tags by default.

## Changelog

### 1.2.2

* Updated dependencies and gulpfile

### 1.2.1

* Updated dependencies and gulpfile
* Added `no-image` optional class for projects without images (see above for usage)

### 1.2.0

* Added support for optional "Show More Projects" that hides some projects by default if included
* Added optional sections to display certifications, languages, etc.

### 1.1.3

* Added default favicon to be used or changed
* Added `sticky` class to make header fixed
* Updated docs to add image section

### 1.1.2

* Added `no-scroll` class option to header navigation anchor if you want to link to external site
* Changed contact form input / textarea colours to be based off `$base-color`
* Changed main background to 100vh so it doesn't overflow if viewport height < 700px

### 1.1.1

* Made input placeholder text more readable
* Removed timeline line when no JS
* Added some basic styling to timeline when no JS

### 1.1.0

* Fixed menu toggle on mobile devices
* Fixed z-index / scrolling issue with mobile menu
* Mobile menu now closes once a nav element is hit

## License

Completely free (MIT)! See [LICENSE.md](LICENSE.md) for more.
