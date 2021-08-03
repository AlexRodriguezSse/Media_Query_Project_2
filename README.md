# Media_Query_Project_2
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

#### 6.5. It´s helpful to set a border and style it to see what we are doing



