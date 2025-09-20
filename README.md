## Steps
1) Write your website content. This should include the following information, you can decide if you want it to be on different pages, or in different sections all on one page.
```
Home page
- Your name
- Your position and the university you're at
- Your advisor
- Where you did your undergrad
- Your email 
- A photograph of you
- A section for upcoming travel that you update regularly (so people know when they can see you! start this early, it's a good habit to get into)

Research page
- a summary of your research interests/what you work on
- a list of publications, including arxiv preprints

Teaching page
- a list of courses you've taught: 
Institution
Semester Year: Course number Course Title - Role

Notes page
- any other things you want to live on your website. maybe notes from your research or class work that you want to share, maybe advice, maybe a tutorial about how to build a math website :) 

CV page
- it's just a link to your CV pdf
```

2) Decide how you want to build your website: google site (no code) or static site (edit an html template and host through github.io site or through the department). 

|               | Google Site   | HTML Static Site |
| ------------- | ------------- | ------------- |
| Pros | Free, very easy to set up, very easy to update, low maintenance | Free, complete control over how your website looks, easy to update, a nice introduction to how to use the department research servers, more classic math website look |
| Cons | Appearance is not very customizable, it's Google so you never know if they'll randomly decide to stop supporting google.sites | Requires coding, have to use a terminal every time you want to update |

## Inspiration websites
### Static sites
this site
- https://people.math.wisc.edu/~gbrown29/

minimal
- https://joshuamundinger.github.io/
- https://people.reed.edu/~zdaugherty/
- https://www.dumas.io/
- https://bsteinberg.ccny.cuny.edu/Webpage/
- https://people.math.wisc.edu/~apisa/
- https://people.math.wisc.edu/~ellenberg/

cool
- https://people.math.wisc.edu/~aekent2/

90's core
- http://wphooper.com/
- https://people.math.wisc.edu/~dymarz/

### More complicated static sites
structured data template/generation:
- https://johndcobb.github.io/

### Google sites
- https://www.caglaruyanik.com/
- https://sites.google.com/site/amylouisecochran
- https://sites.google.com/view/lovingmath/home


## Steps for a Google Site
3) Sign into a personal email account and go to https://sites.google.com
4) Create a new website (there is a template specifically for graduate students)
5) Add your website content
5) Publish your website
6) Get the website listed on the department website by emailing the url to nagreen@math.wisc.edu)

## Steps for HTML Static Site
2) Find a template! Some inspiration websites are linked above. You can also find a website you like and if it's a static website, then you can download the html and other resources by going to `file>save page as` in your browser. (If it's a google site or a wordpress site this won't really work. You can tell something is a static website because the index.html will be pretty simple. The one in this repository is a good example.)
3) Download VS Code
4) Download the template you're using into a new folder titled `website`
5) Open the `index.html` file in VS Code and edit to have your content
6) Transfer all the relevant files to the math department servers
6) get the website listed on the department website! (email nagreen@math.wisc.edu)
6) submit your website with google SEO ask sara or gabriela for help




## Setting up math department server hosting
Following this KB article (you need to be logged in and on school wifi or on a VPN)
https://kb.wisc.edu/math/internal/page.php?id=122221

### 0) How to read this doc
For this document, USERNAME means the username for your wisconsin email account. For example, if your email is gbrown29@wisc.edu then USERNAME should be read as gbrown29. 

Text that looks like 
> this 

is intended to be typed into a terminal, but make sure to check the surrounding text that describes it to see if you actually need to do that step. 

### 1) SSH
Open terminal and ssh to your UW math account

> ssh USERNAME@login0.math.wisc.edu

This will prompt you for a password, this is now the same as your SSO password.

### 2) Check for a `public` folder

You should now be in an ssh directory called `/grad/USERNAME`, which you can check using

> pwd

In your ssh directory type 

> ls 

this will display a list of folders and files in your math account server space. If there's already a folder named `public`, open it using 

> cd public

Otherwise create one and set its permissions properly, then open it using 

> mkdir public; chmod 755 public; cd public

### 3) Check for an `html` folder

Similarly to step 2), check what is already in this folder with

> ls

If there's already a folder called `html`, open it using 

> cd html

If there isn't one, make it, set its permissions, and then open it using 

> mkdir html; chmod 755 html; cd html


### 4) Check for an `index` file

Now we're at the place where your main website file will live. Once again, check what's already here using 

> ls 

If there's already a file called `index.html` congrats! This is where your website code lives. If there isn't one, make it using 

> touch index.html; chmod 755 index.html 

You can see your website (which at this point will be empty!) at `people.math.wisc.edu/~USERNAME`

### 5) Transferring files 
**Option 1**
You can transfer the `website` folder files directly to the math department servers using the following command: 
 
> scp -r website USERNAME@login.math.wisc.edu:/homes/USERNAME/public/html

**Option 2**
Or you can follow these instructions to do it with a GUI interface https://kb.wisc.edu/math/internal/page.php?id=122223

**Option 3**
My preferred method is to set up a Github repository for the `website` folder, and then clone it to the math department servers. This way you can make changes on your computer, preview them, commit them to the github repository, and then pull the changes into the department servers. 


### 6) Troubleshooting permissions
If you're trying to access your website and you're getting an error that you don't have permission to access this file, make sure every file in your `/grad/USERNAME/public/html` directory has the right permissions. You can check this by running 

> ls -l 

and in the output you want to see that the files have the permissions `-rwxr-xr-x`. If some file doesn't have this set of permissions you can update it using 

> chmod 755 FILENAME
