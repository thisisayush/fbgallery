# fbGallery: A Responsive Facebook Gallery jQuery Plugin
Display Images from your Facebook Page in a nice Gallery using jQuery.

## Initial Setup
### Include jQuery Script

```html
<script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>
```

### Include Font-Awesome in <head>

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" />
```

### Include fbgallery.css file in <head>

```html
<link rel="stylesheet" href="/path/to/fbgallery.css" />
```

### Include fbgallery.js file 
- Add anytime after including jQuery but before initialising FB SDK 

```
<script src="/path/to/fbgallery.js"></script>
```

### Setting Up Container
- Define a container. Give it a unique id. 
- Plugin Uses 'fbGalleryContainer', 'lightbox', 'fbGalleryLoader' id's. Use any id other than these.

```javascript
<div id="mainContainer">
</div>
```
Now Initialise Facebook SDK and call the plugin with

```javascript
    $("#mainContainer").fbGallery({
        accessToken: 'your_access_token',
        excludedAlbums: ['array','of','excluded','album','ids'],
        pageId: 'your_page_id'
    });
```

```javascript
<script>
    var appId = 'your_app_id_here';
    var pageId = "your_facebook_page_id_here";
    var excludedAlbums = ["comma seperated","album ids"];
    var accessToken = 'your_access_token_here';   

    window.fbAsyncInit = function() {
        FB.init({
            appId      : appId,
            xfbml      : true,
            version    : 'v2.8'
        });
        FB.AppEvents.logPageView();
        $("#mainContainer").fbGallery({
            accessToken: accessToken,
            excludedAlbums: excludedAlbums,
            pageId: pageId
        });
    };
    (function(d, s, id){
        var js, fjs = d.getElementsByTagName(s)[0];
        if (d.getElementById(id)) {return;}
        js = d.createElement(s); js.id = id;
        js.src = "https://connect.facebook.net/en_US/sdk.js";
        fjs.parentNode.insertBefore(js, fjs);
    }(document, 'script', 'facebook-jssdk'));
</script>
```

## Settings

Following settings are availaible while calling the plugin:
- accessToken: (string)(required) Containing Facebook Access Token. You can use your <facebook-app-id>|<facebook-app-secret> as your Access Token as only public data is being accessed.
- pageId: (string)(required) Containing the page id of facebook page you are accessing photos. Head to About Section of your page to know your Page ID.
- excludedAlbums: (Array of strings)(optional) Containing the array of Album Ids to ignore/exclude from showing in page.

## Contributors
- @thisisayush