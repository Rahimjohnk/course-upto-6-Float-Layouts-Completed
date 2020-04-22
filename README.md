CSS DESIGN STUFF

How to add icon into our project? 
then use 
linea.io and download iconset
and then copy fonts and styles form _basic/_ICONFONT folder and past it into website css file

https://unsplash.com/
# for pictures
https://coverr.co/
# for videos
https://easings.net/en
# for custom Easing functions
https://loremipsum.io/generator/
# for generate big paragraph
https://gs.statcounter.com/screen-resolution-stats
# for screen resolution
https://sizzy.co/
# css properties browser support status
https://caniuse.com/

# to start the project

# code pen link https://codepen.io/anon/pen/eGZKyY?editors=1100
cmd
cd
cd..
exit
cls clear
e:
dir
mkdir folderName createstype folder
cd folderName

create file
type nul> index.js 

E:\GitProjects\CSS_Ex\starter\js>copy index.js ..
 1 file(s) copied. copied form js to starter folder one level above(..).
E:\GitProjects\CSS_Ex\starter\js>move script.js ..
        1 file(s) moved. moved form js to starter folder onle level above(..).
E:\GitProjects\CSS_Ex\starter\js>del index.js
E:\GitProjects\CSS_Ex\starter>rmdir /s js
js, Are you sure (Y/N)? y
E:\GitProjects\CSS_Ex\starter\img>start hero.jpg // to watch the images

E:\GitProjects\newTry\starter> npm init
to create a package.json file

sass advantages code pen project
https://codepen.io/anon/pen/eGZKyY?editors=1100

npm i node-sass --save-dev
to download node-sass as a developer dependancy

In package .json file add scripts for compile sass 
like that 
 "scripts": {
    "compile:sass" : "node-sass sass/main.scss css/style.css -w"
  },

here node-sass is a package 

and sass/main.scss is a input scss file to converted to css

and css/style.css is output pure css flle
and -w is a watch flag to listening current changes .

npm run compile:sass 
for compile sass code 

to add live server on globally
npm i live-server -g
E:\GitProjects\newTry\starter>npm run compile:sass
E:\GitProjects\CSS_Ex\starter>live-server

for concate 2(css/font-icon.css css/style.comp.css) or more compiled css files
here we concate style.comp.css and font-icon.css file
npm i concat --save-dev
if we concat all css file into one means then of http req is enough to download file.

 npm i autoprefixer  --save-dev
in order to it work we need another one
npm i postcss-cli  --save-dev

"scripts": {
    "compile:sass": "node-sass sass/main.scss css/style.css -w",
    "compileWithoutWatch:sass": "node-sass sass/main.scss css/style.comp.css",
    "concat:css": "concat -o css/style.concat.css css/font-icon.css css/style.comp.css",
   "prefix:css": "postcss --use autoprefixer -b \"last 10 versions\" css/style.concat.css -o css/style.prefix.css",
"compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
"build:css": "npm-run-all compileWithoutWatch:sass concat:css prefix:css compress:css"

  },

"prefix:css": "postcss --use autoprefixer -b \"last 10 versions\" css/style.concat.css -o css/style.prefix.css"


postcss --use autoprefixer : - use postcss package and with autoprefixer

-b \"last 10 versions\"  :-  last 10 versions of browser support.

css/style.concat.css:- input file
 -o:- output
 css/style.prefix.css" :- output file

npm run compileWithoutWatch:sass
it creates compiledCSS code

npm run concat:css
it concat compiledCSS and font-icon.css file and create style.cancat.css file

npm run prefix:css
it add -webkit- prefix into style.cancat.css files properties which required browser supports.

"compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed"

npm run compress:css
it actually compress the css and node-sass package will does for us this job using
 --output-style compressed

 npm i npm-run-all --save-dev"
build:css": "npm-run-all compileWithoutWatch:sass concat:css prefix:css compress:css"

npm run build:css :- 
it does all task for us and give the end result file
that is compressed css file.

"scripts": {
"devserver": "live-server",
 "start": "npm-run-all --parallel devserver compile:sass",
}

npm run start :- it does two(devserver ,compile:sass) task parallely using --parallel command .



