# CS110
Lab1
Due Wednesday by 11pm Points 100 Submitting an external tool
Browsers: Unfortunately, Web browsers are still not 100% identical in their behavior, so Web pages may behave differently on different browsers. For this class, the reference browser is Chrome: your project solutions must work on Chrome, and the CAs will use Chrome to test them. Your solutions need not work on any browser other than Chrome. You may use a different browser to develop your solution if you wish (Chrome, Firefox, and Safari all have very similar behavior), but please test on Chrome before submitting. We do not recommend that you use Internet Explorer for development: historically, its behavior has been quite different from the other browsers, so things that work on IE may not work on Chrome, and vice versa

Editors:  We recommend that you use VSCode (Links to an external site.) (as the editor for HTML, CSS, and JS).

 The following are a list of VSCode extensions that might be helpful:

HTML CSS Support (Links to an external site.): CSS Support for HTML Documents
HTMLHint (Links to an external site.) : Integrates the HTMLHint (Links to an external site.) static analysis tool into Visual Studio Code.
vscode-stylelint (Links to an external site.) : A Visual Studio Code extension to lint CSS/SCSS/Less with stylelint. Follows Getting Started Guide (Links to an external site.) to set up stylelint for your project.
Markdownlint (Links to an external site.): Markdown/CommonMark linting and style checking for Visual Studio Code
ESLint (Links to an external site.): Javascript linting
Live Share Extension Pack (Links to an external site.): Collaboratively edit and debug with others in real time
Code Spell Checker (Links to an external site.): Spelling Checker for Visual Studio Code
A note on Collaboration
Collaboration is encouraged for this particular lab. You will be assigned a team via Breakout Rooms on Zoom. While To collaboratively work on the lab together, one team member should share their screen and invite the other users to edit the files using the Live Share extension on VSCode. With Live Share, you can all work on different files but still be editing the code on a single member's machine. We encourage you to take turns coding and advising each other as you pair-program. Instructions for starting a Live Share session are below:

Click the Live Share button
Live share screenshot


Sign in with Github
After signing in and granting access to your account, the invitation link to your Live Share session should be copied to your clipboard. Share this link with your group members.
Tutorial

Go through the HTML & CSS review:

Lab1 - Intro to HTML & CSS 
Lab 1 - Bootstrap 
Lab Instructions

Complete the following lab assignment. You can get the starter code here. download

For this assignment, we want you to use HTML and CSS to create a static web page based off of Twitter (Links to an external site.) as below. Note, we know it might be hard to get the page to look exactly like sown below, but try your hardest to follow the template. Any images you'll need can be found in the /images folder, which can be referenced as ./images (when CSS is in its own file, URLs are relative to the CSS file, not the page it is loaded on). All of your HTML should go in the index.html file and all of your CSS should go in the index.css file.

twitter-overview-1.png    

This site should also be responsive. When the browser window is thin enough, the ‘Who to follow’ section should disappear. 

twitter-overview-narrowed-2.png  

Feel free to go on Twitter and use your browser’s inspect element to see how they do font sizes, font weights, margins, paddings, text colors, and background colors (use inspector). Our solution is a bit different than Twitter’s architecture because twitter’s HTML/CSS setup is way too complicated for a simple web mockup. If you try to copy Twitter’s code instead of creating the HTML elements yourself, you’ll end up spending way more time trying to figure out what each div does and how to decipher their massive styling code base.

Usability Requirements
In addition to the functionality requirements listed below, we want you to make your interface screen reader friendly, so that more users can enjoy your Twitter! Here’s what we’re asking you to do and why:

A screen reader needs to know in advance what language your website is in in order to function properly.

To help it out, make sure to declare the language of your website in the lang= attribute of the html tag.

Blind and low-sighted users often can’t see images on a site.

To help them enjoy your site’s content, all images must have alt text.
The alt text goes in the alt="..." attribute of the image element.
You should give a basic description of what is in the image. Putting image in the alt attribute does not count!
 

Blind or low-sighted users may want to “skim through” a page using their screen reader. To make that easier, the page should have a logical hierarchy using different headings to designate different levels of importance.

Note: your Twitter page won’t have that many headings. Just don’t use headings to style things!

If you want a piece of text that isn’t a heading to be big or bold, use HTML elements like em and b tag or CSS to style it rather than the heading attribute.

For people using screen readers to navigate the page, ARIA landmarks are a big help – they can help users skim the page, or to quickly find the content they need. These are attributes that can be added to any element on the page and appear as role= attributes within a div’s opening tag. The ARIA landmarks you are required to include are:

role=navigation (to designate the navigation menu): add this to the navigation bar.
role=main (main page content, i.e. the tweets): add this to the div you use to contain your tweets.
Look here (Links to an external site.) for more tips and examples.

Finally, your page should have a skip link (think <a> !) somewhere at the top of the navigation. Skip links are links at the top of the page which allow a user to skip to the main content of the page. They’re important for older browsers and screen readers that may not support ARIA landmark navigation.

