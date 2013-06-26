Title: Setting up this blog
Category: Pelican
Tags: Pelican, github, git
Author: KaChon Lei
Summary: Setting up this blog 

I have been thinking about setting up a blog to track and share what I have learned recently.  So I look around to see where I should host my blog.  There are lots of platforms out there, like Wordpress, Tumblr, and LiveJournal.  However, I just need a simple one and probably a static one is fine for me.  And then I notice [github](http://github.com) provided a place where I could host a static page.  So I decide to try it out.  

So here is my first post.  About how I set up this blog!

**A.**  Setup a repository in github with the syntax ***username.github.io***.  For me, my repository is this [kachon.github.io](http://kachon.github.io).  Once the repository is setup.  I just need to push the html file onto the server and everything will be done.

**B.**  Use [Python](http://python.org) and [Pelican](http://blog.getpelican.com/) to generate the static html page.  Github have some examples about using [jekyll](http://jekyllrb.com/) to create the static webpage.  However, I am not that familar with Ruby.  Therefore, it is easier for me to use [Pelican](http://blog.getpelican.com/) instead. 

To create a virtual environment for Python	

    :::bash
	$ virtualenv ~virt_env/pelican
	$ cd ~/virt_env/pelican
	$ . bin/activate
        
To install Pelican and [Markdown](http://daringfireball.net/projects/markdown) (a text to HTML conversion tool)

    :::bash 
	$ pip install -e git://github.com/getpelican/pelican#egg=pelican
	$ pip install Markdown    	

After installing Pelican and Markdown.  I am ready to write my content.

**C.**  Use pelican-quickstart to setup the skeleton

Issue pelican-quickstart

    :::bash
	$ pelican-quickstart

After executing this command and answering some questions, my file system will have something like this:

    :::bash
	--/content
	--develop_server.sh
	--Makefile
	--pelicanconf.py
	...

The content of the blog will be stored in content folder and pelicanconf.py is used to control how to generate the static page.  For example, I have created a Markdown file called ***2013-06-24-setting-up-this-blog.md*** under the content folder for this first blog. 

**D.**  Install pelican-themes

To make the blog looks nicer, I choose to use ***Just-Read*** themes.  However, I prefer to use another [css](https://github.com/uraimo/pygments-vimstyles) for syntax highlighting.  So I decide to fork it and create my own repository [pelican-themes](https://github.com/kachon/pelican-themes). 

To install the theme
    
    :::bash
	$ pelican-themes -i pelican-themes/Just-Read


And add the following line to pelicanconf.py

    :::python 
	THEME = 'Just-Read'

**E.**  Create the output and push to github

The last step is to create the output folder and output the whole directory to github.

    :::bash
	$ pelican -s pelicanconf.py ./content -o ../output

And then push the output directory to github.

Done!
