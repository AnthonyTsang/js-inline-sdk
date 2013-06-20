## How it looks like
http://demo.oneskytranslate.com/


### 1. Wrap the text to be translated with OneSky tag and provide a key
  ```html
  <os-p key="the_key_of_the_text">the text to be translated<os-p> 
  <os-p key="menu.bar.item.about_us">About Us<os-p> 
  ```
  
  Remember DO NOT wrap the text in attributes, select elements nor header elements
  ```html
  <a href="#" title="<os-p key="some_link_descriptions">Link Description<os-p>">Link</a>
  <title><os-p key="some_link_descriptions">My site title<os-p></title>
  <select>
      <option><os-p key="a_list_item">An item<os-p></option> 
  </select>
  ```

### 2. Put a Cross-domain channel file under your domain

  We'd need to have some javascript communications with your page, so we require to put a file at your side to allow cross-domain javascript communication.
  Download the xd_receiver.html from this repo.

  Make sure it is read-able in this url
  http://www.yourdomain.com/xd_receiver.html

### 3. Include OneSky's javascript
```html
<script type="text/javascript" src="//s3.amazonaws.com/oneskyapp.static/onesky-loader.js"></script>
```

### 4. Config the page
  ```javascript
  OneSkyClientConfig = {
    'key'				: 'Your Public API Key',
  	'platform_id'			: 'Platform ID for the page, e.g. 1234', // the number below your platform name
  	
  	// You can set this as FALSE or simply not calling OneSkyClient 
  	'start_translate'		: TRUE,
  	
  	// The locale that user is accessing, we do not have any default setting for that, all depends on you 
  	'locale'			: 'en-US', // we support ISO 639-1
  	
  	/* 
  	* [OPTIONAL] Single Sign On settings to seamlessly sign in your users for inline translation
  	* You may refer to SSO Tutorial
  	*/ 
  	'sso_id'			: '6894', // ID from your system to manage user contributions
  	'sso_name'			: 'User_6894',
  	'sso_data'			: '48c37dd76116e825f11cc100188bf063',
  	'sso_time'			: '1355371257'
  	
  	// [OPTIONAL] More settings that you might be interested in 
  	'xd_receiver'			: '/my/own/xd_receiver.html'	
  }};
  ```
### 5. Done!
  Shall you need further assist, ping us support@oneskyapp.com
