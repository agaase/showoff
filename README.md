# showoff

Ever wondered if you can have a website of your own where you can just add your project images, write something corresponding to that and it just shows up?. Its possible with showoff; A simple way to showcase your work online. [See a demo here.](http://agaase.github.io/webpages/showoff)

### Major Features
1. Add projects and its data using a simple file structure.
2. Two out of the box templates for listing your projects - Card & Stack. (Check out on [demo](http://agaase.github.io/webpages/showoff) page)
2. Look & feel as per your requirements using plain old css.
3. Ability to add commenting system using disqus and that too with just some configuration.


### How to use
1. Clone the git [repo](https://github.com/agaase/showoff.git) or download the zip ([here](https://github.com/agaase/showoff/archive/master.zip)) from the github page to your localhost root directory. 
2. Copy demo folder and give it a new name; lets say myportfolio.
3. In the data.json add the data for your site. (Look at section "Configuring data" below to see how to add data)
4. (Optional) To change the look and feel you can edit colors and font families in style/branding.css. All elements are commented so that you know what works where.
5. Launch your new site at http://localhost/showoff/myportfolio

###Configuring Data.
Data is maintained in json format in data.json and follows a tree structure. You can think of all projects grouped under a category. For e.g all your photography projects can be grouped under photography. The below explanation explains the details of data.json.

> NOTE - Below json is commented and hence invalid. (See raw valid json [here](http://agaase.github.io/webpages/showoff/data/data_explain.json) and json with full data [here](http://agaase.github.io/webpages/showoff/data/data.json))   

```
{
	"config" : {
	    //This section controls the config for the website.
	    //Right now only disqus config is present.
		"disqus" : {
		    //The shortname for disqus as you will find in your 
		    //disqus account
			"disqus_shortname" : "myshortname",
			
			//This is optional and more details can be found here
			//http://bitly.com/1y4buq3
			"disqus_url" : "http://aseemagarwal.in/"
		}
	},
	
	//This is the title of your website as appears on sections menu
	// on top left corner. This can be html formatted text.
	"masthead" : "Aseem Agarwal",
	
	"section" : [
	 //This is where your different categories start.
		{
		// A category can be shown as a plain html text.
		    //Title shows up in the sections menu as the category
		    //name
			"title" : "About me",
			
			//The content that will be shown in the main area.
			//This can be html formatted text.
			
			"itemBody" : "Some content about me",
			
			// Whether to launch this category as the home page.
			"isHome" : true

		},
		{
		// A category can be shown as a collection of different 
		// projects you want to showcase
			"title" : "MY WORK",
			
			//The classes you want to assign in dom to the item (seperated by space)
			//in the list.('list-stack' for stack layout and 'list-card' for card layout)
			"listItemClass" : "list-stack",
			
			//The list of projects starts here.
			"itemList" : [
				{
				    //Title of the project
					"title" :  "My project",
					
					//Thumbnail to show in the list.
					"thumbnail" : "http://abc.com/xyz_thumb.png",
					
					//Summary to show in the list.
					"summary" : "A community of magazine lovers.",
					
					// The list of image plus writeup combination
					// starts here.
					"_showcaseList" : [
						{
						    //The writeup for the image.
							"writeup" : "",
						    //The actual image.
							"img" : "http://abc.com/xyz.png"
						}
					]
				}
			]
		}
	]
}
```
###Project structure
```
 demos 
   - index.html
   - data
     - data.json // data for the demo page.
     
 dist
   - showoff.min.js (distribution minified file for showoff)
   
 src
   - showoff.js (source file for showoff)
   
 style
   - layout.css (all the layout styling)
   - branding.css (all the branding styling - font size, family, color etc)
```
