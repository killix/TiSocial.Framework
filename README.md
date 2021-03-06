# TiSocial.Framework Module

## Description

The TiSocial.Framework Module extends the Appcelerator Titanium Mobile framework with the iOS6 social.framework. This enables sharing content to Facebook and Twitter.

The module is licensed under the MIT license.


## Referencing the module in your Titanium Mobile application ##

Simply add the following lines to your `tiapp.xml` file:
    
    <modules>
        <module version="1.0" platform="iphone">dk.napp.social</module> 
    </modules>


## Accessing the TiSocial.Framework Module

To access this module from JavaScript, you would do the following:

		var Social = require("dk.napp.social");


The provided API is simple: None of the `text`, `image` and `url` are required. So you could just call `Social.facebook();`
You can use `Social.isFacebookSupported` and `Social.isTwitterSupported` to ensure that the user has minimum iOS6.
		
		if(Ti.Platform.osname == 'iPhone OS'){
			if(Social.isFacebookSupported){ //min iOS6 required
		        Social.facebook({
					text:"initial fb share text",
					image:"image.png",
					url:"http://www.napp.dk"
				});
			} else {
				//implement Ti.Facebook Method
			}
			
			if(Social.isTwitterSupported){ //min iOS6 required
				Social.twitter({
					text:"initial tweet message",
					image:"image.png",
					url:"http://www.napp.dk"
				});
			} else {
				//implement iOS5 Twitter method..
			}
			
			Social.addEventListener("complete", function(e){
				Ti.API.info("complete: "+e.success);	
			});
			
			Social.addEventListener("cancelled", function(e){
				Ti.API.info("cancelled");	
			});
			
		}

## Author

**Mads Møller**

web: http://www.napp.dk

email: mm@napp.dk

twitter: nappdev

## License

    Copyright (c) 2010-2011 Mads Møller

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.