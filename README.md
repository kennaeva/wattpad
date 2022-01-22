# MiniWiki

A classic wiki is a small system for creating a hypertext network via a web browser. 
In the classic wiki, all pages used WikiCaseNames, which allows the system to automatically
format hyperlinks inline and generate new pages as names are defined, without the user needing
to know any HTML or HTTP. Additionally, in the classic wiki, all users can edit all pages.

MiniWiki implements a very simple, classic Wiki, using PHP and some rudimentary React Javascript.

## What we're asking

As we mentioned in the brief, during your technical interview, we'll ask you to make
some changes to this code. We've included a simple front-end, to help you visualize the
application. However, we don't actually care about it. You are free to invoke the API
any way you want during your interview. 

**We ask you make two changes at home, before your interview**. During your interview, you'll 
walk us through your changes, so that we can review your code. Then, we'll get you to make a 
third change during the interview. You can use your favourite tools and whatever online 
documentation you prefer. We want this to feel as much like your usual workday as possible. 
That's what we're interested in seeing -- how you actually work.

Your homework:

1. **Add the ability to delete a page.**

We leave it up to you how you want to implement this. Remember: we don't care if you update the
frontend code, as long as the API works.

2. **Add a change log to each page.**

For this step, we want you to add code so that every time a page is updated, in addition to updating
the text, you also save the new text and the timestamp (you can use `time()` for that purpose) in a
change log. Then include that change log in the response for the article page. Here's what your 
response might look like for `/HomePage?json`:

```
{
  "name":"HomePage",
  "text":"Welcome to MiniWiki, version 2.",
  "html":"<p>Welcome to <a href='/MiniWiki' title='MiniWiki'>MiniWiki</a>, version 2.</p>",
  "history":[
     {"time":1612500000,"text":"Welcome to MiniWiki, version 2."},
     {"time":1612400000,"text":"Welcome to MiniWiki, version 1."}
  ]
}
```
 
## Setup and execution

To run MiniWiki, you will need a Docker client and a network connection. 
[Docker Desktop](https://www.docker.com/products/docker-desktop) is a good option. Once installed,
from the root of this repository, use the `dev` command to start the system:

```
./dev start
```

## `dev` Usage

Run your commands from the root of this repository:

```
USAGE: dev COMMAND [ARGS...]

Commands:
   start   Starts the VM
   stop    Stops the VM (or you can ctrl-c the start command)
   test    Runs the specified (or all, if none specified) tests in separate processes
   php     Runs the parameters as a PHP script

```

## Web Access

Once you have the VM started (`./dev start`), you'll be able able to access the wiki at:
* http://localhost:9081/

To bypass the React frontend on any request, append `?json` to the URL:

* http://localhost:9081/?json
* http://localhost:9081/HomePage?json

## Where to begin

The application entry point is [app/public/index.php](https://github.com/Wattpad/mini-wiki/blob/main/app/public/index.php).

The classes live in [app/classes](https://github.com/Wattpad/mini-wiki/tree/main/app/classes).

The JSON API is defined in [app/classes/MiniWikiApi.php](https://github.com/Wattpad/mini-wiki/blob/main/app/classes/MiniWikiApi.php).

The JSON API tests are in [app/classes/MiniWikiApi.tests.php](https://github.com/Wattpad/mini-wiki/blob/main/app/classes/MiniWikiApi.tests.php).

The React frontend lives in [app/public/js](https://github.com/Wattpad/mini-wiki/tree/main/app/public/js).





