# Krystal for Glitch

Get your own online wiki to take notes:

1. Go to <https://glitch.com/~krystal-tiddlywiki>.
2. Click the `Remix` button there to make your own project.
3. Click the `Show` button and start using it. It should work. 

After remixing the project:

Probably sign in to Glitch
--------------------------
Anonymous projects might get deleted after a while. So.

* make an account and sign in
* maybe rename your project – it got an autmatically generated name. Click the top left button and (over-) write on the lines at the top.

You have your own TiddlyWiki online app now. TiddlyWiki is the software we use. Glitch is the server environment that makes your project available on the web. TiddlyWiki (TW) is the foundation, your app is what you build on it.


Set up who has access
---------------------
Go to the `.env` file to control who can read and write to your app. Maybe change the `SERVEROPTS`-line to something along the lines of:

    SERVEROPTS="readers=(anon) writers=joe username=joe password=bloggs"

But like with different username and password probably. See <https://tiddlywiki.com/static/WebServer.html> for details and more options.

Note that if you set it up along these lines, so that everyone can read,
and only some can write, then you must go to `/login-basic` in order to log in for writing.
Like if the wiki is at e.g. <https://your-appname.glitch.me/> 
then you go to <https://your-appname.glitch.me/login-basic> to log in.

Details
-------
Maybe take a look at `package.json`. Or not. If you want. There isn't too much going on there.

The wiki is put in `.data/wiki` (set up in the `scripts` part of `package.json`). Stuff in `.data` is kind of private, other people can't see it and stuff in there won't be carried over if the project is remixed. So when the project is remixed, a new kind of empty TiddlyWiki is created.

The `.env` file is also private. Or at least the part that comes after the `=` on a line. Others can't see it, won't carry over when remixing.

If you download your own project (click the `Tools` button in the lower left corner, `Git, Import and Export` then `Download Project`), you do get everything. Including the `.data` folder and the full `.env` file. So can do that if you wanna host it somewhere else, or back everything up somewhere else, or something.

Backup
------
Instead of downloading the whole project as described in the `Details` section, you can download a fully functional one-page HTML version of your project anytime. Just click the checkmark icon to download a file `tiddlywiki.html` that shows your content in every browser. 
Visit <https://tiddlywiki.com/> to find out more about TW versions and saving options.

### Restore
To import your data from a backup file, e.g. into a new `Remix`, just drag and drop it onto the browser window of the destination wiki.

Help
----
Visit <https://groups.google.com/forum/#!forum/tiddlywiki> if you have questions, the community is really welcoming and friendly.

Upgrading
---------
In the file `package.json` you can define the version of TiddlyWiki you would like to use.
A test with the following code seemed to work.

    "dependencies": {
        "tiddlywiki": "^5.1.21"
    }

About
-----
* Krystal was created by [Roman Veselý](https://romanvesely.com/) - see the Github Repo here: <https://github.com/crazko/krystal>
* Glitch example created by [Tom Critchlow](https://tomcritchlow.com)