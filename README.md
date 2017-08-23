# practice

Table Overflow:
<a href="https://classroom.udacity.com/courses/ud893">Udacity</a>

Image width: 100vw;
<a href="https://classroom.udacity.com/courses/ud882"> Image Processing</a>

<h4> Selecting the right image format </h4>
<img src="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/images/format-tree.png">


<h4> Image Optimization</h4>
<a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization">https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization</a>



~~~

*  WebP delivers a 30% filesize decrease over a comparable JPEG image.

~~~


# <a href="https://www.youtube.com/watch?v=pS8udLMOOaE">https://www.youtube.com/watch?v=pS8udLMOOaE</a>

#webp 
<br>
<img src="http://res.cloudinary.com/duqwfkttw/image/upload/v1501617743/download_xpi3qs.webp">
~~~
42kb
~~~

#Jpeg
<img src="http://res.cloudinary.com/duqwfkttw/image/upload/v1501617850/download_rfdevd.jpg"> 

~~~

240kb
~~~

#Automating Performance Best Practices with PageSpeed - Google I/O 2013
<hr>
<a href="https://www.youtube.com/watch?v=uR5urTx8S4E">https://www.youtube.com/watch?v=uR5urTx8S4E</a>
 
 
  1. Provides Suggestions to Increase speed
  2. Suggestions to what to modify and <strong>relative link to take action</strong>
  3. If the older client doesn't understand the WebP then it serves with Jpeg.
  
  <img src="http://res.cloudinary.com/duqwfkttw/image/upload/v1501628293/Screen_Shot_2017-08-01_at_3.57.29_PM_l3y11s.png">

<hr>

<strong>Use less data with Chrome’s Data Saver</strong>
With Data Saver, you can lower your phone bill or load webpages faster on slow connections by reducing the amount of data Chrome uses.

How Data Saver works
When you use Data Saver, most of your web traffic goes through Google servers before being downloaded to your device. Less data gets downloaded to your device, because Google servers will compress it.

