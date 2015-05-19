## Server ##

Server-side is designed for AppEngine. It's written in Python with the help of Django. Setup should be easy:

  1. Install AppEngine SDK and Python
  1. Checkout the code
  1. Copy libraries from [djangoappengine](http://www.allbuttonspressed.com/projects/djangoappengine):
    * django-nonrel/django => project/django
    * djangotoolbox/djangotoolbox => project/djangotoolbox
    * django-autoload/autoload => project/autoload
    * django-dbindexer/dbindexer => project/dbindexer
    * djangoappengine => project/djangoappengine
  1. Copy gdata libraries from [gdata-python-client](http://code.google.com/p/gdata-python-client/source/browse/#hg%2Fsrc)
    * gdata => project/gdata
    * atom => project/atom
  1. Modify app.yaml for your own AppEngine instance (first line)
  1. Run it locally by `./manage.py runserver`
  1. Deploy to AppEngine using `./manage.py deploy`

Note: It's packaged as PyDev Eclipse project, so if you have Eclipse and PyDev, you can import project easily through File->Import->Existing Projects into Workspace.

## Android app ##

Android app is using Eclipse and again all libraries are included. Android app is tied to the server, so if you have own AppEngine instance you need to change few things:

  1. Install Android SDK, Eclipse and ADT Plugin
  1. Checkout the code
  1. In Eclipse File->Import->Existing Projects into Workspace
  1. Search code for "quiz-n-poll.appspot.com" and replace it with own server
  1. Search code for "org.quizpoll" and replace it with own package
  1. Connect your phone and hit Play button in Eclipse

## Spreadsheets ##

The solution is build on top of spreadsheets so you might want to change few things in order to offer content specific to your organization.

  1. Copy template spreadsheets from [documentation](http://quiz-n-poll.appspot.com)
  1. All spreadsheets and collection need to be shared with account **your-appengine-instance@appspot.gserviceaccount.com**
  1. Change SERVER constant in Apps Script for the spreadsheets (Tools->Script Editor)
  1. Create collection for your public quizzes. Put ID of this collection into Android app: QuizBrowserActivity.java, constant QUIZZES\_SHARED\_COLLECTION