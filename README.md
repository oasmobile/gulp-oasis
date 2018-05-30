## What is gulp artisan?
Gulp artisan is a tool which can optimize website based on json configration files
## What can gulp artisan do?
- **Images** Compress images using gifsicle mozjpeg pngquant svgo
- **Sprites** Generate Sprites
- **CSS** Minify css
- **JS** Minify js
- **Console** Detect website console errors in chrome
## Install
```
//install node 
https://nodejs.org  
//install gulp  
npm install --global gulp  
//install gulp artisan
npm install --global gulp-artisan
```
## Command  
```
gulp-artisan  
--run compress //compress images
--run atlas //generate sprites
--run minify_css //minify css
--run minify_js //minify js
--run console //detect website console errors in chrome
--config xxxx.json //specify json
--cwd //change directory
```
### Default configuration file
```
sample compress_images.json
path: images/** //recursive directory
path: !images/a.png //ignore file
gifsicle: [https://www.npmjs.com/package/imagemin-gifsicle]
mozjpeg: [https://www.npmjs.com/package/imagemin-mozjpeg]
pngquant: [https://www.npmjs.com/package/imagemin-pngquant]
svgo: [https://www.npmjs.com/package/imagemin-svgo]
{
    "images1": {
        "input" : "images2/*",
        "output": "dist/images2"
    }
}
{
    "images1": {
        "input"   : "images2/*",
        "output"  : "dist/images2",
        "enabled" : false,
        "gifsicle": {
            "interlaced": true
        },
        "mozjpeg" : {
            "quality": 90
        },
        "pngquant": {
            "quality": "60-80"
        },
        "svgo"    : {
            "plugins": [
                {
                    "removeViewBox": false
                }
            ]
        }
    }
}
sample atlas_sprites.json
image_path_prefix: image path prefix in generated css file
{
    "buttons1": {
        "input"       : "buttons1/*",
        "output_image": "src/image",
        "output_css"  : "src/css",
        "image_name"  : "atlas_buttons1.png",
        "css_name"    : "atlas_buttons1.css"
    },
    "buttons2": {
        "input"            : "buttons1/*",
        "output_image"     : "src/image",
        "output_css"       : "src/css",
        "image_name"       : "atlas_buttons1.png",
        "css_name"         : "atlas_buttons1.css"
        "image_path_prefix": "../buttons1/"
    }
}
sample minify_css.json
{
    "css1": {
        "input" : "css1/*",
        "output": "css1-minify"
    },
    "css2": {
        "input" : "css2/*",
        "output": "css2-minify",
        "concat": "css2.min.css"
    },
    "css3": {
        "input" : ["css3/a.css","css3/b.css"],
        "output": "css3-minify",
        "concat": "css3.min.css"
    }
}
sample minify_js.json
{
    "js1": {
        "input" : "js1/*",
        "output": "js1-minify"
    },
    "js2": {
        "input" : "js2/*",
        "output": "js2-minify",
        "concat": "js2.min.js"
    },
    "js3": {
        "input" : ["js3/a.js","js3/b.js"],
        "output": "js3-minify",
        "concat": "js3.min.js"
    }
}
sample console.json
{
    "narutoen": [
        "http://naruto.oasgames.com/en/articlelist/news",
        "http://naruto.oasgames.com/en/strategy/gameStrategy"
    ]
}
```
## License

[MIT License](https://en.wikipedia.org/wiki/MIT_License)
