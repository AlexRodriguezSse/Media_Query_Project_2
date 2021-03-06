# Media_Query_Project_2
### https://alexrodriguezsse.github.io/Media_Query_Project_2/
A begginer project to understand how to apply MediaQuery Source (https://www.youtube.com/watch?v=aook54SsfhY&t=3077s)

### What I used?
  - VS Code: Live Sass Compiler; Live Server
  - HTML; SCSS 

### The project in sentence
   -  Responsive business card 

### What I learned by doing this project?
  - How to use SASS
    - Variables
    - SASS is a super power CSS, more easy to work with


DOCUMENTING THE STEPS I FOLLOWED TO BUILD THE PROJECT, It is important because this way I can internalize the concepts and in the future be able to explain to everyone. 
Notice that the creator of this content has already a written step by step of this project, but I do the same like him but on my own way, only for educational purposes
  -  Here is the source of the creator (https://www.freecodecamp.org/news/learn-css-media-queries-by-building-projects/)
  - 

### 1. Create a container 
    <div class="container"> </div>


### 2. Inside the container. Create the HTML structure, with 3 sections and the classes according for each one section

    <div class="container"> 

      <div class="header"></div>

      <div class="main"></div>

      <div class="footer"></div>

    </div>

### 3. A header logo and the menu 

    <div class="header">
    
        <div class="header__logo"> Alexander Rodríguez</div>
        
            <div class="header__menu">
            
                <div class="header__menu-1"> Home </div>
                <div class="header__menu-2"> Portafolio </div>
                <div class="header__menu-3"> Contacts </div>
                
            </div>
            
     </div>

### 4. Placing The image and the text inside .main div

        <div class="main">

            <div class="main__image"></div>

            <div class="main__text">
                
                <div class="main__text-1">Hello 👋</div>

                <div class="main__text-2">I'm <span>Alexander Rodríguez</span></div>

                <div class="main__text-3">A Web Developer From</div>

                <div class="main__text-4">Cariamanga, Ecuador</div>

            </div>

### 5. Placing The image and the text inside .main div

        <div class="footer">
            
            <div class="footer__instagram">
                <img src="./Imágenes/instagram.png" alt="">
            </div>

            <div class="footer__twitter">
                <img src="./Imágenes/twitter-sign.png" alt="">
            </div>

            <div class="footer__dribble">
                <img src="./Imágenes/dribbble-logo.png" alt="">
            </div>

            <div class="footer__behance">
                <img src="./Imágenes/behance.png" alt="">
            </div>

        </div>

### 6. Now it's time to build in SASS
#### 6.1. Deleting the default window browser style
    * {
        //Placing margin to left and right
        margin: 0px 5px;

        padding: 0px;
        box-sizing: border-box;

        body {
            font-family: 'Courier New', Courier, monospace;
        }
    }
#### 6.2. Setting a style for the window

    .container{
        height: 100vh;
        display: flex; 
        flex-direction: column;
      }

#### 6.3. Nesting all the divs class and his childrens

    .header{
        &__logo {}
        &__menu {}
    }

    .main {
        &__image {}
        &__text {}
    }

    .footer { 
        //a way to nested all the footer childrens (img's) for to Make them smallest 
        [class ^="footer__"] {}
    }

#### 6.4. Applying display flex and his direction to see like a row the header and his menu

    .header{     
        display: flex;
        flex-direction: row;

        &__logo {}
        &__menu {
            display: flex;
            flex-direction: row;
        }
    }

#### 6.5. It´s helpful to set a border and style it to see what we are doing, it's setup is temporary

    .header{

        //border & height styles
        border: 2px solid red;
        height: 10%;

        display: flex;
        flex-direction: row;

        &__logo {}

        &__menu {
            display: flex;
            flex-direction: row;
        }

    }

    .main {

        //border & height styles
        border: 2px solid black;
        height: 80%;

        &__image {}

        &__text {}

    }

    .footer {

        //border & height styles
        border: 2px solid green;
        height: 10%;

        //a way to nested all the footer childrens (img's) for to Make them smallest 
        [class ^="footer__"] {}

    }
#### 6.6. Adding the image into main
      //Image & text will act like a row
        display: flex;
        flex-direction: row;
        
       //border & height styles   
        border: 2px solid black;
        height: 80%;

    &__image {
        //Adding the image
        background-image: url("./Imágenes/Alex_1.jpg");
        // will cover half of screen width
        width: 50%;

        //make image fluid
        background-size: contain;

        //stop image repetition
        background-repeat: no-repeat;

        //position the image
        background-position: left center;
    }

#### 6.8. Styling the text
    &__text {
        // will cover half of screen width
        width: 50%;
        display: flex;
        flex-direction: column;
        
        // To bring it at the center
        justify-content: center;
        align-items:center;

        //To add gaps between texts vertically
        gap: 15px;

        //Font size for Hello
            &-1{
                font-size: 10vw;
            }
        
        //Font size for the other texts
        &-2, &-3, &-4{
            font-size: 5vw;
        }

        //To color the name
            span {
                color: red;
            }
    }
   
### 6.9. The Footer Section
#### 6.9.1. Resizing the Images

    //a way to nested all the footer childrens (img's) for to Make them smallest 
    [class ^="footer__"] {
        img {
            width: 5.3vw;
        }
    }

#### 6.9.2. Positioning the images
    display: flex;
    flex-direction: row;

    //To align icons along x-axis
    align-items: center;

    //Placing image to the right side
    justify-content: flex-end;

    //Gap between icons
    gap: 20px;

    //margin to right side of icons
    margin-right: 10%;

    //to separate the footer from the main
    padding-top: 5vw;

## 7. The Mobile Layout
### 7.1. Media Query at 650px
#### 7.1.1. Header
    .header {
        //To place logo at center
        justify-content: center;

        &__logo {
            font-size: 30px;
        }

        //hiding the menu at mobile device
        &__menu {
            display: none;
        }
    }
#### 7.1.2. Main
##### 7.1.2.1. Image
         &__image {
            //Image size
                height: 200px;
                width: 200px;
                background-size: 100%;

            //To have rounded image
                border-radius: 100%;
                background-position: center;
            }
        }
##### 7.1.2.2. Text
    &__text {
        width: 100%;

        &-1 {
            display: none;
        }

        &-2, &-3, &-4 {
            font-size: 30px;
        }
    }

#### 7.1.3. Footer
    .footer {
        //placing icons along the X-axis
        justify-content: center;
        margin: 0px;

        [class ^="footer__"] {

    //Resizing images for mobile layout
            img {
                width: 45px;
                height: 45px;
            }
        }
    }








