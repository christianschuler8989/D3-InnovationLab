<script lang="ts">
	import { Presentation, Slide, Notes } from '@components'
	import Layout from './layout.svelte'
</script>

<!-- Typical Errors
	
	"Uncaught TypeError: slidesInChapter[0] is undefined" and layout elements missing.
	→ This can happen if a chapter is defined but has no slides.

-->

<Presentation>	
	<script>
		// information about this presentation 
		const author = "Stephan Leible, Maren Gierlich-Joas, Tilo Böhmann,<br> Christian Schuler, Dominik Hauser, Hannes Klingler"; 
		const authorShort = "Leible, Gierlich-Joas, Böhmann, Schuler, Hauser, Klingler"; 
		const title = "Data-driven Digital Innovation Lab";
		const subtitle = "Digital and Data Literacy in Teaching Lab";
		const department = "Mathematik, Naturwissenachaften und Informatik (MIN)"; 
		const university = "University of Hamburg"; 
		var currentChapterName="";
		var currentChapterNumber=0;
		var chapterNames=[];
		var toc = false;  // whether toc is to be generated
		// data structure: [chapter number, chapter name, slideID]
		var presentationData = []; 
		function newChapter(chapterName){
			currentChapterName=chapterName; 
			currentChapterNumber++;
			chapterNames.push(chapterName);
		}
		// called when new slide is created
		var page=0; 
		function newPage(){
			page++; //note that page n has index n-1
			presentationData.push({chapternr: currentChapterNumber, chapter:currentChapterName,pagenr:page});
		}
	</script>

	<!-- title page -->
	<Slide><Layout>
		<div class="m-16 flex h-[25vh] w-[90vw] bg-[var(--themecolor)] text-white items-center justify-center gap-[100px]">
			<div>
				<div class="text-[6vh]">
					<span id="mytitle"> </span>
				</div>
				<br>
				<div class="text-[4vh]">
					<span id="mysubtitle"> </span>
				</div>
			</div>
		</div>
		<br>
		<div> 
			<span id="myname"></span>
		</div>
		<br>
		<div class="text-[3vh]"> 
			<span id="myuni"></span>
		</div>
		<div class="text-[3.5vh]"> 
			<br>
			<span id="mydate"></span>
		</div>
		<br>
		<div class="flex items-center justify-center">
			<img class="h-[10vh] align-middle" src="/AwesomeAnranSlides/tum-logo.svg" alt="tum logo">
		</div>
		<!-- fill in the data for this presentation  -->
		<script> 
			document.getElementById("mytitle").innerHTML=title;
			document.getElementById("mysubtitle").innerHTML=subtitle;
			document.getElementById("myname").innerHTML=author;
			document.getElementById("myuni").innerHTML=department+"<br>"+university;
			let today = new Date(); 
			document.getElementById("mydate").innerHTML=today.toISOString().split('T')[0]; 
		</script>
	</Layout></Slide>
	<!-- TOC -->
	<!-- <Slide>
		<script>
			toc=true; // decides whether to generate table of content page
		</script>
		<Layout>
			<toc class="flex h-full items-center justify-center gap-[100px]">
				<chpicons> </chpicons>
				<chpnames class="text-left"> </chpnames>
			</toc>
		</Layout>
	</Slide> -->
	
	<!-- intro -->
	<script>newChapter("Data-driven Digital Innovation Lab ")</script>
	<Slide><Layout>
		<titlebar > Data-driven Digital Innovation Lab  </titlebar>
		<mybody>
			<ul class="a">
				<li>The Data-driven Digital Innovation Lab project<br> is an initiative to further student's data literacy.</li>
				<br>
				<li>This project ran 12 months from early 2023 until spring of 2024,<br> with a number of results, some are:</li>
				<ul class="b"> 
					<li>A seminar called "Zukunftsfelder der Digitalisierung: Datengetriebene Digitale Innovationen und Generative KI"</li>
					<li>A Wiki regarding the data life cycle and how to manage it</li>
					<li>A teaching concept presented at the TURN-2024</li>
					<li>An idea management tool to foster co-creation approaches</li>
					<li>A Design-Workshop presented on the following slides</li>
				</ul>
			</ul>
		</mybody>
	</Layout>
	<Notes>
		These are some presenter notes that can help during the actual presentation.<br>
		They are displayed on the presenter's screen if "presenter mode" has been entered.
	</Notes></Slide>

	

	<script>newChapter("Kokreation Explorationsraum Workshop");</script>
	<Slide><Layout>
		<titlebar > Co-Creation Workshop Designing a Exploration-Lab </titlebar>
		<mybody>
			<ul class="a">
				<li>First, students were introduced to a 3D-room planner software.</li>
				<br>
				<li>Next, the students (in groups of each 2-3):</li>
				<ul class="b"> 
					<li>designed an exploration-lab room,</li>
					<li>documented their process and decisions,</li>
					<li>and presented their results.</li>
				</ul>
				<br>
				<li>Each presentation was followed by a short round of feedback and discussion.</li>
				<br>
				<li>These designs serve as basis for creating rooms in which students find a place to work and study- in groups or alone.</li>
			</ul>
		</mybody>
	</Layout></Slide>

	<script>newChapter("Student-Made Lab Designs");</script>
	<Slide><Layout>
		<titlebar > Lab Design #1 </titlebar>
		<mybody>
			<img src="design-01.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>

	<Slide><Layout>
		<titlebar > Lab Design #2 </titlebar>
		<mybody>
			<img src="design-02.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>

	<Slide><Layout>
		<titlebar > Lab Design #3 </titlebar>
		<mybody>
			<img src="design-03.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>

	<Slide><Layout>
		<titlebar > Lab Design #4 </titlebar>
		<mybody>
			<img src="design-04.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>

	<Slide><Layout>
		<titlebar > Lab Design #5 </titlebar>
		<mybody>
			<img src="design-05.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>

	<Slide><Layout>
		<titlebar > Lab Design #6 </titlebar>
		<mybody>
			<img src="design-06.gif" alt="Lab Design Gif" class="w-[75vw] h-[88vh] mx-auto my-auto p-2" />
		</mybody>
	</Layout></Slide>


	<!-- to mimic the latex template  -->
	<script>
		const totalSlides = document.getElementsByTagName('pagenumber').length;
		const totalChapters = chapterNames.length;
		var temp; 
		for (let i = 0; i < totalSlides; i++) {
			// one section, one slide
			document.getElementsByTagName('section')[i].setAttribute("id", "slide-"+(i+1));
			// add author name 
			document.getElementsByTagName('author')[i].innerText=authorShort;
			// add title 
			document.getElementsByTagName('mytitle')[i].innerHTML="<a href=\"#slide-1\">"+title+"</a>";
			// show slide number with total slide number
			document.getElementsByTagName("pagenumber")[i].innerHTML = (i+1)+"/"+totalSlides;
		}
		for (let i = 0; i < totalSlides; i++) {
			for (let j = 0; j < totalChapters; j++) {
				// fill in chapter names
				temp = document.querySelectorAll("table.topbar")[i]; 
				temp.getElementsByTagName("tr")[0].innerHTML += "<th data-chpcol=\"chpcol\" style=\"font-weight:normal\">"+chapterNames[j]+"</th>";
				// document.getElementsByTagName("test")[0].innerHTML="here!"; 
				// fill in dots
				let slidesInChapter = presentationData.filter(item => item.chapter == chapterNames[j]);
				let begin = slidesInChapter[0].pagenr;
				let end = slidesInChapter[slidesInChapter.length-1].pagenr;
				let circles=toCircle(begin,end);
				temp.getElementsByTagName("tr")[1].innerHTML += "<td>"+ circles +"</td>";
			}
		}
		for (let i = 0; i < totalSlides; i++) {
			// first, find out if title page and toc exist 
			let chapter0 = presentationData.filter(item => item.chapternr == 0).length;
			if (i>=chapter0){
				// then set corresponding circle to white
				let circle = document.getElementsByTagName("circle-"+(i+1))[i]; 
				circle.style.background="white";
				circle.style.border="0px";
				// also the chapter names 
				let chapterNr = presentationData.filter(item => item.pagenr == i+1)[0].chapternr;
				temp = document.getElementsByTagName("th")[(i)*(totalChapters)+chapterNr-1];
				if (temp.hasAttribute("data-chpcol")){ 
					temp.style.color="white";
				}
			}
		}
		// circles: start, start+1, . . . , end are created
		function toCircle(begin,end){
			let circles = ""; 
			for (let i=begin; i<=end; i++){
				circles+="<a href=\"#slide-" +i+ "\"><circle-" +i+ " class=\"dot\"> </circle-" +i+ "> </a>" ;
			}
			return circles;
		}
		// to create table of contents
		if (toc) {
			for (i=1; i<=chapterNames.length;i++){
				document.getElementsByTagName('chpicons')[0].innerHTML += "<div class=\"chpicon\">"+i+"</div> <br>";
				document.getElementsByTagName('chpnames')[0].innerHTML += "<div>"+chapterNames[i-1]+"</div> <br>";
			}
		}
	</script>
	
	<style>
		.chpicon{
			color: white;
			width:180%;
			background: var(--themecolor);
		}
		.dot {
			height: 15px;
			width: 15px;
			background: rgba(0,0,0,0);
			border-radius: 50%;
			border: 1.5px solid var(--themecolorlight);
			display: inline-block;
		}
		ul.a {
			list-style-type: square;
			padding-top:5vh;
		}
		ul.b {
			list-style-type: circle;
			margin-left:5vh;
			margin-right:5vh;
			padding-top:1vh;
			padding-bottom:1vh;
		}
		ul.c {
			list-style-type: disc;
			margin-left:10vh;
			margin-right:5vh;
			padding-top:1vh;
			padding-bottom:1vh;
		}
		ul{
			text-align: left;
			margin-left:20vh;
			margin-right:5vh;
			padding-top:1vh;
			padding-bottom:1vh;
		}
		titlebar{
			position:absolute;
			top:0;
			left:0;
			background: rgb(242,242,242); 
			width: 100vw; 
			height: 9vh; 
			text-align: left;
			padding-left: 5vh; 
			padding-top: 2vh;
			font-size: 5vh;
		}
		mybody{
			display: flex;
			justify-content: center;
			align-items: center;
			height:79vh;
		}
		figure {
			border: 0px #cccccc solid;
			padding: 4px;
			margin: auto;
		}
		figcaption {
			background-color: rgb(242,242,242);
			color: black;
			font-style: italic;
			padding: 2px;
			text-align: center;
		}
	</style>
</Presentation>