Data Saver won't work if you're on secure pages (addresses that start with https://) or if you're browsing in private with Incognito mode.

If you're using Data Saver, keep in mind that:

Some websites might have trouble finding your location.
Some images might look fuzzy.
Websites that are restricted to certain groups, like your company’s internal sites, might not load.
You might not be able to sign in to your mobile carrier's website.
Changes you made to your /etc/hosts file won't work.


<strong>Turn on Data Saver</strong>
Install the Data Saver extension from Chrome Web Store.
Data Saver should turn on automatically. If it doesn't, at the top right of your browser, click Data Saver Data Saver.
Click the checkbox.

# Data saver is not available in iphones 

Link:
<a href="https://support.google.com/chrome/answer/2392284?co=GENIE.Platform%3DDesktop&hl=en&oco=0">https://support.google.com/chrome/answer/2392284?co=GENIE.Platform%3DDesktop&hl=en&oco=0</a>

<h3> ImageOptum </h3>

<a href="https://imageoptim.com/mac">ImageOptim is excellent for publishing images on the web (easily shrinks images “Saved for Web” in Photoshop). It's useful for making Mac and iPhone/iPad ...</a>

<h3> ImageAlpha — image minifier (like JPEG with transparency!) </h3> 

https://pngmini.com/
<a href="https://pngmini.com/">ImageAlpha greatly reduces file sizes of 24-bit PNG files (including alpha transparency) by applying lossy compression and conversion to a more efficient ..</a>

~~~
What is the main difference between lossy and lossless compression?

Lossless and lossy compression are terms that describe whether or not, 
in the compression of a file, all original data can be recovered when the 
file is uncompressed. With lossless compression, every single bit of data 
that was originally in the file remains after the file is uncompressed
~~~

<h4> How to find the Natural size of the Image </h4>

<img src="http://res.cloudinary.com/duqwfkttw/image/upload/v1502738344/Screen_Shot_2017-08-14_at_12_12_52_PM_cvapt4.webp"></img>

#  ****************    Grunt Automation   ***********************

<h4> Automation : Grunt (configure and merge with projects)</h4

Process is wiered to understand, first read Documentation and follow steps:

step 1: <a href="https://www.youtube.com/watch?v=TMKj0BxzVgw"> Automation : Grunt </a>

paradigm :1 

```javascript 
package.json
  "name": "projectgrunt",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "grunt": "^1.0.1"
  },
  "devDependencies": {
    "grunt-contrib-concat": "^1.0.1",
    "grunt-contrib-imagemin": "^2.0.1",
    "grunt-contrib-watch": "^1.0.0"
  }
}
```
<hr>

```javascript
gruntfile.js
module.exports =function(grunt){
grunt.initConfig({
  concat: {
    dist: {
      src: ['intro.js'],
      dest: 'built.js',
    },
  },
});
grunt.loadNpmTasks('grunt-contrib-concat');
//grunt.registerTasks('default',['concat']);
};
```

<hr>

```javasript
intro.js/(built.js)
hello how are you this is grunt 
```

Paradigm 2:

```javascript

package.json
{
  "name": "projectgrunt",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "grunt": "^1.0.1"
  },
  "devDependencies": {
    "grunt-contrib-concat": "^1.0.1",
    "grunt-contrib-imagemin": "^2.0.1",
    "grunt-contrib-watch": "^1.0.0"
  }
}

Gruntfile.js
module.exports =function(grunt){
grunt.initConfig({
    imagemin: {
        dynamic: {
            files: [{
                expand: true,
                cwd: 'src/',
                src: ['**/*.{png,jpg,gif}'],
                dest: 'dist/'
            }]
        }
}
});
grunt.loadNpmTasks('grunt-contrib-imagemin');
grunt.registerTask('default', ['imagemin']);
};

after <strong> grunt imagemin</strong> command : it creates dist folder with compressed files (lossless)

```

Paradigm 3:

~~~
Previous project converts jpeg to compressed jpeg  but at the end it decreases to only 50 to 80 kb.
Where as Webp format compress file to 70 to 85 %( by own cross-check). Standrad document says reduces to 25-34%. 

provided plugin does lossless or lossy? 
~~~

```javascript
WebP is a modern image format that provides superior lossless and lossy compression for images on the web. ... WebP lossy images are 25-34% smaller than comparable JPEG images at equivalent SSIM quality index. Lossless WebP supports transparency (also known as alpha channel) at a cost of just 22% additional bytes.
```

```javascript

Gruntfile.js
module.exports = function (grunt) {
  grunt.initConfig({
    cwebp: {
     
      dynamic: {
        options: {
          q: 50
        },
        files: [{
          expand: true,
          cwd: 'src/', 
          src: ['**/*.{png,jpg,gif}'],
          dest: 'dist/'
        }]
      }
    }
  });
 
  grunt.loadNpmTasks('grunt-cwebp');
  grunt.registerTask('default', ['cwebp']);
};
```
```javascript
package.json
{
  "name": "projectgrunt",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "grunt": "^1.0.1"
  },
  "devDependencies": {
    "grunt-contrib-concat": "^1.0.1",
    "grunt-contrib-imagemin": "^2.0.1",
    "grunt-contrib-watch": "^1.0.0",
    "grunt-cwebp": "^2.1.0"    // new plugin converts jpeg to webp
  }
}
```

<h4> How does a JavaScript engine, such as Rhino, V8, or SpiderMonkey, work? What are some useful resources for understanding them? </h4>

~~~
V8 is faster engine ,its open source.Java script is staic obect-oriented programming (which is slow) it makes dynamic by creating the hidden class objects(which is faster).
~~~

<a href="https://www.quora.com/How-does-a-JavaScript-engine-such-as-Rhino-V8-or-SpiderMonkey-work-What-are-some-useful-resources-for-understanding-them">https://www.quora.com/How-does-a-JavaScript-engine-such-as-Rhino-V8-or-SpiderMonkey-work-What-are-some-useful-resources-for-understanding-them</a>

<p> Interesting Projects already using V8 </p>
<ul><li> chromium <//li>
<li> V8R: Extensible javasript scripting shell </li>
<li> pyV8 : Python running on the top of v8 </li>
</ul>

<h4> The order from "freshness" to "stable": Canary -> Dev -> Beta -> Stable</h4>

~~~
PaulNewman (branch #) mogrifyy $ identify image2.jpg
image2.jpg JPEG 1224x816 1224x816+0+0 8-bit sRGB 108993B 0.000u 0:00.000
~~~

<h4> Google Optimizations : google page spedd -> Insight <strong>normal.css vs optimised/organised.css</strong> </h4>

<a href="http://res.cloudinary.com/duqwfkttw/image/upload/v1503480111/Screen_Shot_2017-08-23_at_2.20.26_AM_jnkfyc.png">best practice: html tag followed by id or class name </a>







