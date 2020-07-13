# How I created my webpage

This guide is supposed to document the process of creation of my own personal webpage. If you didn't ended up here by chance, I hope this guide will be of inspiration to create your own webpage.

I'm a linux user ([and you should be too](https://itsfoss.com/reasons-switch-linux-windows-xp/)), so I will put some command line instructions, but whatever suits your purposes is good.

## Documenting 

Rome wasn't built in a day, and so won't your webpage. The first step to create a webpage is understanding what you need to do so (big whoop!). I've already had some knowledge of how webpages work (the HTML structure, the CSS styling and the Javascript dynamics), so I told my self it was time I had started my personal portfolio. 

Ok, but were to start? Well... I just googled "Django how to create my website"!

This lead me to a (series of) page(s) by the Mozilla foundation that I'd already stumbled upon but forgot to keep reading; mostly due to the fact I wasn't able to understand what was written in it. 
There is a lot of information to crunch: so fasten your seatbelt and understand that the first week (at least) will be devoted to just studying the details!

First of all, you should be aware of [what you will need](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_software_do_I_need) and [how much would it cost](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/How_much_does_it_cost) the hosting of your webpage. The basic cost can be as low as 5-15$ per year! (That's encouraging, isn't it?!)

A simple webpage constists of a server (a physical computer) that serves allows other users to access the content of your data (a series of files) over a internet connection. Already here a fairly broad amount of knowledge comes into play: trasmission protocols, databases, content service management, ISP (internet service providers), serverless services. But you **don't need**  to be an expert in all of these.

A very good idea to handle the files which are going to form your webpage is by installing a text editor of IDE (Integrated Development Editor). My choiche will be [VS Code](https://code.visualstudio.com/), beginner-friendly but still powerful and complete IDE, and [GNU Emacs](https://www.gnu.org/software/emacs/), the ultimate text editor: an advanced and higly-customizable working environment (but for this reason not friendly and with an high-learning curve). You could take whatever editor you prefer, and there is really no absolutely good choice.

#### Creating the structure

The first step is to create a folder in your computer dedicated to this project and some subfolders for keeping files tidy and organized (this is very important).
To do so at once, run the following:

    $ mkdir -p MyWebPage/{Images,Styles,Scripts}

> `mkdir` is the basic command to create folders (it works on Windows too!). The `-p` (_parent_) flag is an option that is used to tell it that we will create subfolders (_child folders_).

We created the project folder along 3 other subdirectories we will use to store the pictures (Images), the CSS files (styles) and the Javascript file (Scripts) used by the page. I have also created a read-me file in which I will keep the documentation of the project (this page you're now reading) and a `index.html` file, which will contain the basic [HTML] structure of the webpage. The name of this latter file is standard and you should stick with it. 

This is a good point to introduce some Version Control System (VCS) into our project. It is not strictly necessary, yet it is **higly** recommended that you some SVC for your project: it will act a sort of diary of the project and can allow you to move back and forth is something goes wrong; plus, it could be essential if you later decide to let other people get involved with your page. My choice is going to be [Git](https://git-scm.com/), which is one of the most popular and versatile tool, but, as always, other choices are available. To set up the git version control of this project just type:

    $ git init .
    $ git add .
    $ git commit -m "Initial commit"
If you're not familiar with Git or you simply want to deepen your knowledge and learn some cool tricks, I advice to have a look at the [Atlassian guide](https://www.atlassian.com/git) on git. It is recommended to commit (repeating the last two commands) often (several times per day) in order to keep track of the history of your project.

At this point the project folder should have the following structure:

```
MyWebPage
├── .git
│   ├── branches
│   │   └── ... 
│   ├── hooks
│   │   └── ... 
│   ├── info
│   │   └── ... 
│   ├── logs
│   │   └── ... 
│   ├── objects
│   │   └── ... 
│   ├── refs
│   │   └── ... 
│   ├── COMMIT_EDITMSG
│   ├── config
│   ├── description
│   ├── HEAD
│   └── index
├── Images
│   └── Vendors
├── Scripts
│   └── Vendors
├── Styles
│   └── Vendors
├── index.html
└── README.md
```

Morale: an empty project is already quite messy! So **DO USE** version control!

## The website

Now we are ready to start working on the website. This will consist of many files and the content varies for every page. But roughly the process can be split in 3 phases:
- HTML creation
- CSS styling
- plug-ins

#### HTML: the scaffolding of your page

Html is a markup language, which means that its purpose is to format the text: divinding into sections and defining the various elements that will be later re-styled by the aid of the CSS file(s).

The most fundamental unit of the HTML language is the _tag_: these are the keywords used by to comunicate the computer what we intend to do within the file.
Tags can come single (_open tags_) delimited by  "<" ">" signs, or in pairs (_closed tags_) where the closing tag is delimited by "<\" ">" signs.
Most of the time we will be dealing with closed tags which are encapsulated into each other.
The most notable exception is the starting tag of an html page: `<!DOCTYPE html>`, which should always included at the beginning of a file that you want to use as webpage. 

Closed tags define an HTML element as shown in the picture:

![tag structure](./Images/Vendors/tags.svg "Image source [Wikipedia](https://en.wikipedia.org/wiki/HTML_element#Syntax)")

There could be many _attributes_ inside the opening tag, and some of them may take a _value_ which is assigned by you inside the quotation marks. The `class` attribute provide a way of classifying similar elements by giving it a value of your choice. Whereas, the `id` attribute is used to identify an element univocably. Thus, you must pay attention to give unique values to each element's id, while it's possible for several elements to share the same class.

There is a large number of possible keywords for the tags, and also they are under continuous development by the [W3C](https://www.w3.org/), the organization that is in charge of defining the standards of the [world wide web](https://en.wikipedia.org/wiki/World_Wide_Web).
In the table we will summarize the most important ones and explain briefly their use. 

| TAG | NAME |  USAGE|
|---| --- | ---|
| `<html> ... <\html>` | | This is the main tag that defines the top level of what is going to be rendered in the document.
| `<meta>` | | |
| `<title></title>` | |  |
| `<head> ... <\head>` | |  |
| `<body> ... <\body>` | | |
| `<header> ... <\header>` | | |
| `<div> ... <\div>` | | |
| `<nav> ... <\nav>` | | |
| `<h1> ... <\h1>` | | |
| `<p> ... <\p>` | | |
| `<ul> ... <\ul>` | | |
| `<ol> ... <\ol>` | | |
| `<li> ... <\li>`  |  | |
| `<a href="..."> ... <\a>` | | | 
| `<img src="..." alt="...">` | | | 
| `<em> ... <\em>` | | | 
| `<footer> ... <\footer>` | | |