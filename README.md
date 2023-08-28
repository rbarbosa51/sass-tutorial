# Sass Tutorial
This tutorial will help you get acquainted with the Sass toolset. 
First thing we need to do is download the starter code:

```sh
git clone https://github.com/rbarbosa51/sass-tutorial.git
```

  Once you clone the repository, go inside its directory and run the following command:
```sh
npm install
```
   This will install a very basic React boilerplate code. It is made with the Vite toolset so it is very fast, small, and looks good for future employers (because you are using the latest and greatest).

Now, install the sass tool:

```sh
npm install -D sass
```
This will install sass inside your project. No configuration needed on your end.
Open the project in VS Code
   
   Take a minute to look at the project structure. Inside the src directory, you will see 3 files App.jsx, Component1.jsx, main.jsx. The .jsx extension just tells the tooling that this is a React file. It is otherwise a regular JavaScript file. The React app entry point is the main.jsx. It is just the render function for the App component. The app component then calls Component1. 

```sh
npm run dev
```

This should have started the dev server. The elements are very plane (we are about to remedy this). Inside the src folder, create a sass folder
Create the following 3 files: App.scss, Component1.scss, and Global.scss

Inside the Global.scss file write the following (you can copy and paste the Google Font: 
```css
/* Import the Google Font - Poppins */
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;1,200;1,300&display=swap');

/*Global Variables*/
$PoppinsFont: 'Poppins';
/*Color variables*/
$pink: hotpink;
$blueish:  #809fff;
$titleColor: #ff8080;
```

   Let me explain. This is the Global file. Inside it will store Global Variables to be imported in the next set of files. First I am importing the Google Font Poppins (I like it). Then we assign it into a variable. Variables in Sass are made by using a $ sign. Example: $variable1: value; We assign $PoppinsFont the ‘Poppins font we just imported. Then we assign global variables for pink, bluish and titleColor.

Inside the App.scss file, write the following:
```css
@import 'Global';

.App {
   font-family: $PoppinsFont;
   padding: 10px 100px;
   h1 {
       color: $titleColor;
       text-align: center;
       width: 500px;
       font-size: 5rem;
       margin: 0 auto;
   }
   p {
       color: $blueish;
   }
}
```
   This styles the App React component. We first need to import the Global file that we just made, so we can use the global variables. Then, we assign padding, and we assign the Google Font to the whole Component. Then we can embed (just like in html) the other elements (h1 and p). We are styling the p element the blueish global variable. All styling is the exact same as CSS.

Inside the Components1.scss file, write the following:
```css
@import "./Global";

.Component1 {
   font-family: $PoppinsFont;
   padding: 10px 100px;
   p {
       color: $pink;
   }
   form {
       text-align: center;
       padding: 0 20px;
       label {
           color: $blueish;
       }
   }
  
}
```
  Again, first we import the Global file so we can get the variables. Look at how the form and label are set up. 

```sh
npm run dev
```

  Now, the web browser can NOT include .SCSS files. The only reason why you can view the results is because the dev server is rendering them for you. Therefore, we need to transpile them to regular a single css file.

```sh
npm run build
```
  You should now see a dist folder. Inside there is an assets folder that has a JavaScript file and a single CSS file. This CSS file is the Sass code transpiled and bundled.

Feel free to experiment or ask me any questions when we see each other in class.
