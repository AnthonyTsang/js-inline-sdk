## See it in action
www.oneskyapp.com/docs/bootstrap/es?inlineTranslate=true


### 1. For the texts to be translated, wrap them with a OneSky tag and provide a key
  ```html
  <os-p key="the_key_of_the_text">the text to be translated<os-p> 
  <os-p key="menu.bar.item.about_us">About Us<os-p> 
  ```
  
  [Reminder!] Do not wrap the text in attributes, select elements or header elements
  ```html
  <a href="#" title="<os-p key="some_link_descriptions">Link Description<os-p>">Link</a>
  <title><os-p key="some_link_descriptions">My site title<os-p></title>
  <select>
      <option><os-p key="a_list_item">An item<os-p></option> 
  </select>
  ```

### 2. Put a Cross-domain Channel File under your domain

  Our system will need to communicate with your page in javascript, so you need to put a file on your side to allow cross-domain javascript communication.
  Download the xd_receiver.html from this repo.

  Make sure it is read-able in this url
  http://www.yourdomain.com/xd_receiver.html

### 3. Include OneSky javascript file
```html
<script type="text/javascript" src="//s3.amazonaws.com/oneskyapp.static/onesky-loader.js"></script>
```

### 4. Configure the page
  ```javascript
  OneSkyClientConfig = {
    'apiKey'				: 'Your Public API Key',
  	'project'			: 'Platform ID for the page, e.g. 1234', // the number below your platform name
  	
  	// You can set this as FALSE or simply not calling OneSkyClient 
  	'translate'		: TRUE,
  	
  	// The locale that user is accessing 
  	'locale'			: 'en-US', // we support ISO 639-1
  	
  	/* 
  	* [OPTIONAL] Single Sign On settings to sign in your users for inline translation
  	* You may refer to SSO Tutorial
  	*/ 
  	'ssoId'			: '6894', // ID from your system to manage user contributions
  	'ssoName'			: 'User_6894',
  	'ssoData'			: '48c37dd76116e825f11cc100188bf063',
  	'ssoTime'			: '1355371257'
  	
  	// [OPTIONAL] More settings that you may be interested in 
  	'xdReceiver'			: '/my/own/xd_receiver.html'	
  }};
  ```
### 5. Done!
  Shall you need further help, ping us at support@oneskyapp.com
