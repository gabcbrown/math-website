## Inspiration websites
### Static sites
minimal
- https://joshuamundinger.github.io/
- https://www.caglaruyanik.com/
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

### google sites
- https://sites.google.com/site/amylouisecochran
- https://sites.google.com/view/lovingmath/home


## Steps
0) Decide how you want to build your website: google site (no code) or static site(edit an html template and host through github.io site or through the department).
1) Figure out what template to use. I recommend starting by using this basic template so you get the information out there, and then you can change the template in the future. If you find a website you like and it's a static website, then you can download the html and other resources by going to `file>save page as` in your browser. (If it's a google site or a wordpress site this won't really work.)

2) Write your website copy. This should include the following information, you can decide if you want it to be on different pages, or in different sections all on one page.
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
3) put the copy and the template together
4) publish your website
5) get the website listed on the department website!
6) submit your website with google SEO

## Setting up math department server hosting
### 0) How to read this doc
For this document, USERNAME means the username for your wisconsin email account. For example, if your email is gbrown29@wisc.edu then USERNAME should be read as gbrown29. 

Text that looks like 
> this 

is intended to be typed into a terminal, but make sure to check the surrounding text that describes it to see if you actually need to do that step. 

### 1) SSH
Open terminal and ssh to your UW math account serverspace

> ssh USERNAME@login0.math.wisc.edu

This will prompt you for a password, and you need to use the one you set for your math wisc account not your email (password reset at https://help.math.wisc.edu).

### 2) Check for a `public` folder

You should now be in an ssh directory called `/grad/USERNAME`, which you can check using

> pwd

In your ssh directory type 

> ls 

this will display a list of folders and files in your math account server space. If there's already a folder named `public`, open it using 

> cd public

Otherwise create one and set its permissions properly, then open it using 

> mkdir public; chmod 775 public; cd public

### 3) Check for an `html` folder

Similarly to step 2), check what is already in this folder with

> ls

If there's already a folder called `html`, open it using 

> cd html

If there isn't one, make it, set its permissions, and then open it using 

> mkdir html; chmod 775 html; cd html


### 4) Check for an `index` file

Now we're at the place where your main website file will live. Once again, check what's already here using 

> ls 

If there's already a file called `index.html` congrats! This is where your website code lives. If there isn't one, make it using 

> touch index.html; chmod 755 index.html 

You can see your website (which at this point will be empty!) at `people.math.wisc.edu/~USERNAME`

