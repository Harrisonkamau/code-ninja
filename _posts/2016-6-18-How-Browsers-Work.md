---
layout: post
title: How Browsers Work
---
<h1>How Browsers Work</h1>
<h2>Introduction</h2>
<p>Web browsers are the most widely used software today.</p>
<p>There are five major browsers used on desktop today:
		<ul>
		<li>Chrome</li>
		<li>Internet Explorer</li>
		<li>Firefox</li>
		<li>Safari</li>
		<li>Opera</li>
		</ul></p>
	<h3>Summary</h3>(http://ptgmedia.pearsoncmg.com/images/9780789736260/samplechapter/0789736268%5FSample%5FChapter%5F18.pdf)
	<p>
	Like much of the Internet, the World Wide Web operates on a client/server model. You run a web
	client on your computer—called a web browser—such as Microsoft’s Internet Explorer or Firefox. That
	client contacts a web server and requests information or resources. The web server locates and then sends
	the information to the web browser, which displays the results.
</p>
<p>
	When web browsers contact servers, they’re asking to be sent pages built with Hypertext Markup
	Language (HTML). Browsers interpret those pages and display them on your computer. They also can dis-
	play applications, programs, animations, and similar material created with programming languages such as
	Java and ActiveX, scripting languages such as JavaScript, and techniques such as AJAX.
	Sometimes, home pages contain links to files the web browser can’t play or display, such as sound or ani-
	mation files. In that case, you need a plug-in or a helper application. You configure your web browser or
	operating system to use the helper application or plug-in whenever it encounters a sound, animation, or
	other type of file the browser can’t run or play.
</p>

<p>
	Over the years, web browsers have become increasingly sophisticated. Browsers are now full-blown soft-
	ware suites that can do everything from videoconferencing to letting you create and publish HTML pages.
	Browsers now also blur the line between your local computer and the Internet—in essence, they can make
	your computer and the Internet function as a single computer system.
</p>

<h2>Browser's Functionality</h2>(http://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)
<p>The main function of a browser is to present the web resource you choose, by requesting it from the server and displaying it in the browser window. The resource is usually an HTML document, but may also be a PDF, image, or some other type of content. The location of the resource is specified by the user using a URI (Uniform Resource Identifier).</p>
<p>The way the browser interprets and displays HTML files is specified in the HTML and CSS specifications. These specifications are maintained by the W3C (World Wide Web Consortium) organization, which is the standards organization for the web. </p>

<h2>Browser's main components</h2>
<ol>
	<li><em><strong>User Interface</strong></em>
	<p>Includes the address bar, back/forward button, bookmarking menu, etc. Every part of the browser display except the window where you see the requested page.</p></li>
	<li><em><strong>Browser Engine</strong></em>
	<p>Marshals actions between the UI and the rendering engine.</p></li>
	<li><em><strong>The Rendering Engine</strong></em>
	<p>Responsible for displaying requested content. For example if the requested content is HTML, the rendering engine parses HTML and CSS, and displays the parsed content on the screen.</p></li>
	<li><em><strong>Networking</strong></em>
	<p>For network calls such as HTTP requests, using different implementations for different platform behind a platform-independent interface.</p></li>
	<li><em><strong>UI Backend</strong></em>
	<p>Used for drawing basic widgets like combo boxes and windows. This backend exposes a generic interface that is not platform specific. Underneath it uses operating system user interface methods.</p></li>
	<li><em><strong>JavaScript Interpreter</strong></em>
	<p>Used to parse and execute JavaScript code.</p></li>
	<li><em><strong>Data Storage</strong></em>
	<p>This is a persistence layer. The browser may need to save all sorts of data locally, such as cookies. Browsers also support storage mechanisms such as localStorage, IndexedDB, WebSQL and FileSystem.</p></li>
</ol>
<p>The two main modules in any browser are The rendering engine also known as layout engine and JavaScript Interpreter</p>

<h2>Components of a web page</h2>(https://docs.google.com/presentation/d/1kjC_L5C-E2Y_wOVkblJxRr6GBgw1V_FBbFI4jAoh688/edit#slide=id.gc563c71b0_1_35)
	<ul>
		<li>HTML: The main component of the page/application</li>
		<li>CSS:The style of the content</li>
		<li>JavaScript: The logic of the application,sometimes also for animations, etc.</li>
	</ul>

<h2>Steps involved to render a webpage on a browser</h2>(https://varvy.com/pagespeed/display.html)
	<ul>
		<li>A request is made when a link is clicked. </li>
		<li>The page and its resources (files) are downloaded. </li>
		<li>The web browser uses the page resources to build the page. </li>
		<li>The page then is rendered (displayed) to the user. </li>
	</ul>

<h2>The Rendering Engine</h2>
<p>This program that renders marked up content (such as HTML, XML, image files, etc.) and formatting information (such as CSS, XSL, etc.).</p>
<p>This is done roughly in four phases:
	<ol>
		<li>Process the HTML to build the DOM,process the CSS to build the CSSOM</li>
		<li>Combine DOM and CSSOM together into a render tree</li>
		<li>Layout the render tree (computing geometries)</li>
		<li>Paint the render tree on the screen</li>
	</ol></p>
<h2>Phase 1: <h3>Parsing the HTML and CSS</h3></h2>
<p>In this phase, the engine will start the parsing of the HTML.</p>
<p>The output will be a tree called Document Object Model (DOM) or content tree,
where each HTML tag is represented by a node of the tree (DOM node).</p>
<p>The mapping between HTML tags and DOM nodes is not 1:1 but almost.
The root element of the tree is the <html> element.</p>
<p>The purpose of the DOM is at least dual:
<ul>
	<li>as an input tree for the next phases (to build the render tree)</li>
	<li>as an interface to connect the web page to scripts:
<ul>
	<li>every DOM node implements an interface that defines how the structure of the tree can be accessed and manipulated</li>
	<li>examples of common DOM methods are: .getElementById(), .createElement(), .removeChild()</li>
</ul></li>
</ul></p>
<h3>The HTML parsing is synchronous</h3>
<p>When the parser reaches a "script" tag:
	<ul>
		<li>It <strong>stops parsing</strong></li>
		<li>It fetches the script from the network, if it is externa</li>
		<li>It yields control over to the Javascript engine to executes the code</li>
		<li>The parsing is resumed</li>
	</ul>
</p>
<p>Since "script" tags are blocking the parsing, moving them at the bottom of our web page (or just after the above the fold content) makes the page rendering faster.</p>