This can be styled any way you like! However, for this project, hide them using display: none;.
To do this, you’ll have to give the div you will be jumping to an ID, and have the link href="..." attribute point to that div’s ID. For example, if I wanted to jump to a div with the ID myDiv, I would have the following link: <a href=”#myDiv”>Jump to myDiv</a>
In our case, this means skipping to content-wrapper or content-center, depending on your implementation. More tips and examples can be found here (Links to an external site.).
We recommend (not required) running your page through WAVE’s accessibility checker, which can be added to the Chrome browser. For help, take a look at our Accessibility Resource Sheet (Links to an external site.) in Docs

Functionality Requirements
In the following, we put together some hints on how to accomplish the functionality requirements. We also encourage you to refer to online resources like CSSTricks for HTML and CSS properties.

twitter-parts.png  

This web page contains five parts:

header
Twitter's header is fixed which means when you scroll down, the header remains at the top of the webpage. We will require you to implement your header in a similar manner. To do this, use:

position: fixed; Adding this to an element makes it stick to whatever position you specify
top: 0; left: 0; These are the positions for the fixed element that will keep the element fixed at the top
z-index: 100; Adding this to an element makes it positioned above other elements (You could probably make it work with z-index: 5, but we put 100 just to make sure). Elements without a specified z-index have a default z-index of 0. Elements with higher z-indexes are placed over elements with lower z-indexes.
If you decide to use Bootstrap, you may find Navbar Placement (Links to an external site.) to be useful.

We will also require you to style the navigation buttons so that they change font color and become underlined when you hover over them. Like this:
Twitter how Navbar Link looks like
You can use .yourCssClass:hover {...} to specify the style on hover. Note :hover is appended to the CSS selector, in fact, hover is one of the pseudo-class (Links to an external site.), targeting particular elements at certain state.

Lastly, we require you to have the Twitter logo stay in the middle of the header when you resize the window.

If you have trouble making the Twitter logo stay in the middle, you can turn your nav links into icons at smaller screen sizes.
Here are a set of FontAwesome icons for you to use, after including the FontAwesome script

<script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/js/all.min.js" integrity="sha256-qM7QTJSlvtPSxVRjVWNM2OfTAz/3k5ovHOKmKXuYMO4=" crossorigin="anonymous"></script>
Home  <i class="fas fa-home"></i>
Moments  <i class="fas fa-hashtag"></i>
Notifications  <i class="far fa-bell"></i>
Messages  <i class="far fa-envelope"></i>
 

The file path of the twitter logo is ./images/twitter-logo.png

content-wrapper
We require you to have all the content below the header within a boundary that is centered on the screen. To do this, we recommend creating a wrapper div for the three columns below the header. Use these styles on the wrapper div:

max-width: 1190px; This sets the maximum width of the element.
margin: 56px auto; This sets the vertical margins to 56px so that it is below the header and the horizontal margins to automatically center the element.
 

content-left
In our solution, content-left is made up of 3 rows (divs): How the left content will look like

Cover picture (purple)
Profile picture (orange)
Profile stats (green)
 

We require you to create the overlapping effect between the profile picture and cover picture. Usually to specify priority in stacked display (think it as layers), you will use z-index (Links to an external site.) .

There are multiple ways to create overlapping effect, absolute positioning the cover picture is one way to do it. After configuring the z-index properly. You can use:

position: absolute; With this you can specify the exact coordinates of an element. This is different than position: fixed; in that an absolutely positioned element will not stick to its position on the screen when you scroll.
Bootstrap section for positioning (Links to an external site.)

The filepath of the cover picture is ./images/ratatouille-banner.png while ./images/ratatouille.jpg is the filepath of the profile picture for Remy and ./images/linguini.png is the filepath of Linguini's profile picture.
 

content-center
How the center content will look like
We require that you include the profile picture in every one of the tweets. Additionally, in at least one of the tweets you should have a span tag to change the styling of a single word within the tweet.

border-radius: 50%; or Bootstrap class rounded-circle makes an element a circle.

content-right
If you minimize the width of your browser when on Twitter, you will notice that the content on the right disappears at a certain point. This is done using CSS media queries.

We require you to do the same on your mockup. So, use a media query to make content-right disappear when the window’s width is less than or equal to 1200px.

Other than the explicitly stated requirements for this part, we would like you to make your Twitter mockup generally resemble the solution provided above

If you can, please make your webpage compliant across browsers. But we will be testing your assignment on Chrome.

Note: Don't worry about getting the font sizes or font colors exact. That being said, #4AB3F4 is the blue color used in the mockup and #E6ECF0 is the light gray background color.

 

General Notes

As a reminder, it's a good idea to run your HTML and CSS syntax through validators. You should also consider using an accessibility checker such as WAVE.

Troubleshooting

There are hundreds of HTML and CSS tags, properties, and values, and we do not expect students to learn each one by heart. If you’re having problems, there are many guides on HTML and CSS online (CSSTricks and MDN are your friends).

As a general rule of thumb, do not expect TAs to be able to solve every web problem you have. Even the most adept web developer can struggle a lot with specific CSS rules to use.

Submission

Hand-in all your files (upload the directory containing your files) to Gradescope. Each person must submit the lab to receive points. Be sure to include your name and your partner's name on each file submission. 
