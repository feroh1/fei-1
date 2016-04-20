# Fei-1 
Configurable universal official web site (web app) for my friend (A Fei) and everyone.

## Note
This project has been moved to [ShakingBlog](https://github.com/ShakingMap/ShakingBlog). 

## Description
- this is a: web app
- used as: official web site or blog for organization or personal use
- built with: Meteor, React, Mantra ...
- target: configurable (for use), clear code (for communication and learning)
- welcome: any helps, issues, shares and suggestions

## Get Started

### Install
- install npm and meteor
- clone this repo and run `npm i` and `meteor`
- open `http://localhost:3000` on your browser

### Manage Admin User
Now you can see nearly nothing. You will want to config yours site. But before that, you need to create an admin user.

- goto `/signup` page, and create a user
- find this user in mongodb and add field `"roles": {"__global_roles__": ["Admin"]}`

Now you have an admin user. You can login through `/login` page, logout through `/logout` page, and change password
through `/change-password` page.

Note: If you lost a user, you have to remove it from db and create a new one.

### Manage System
With admin user logged in, you can manage the system (site, app, whatever) through `/admin` page.

Note: by now, most of the settings are json objects or arrays of json objects. If you are not familiar with json,
you should have a quick learning.

Here is a list of what you can set: 

- web.title - String
- web.metas - array of html meta written as json object
- web.links - array of html link written as json object, useful for adding styles without touching the source code
- appbar.brand - {text, href}
- appbar.links - array of {text, href}
- footer.footer - {text, href, target}
- indexPage.title - String
- indexPage.carousel - array of {src, href, head, body}, all fields are String
- indexPage.sectionA - array of {src, href}
- indexPage.sectionB - array of {src, href}

### Manage Posts
You can create, update, publish/unpublish, remove posts through `/blog/admin` page.

Note: to make this app 'lite', it doesn't support file storage by now. So you will need to save your images and videos
in some other places, and refer to them through url in your posts. Though you may use base64 to embed image into text,
I think it's a bad idea unless the image is small enough.

### Support Disqus
To support Disqus comments for your posts, you need a settings.json file config-ed as below:

```
"public": {
    "disqus": {
      "shortname": YOUR_DISQUS_SHORTNAME
    }
  }
```

then, run app with settings.json file, such as `meteor --settings ./settings.json`

## Todo
- deploy a demo site
- upload more docs
- plan and develop more features

## License
MIT
