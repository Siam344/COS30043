<template>
    <section class="reviews">
      <div class="container">
        <h2>Latest Reviews</h2>
        <article class="review-item" v-for="(review, index) in reviews" :key="index">
          <img :src="review.image" :alt="review.title">
          <div class="review-content">
            <h3>{{ review.title }}</h3>
            <p>{{ review.content }}</p>
          </div>
        </article>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: 'Reviews',
    data() {
      return {
        reviews: [
          {
            title: 'Review Title 1',
            content: 'Content for review item 1...',
            image: require('../assets/images/review1.jpg')
          },
          {
            title: 'Review Title 2',
            content: 'Content for review item 2...',
            image: require('../assets/images/review2.jpg')
          },
          {
            title: 'Review Title 3',
            content: 'Content for review item 3...',
            image: require('../assets/images/review3.jpg')
          }
        ]
      }
    }
  }
  </script>
  
  <style scoped>
  /* Add reviews-specific styles here */
  @import url('https://fonts.googleapis.com/css2?family=Archivo:wght@200;300;400;500&family=Audiowide&family=Oswald:wght@200;300;400;500;600&display=swap');

/* variables */
:root{
    --archivo: 'Archivo', sans-serif;
    --audiowide: 'Audiowide', cursive;
    --oswald: 'Oswald', sans-serif;
    --dark-color: #151515;
    --green-color: #5fad05;
    --dark-green-color: #559b04;
    --red-color: #e60012;
    --trans: all 0.3s ease-in-out;
}

*{
    padding: 0;
    margin: 0;
    -webkit-box-sizing: border-box;
            box-sizing: border-box;
    outline: 0;
    text-decoration: none;
}

html{
    font-size: 10px; /* 1rem becomes equal to 10px */
}
body{
    font-size: 1.6rem;
    font-family: var(--archivo);
    background-color: var(--dark-color);
    color: #fff;
}
ul{
    list-style: none;
}
img{
    width: 100%;
    display: block;
}
.container{
    max-width: 1440px;
    margin: 0 auto;
    padding: 0 2rem;
}
.flex{
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
}

.navbar{
    background-color: var(--dark-color);
    color: #fff;
    text-align: center;
    padding: 2rem 0;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 999;
    border-bottom: 5px solid var(--green-color);
}
.navbar .container{
    -webkit-box-pack: justify;
        -ms-flex-pack: justify;
            justify-content: space-between;
}
.navbar-brand{
    font-family: var(--audiowide);
    font-size: 4rem;
    color: #fff;
}
.navbar-brand span{
    color: var(--green-color);
}
.search-form{
    display: none;
}
.navbar-toggler-open, .navbar-toggler-close{
    font-size: 2.8rem;
    background-color: transparent;
    color: #fff;
    border: none;
    cursor: pointer;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.navbar-toggler-open:hover, .navbar-toggler-close:hover{
    opacity: 0.8;
}

.navbar-collapse{
    position: fixed;
    right: -345px;
    top: 0;
    width: 345px;
    background-color: var(--green-color);
    height: 100%;
    padding: 2rem 2rem 2rem 3rem;
    z-index: 999;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.navbar-toggler-close{
    position: absolute;
    right: 2rem;
    top: 2rem;
}
.navbar-nav{
    margin-top: 5rem;
}
.nav-item{
    margin: 2.4rem 0;
    text-align: left;
    font-family: var(--oswald);
}
.nav-link{
    color: #fff;
    text-transform: uppercase;
    font-weight: 600;
    letter-spacing: 2px;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.nav-link:hover, .nav-item-dropdown:hover{
    color: var(--dark-color);
}
.nav-item-dropdown{
    margin-left: 0.5rem;
    cursor: pointer;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.nav-item-dropdown-content{
    max-height: 0;
    overflow: hidden;
}
.nav-item-dropdown-content li{
    margin-bottom: 1rem;
}
.nav-item-dropdown-content li a{
    color: #fff;
    opacity: 0.8;
    letter-spacing: 1px;
    font-weight: 300;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.nav-item-dropdown-content li a:hover{
    opacity: 1;
}

/* nav item dropdown show class */
.show-dropdown{
    max-height: 1000px;
    margin: 1rem 0;
}

/* navbar show class */
.show-navbar{
    right: 0;
}

/* header section */
#header{
    min-height: 100vh;
    margin-top: 85px;
    padding: 2rem 0;
}
.header-item{
    position: relative;
    height: 420px;
}
.header-item img{
    height: 100%;
    -o-object-fit: cover;
       object-fit: cover;
}
.header-item-text{
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    z-index: 2;
    color: #fff;
    background: -webkit-gradient(linear, left bottom, left top, from(rgba(0, 0, 0, 0.8)), color-stop(rgba(0, 0, 0, 0.7)), to(rgba(0, 0, 0, 0)));
    background: -o-linear-gradient(bottom, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0) 100%);
    background: linear-gradient(0deg, rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0) 100%);
    padding: 2.6rem;
}
h1, h2, h3, h4{
    margin: 1.6rem 0;
    line-height: 1.3;
    letter-spacing: 1px;
}
.text{
    margin: 1.6rem 0;
    line-height: 1.5;
    font-weight: 300;
    opacity: 0.9;
    letter-spacing: 1px;
}
.header-item-text small{
    display: block;
    margin: 1rem 0;
    font-size: 1.5rem;
    opacity: 0.6;
    font-style: italic;
}
.header-item-text a{
    background-color: var(--green-color);
    color: #fff;
    padding: 1rem 2rem;
    display: inline-block;
    margin-top: 1rem;
    border-radius: .3rem;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.header-item-text a:hover{
    background-color: var(--dark-green-color);
}

/* news */
.title{
    background-color: var(--red-color);
    padding: 1rem 0;
    color: #fff;
}
.title h2{
    margin: 0;
}

article{
    margin: 2rem 0;
}
.item-img{
    position: relative;
    height: 380px;
    overflow: hidden;
}
.item-img img{
    -o-object-fit: cover;
       object-fit: cover;
    height: 100%;
}
.item-img span{
    position: absolute;
    bottom: 0;
    right: 0;
    display: inline-block;
    padding: 1rem 1.5rem;
    background-color: var(--red-color);
    color: #fff;
}
.item-text{
    padding: 2rem 0;
}
.h1{
    font-size: 2.2rem;
    color: #fff;
    display: block;
    margin-bottom: 1.6rem;
    line-height: 1.3;
    letter-spacing: 1px;
}
.item-text a{
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
.item-text a:hover{
    opacity: 0.8;
}
.category{
    font-family: var(--oswald);
    font-size: 1.6rem;
    display: inline-block;
    text-transform: uppercase;
    padding: 0.4rem 0.8rem;
    background-color: var(--red-color);
    margin-right: 1rem;
    margin-bottom: 1rem;
    border-radius: .2rem;
}
.item-text .date{
    opacity: 0.5;
    margin-top: 1.5rem;
    letter-spacing: 1px;
}

/* videos section */
#videos .title{
    background-color: var(--green-color);
}
#videos article{
    border-bottom: 2px solid var(--green-color);
}
#videos .item-video video{
    width: 100%;
    border-radius: .4rem;
}
#videos .category{
    background-color: var(--green-color);
}

/* promo */
#promo{
    min-height: 100vh;
    margin-bottom: 2rem;
    background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
    background: -o-linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
    background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
    text-align: center;
    -webkit-animation: backgroundChange 10s infinite;
            animation: backgroundChange 10s infinite;
}

@-webkit-keyframes backgroundChange{
    0%, 100%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
    }
    33%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-2.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-2.jpg) center/cover no-repeat;
    }
    66%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-3.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-3.jpg) center/cover no-repeat;
    }
}

@keyframes backgroundChange{
    0%, 100%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
        background: -o-linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-1.jpg) center/cover no-repeat;
    }
    33%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-2.jpg) center/cover no-repeat;
        background: -o-linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-2.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-2.jpg) center/cover no-repeat;
    }
    66%{
        background: -webkit-gradient(linear, left top, left bottom, from(rgba(0, 0, 0, 0.2)), to(rgba(0, 0, 0, 0.3))), url(../resources/images/promo-bg-3.jpg) center/cover no-repeat;
        background: -o-linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-3.jpg) center/cover no-repeat;
        background: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.3)), url(../resources/images/promo-bg-3.jpg) center/cover no-repeat;
    }
}

#promo span{
    text-transform: uppercase;
    font-family: var(--oswald);
    font-size: 3rem;
}
#promo h2{
    font-size: 4rem;
    letter-spacing: 2px;
    font-family: var(--audiowide);
    margin-top: 2rem;
}
#promo .text{
    max-width: 500px;
    margin-right: auto;
    margin-left: auto;
    font-size: 1.8rem;
}
#promo .btn-groups{
    -ms-flex-wrap: wrap;
        flex-wrap: wrap;
    margin-top: 2rem;
}
#promo .btn-groups a{
    margin: 1rem;
    background-color: var(--green-color);
    border-radius: .3rem;
    color: #fff;
    padding: 1.4rem 2rem;
    font-size: 1.8rem;
    text-transform: uppercase;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
#promo .btn-groups a:hover{
    background-color: var(--dark-green-color);
}

/* footer */
#footer{
    background-color: #000;
    padding: 4rem 0;
    text-align: center;
}
#footer a{
    color: #fff;
    -webkit-transition: var(--trans);
    -o-transition: var(--trans);
    transition: var(--trans);
}
#footer a:hover{
    color: var(--red-color);
}
.footer-links-1 ul, .footer-links-2 ul{
    -ms-flex-wrap: wrap;
        flex-wrap: wrap;
}
.footer-links-1 {
    margin: 1.5rem 0;
}
.footer-links-1 h2{
    font-family: var(--oswald);
}
.footer-links-1 ul li{
    margin: 1rem;
}
.footer-links-1 ul li a{
    font-size: 2.4rem;
}
.footer-links-2{
    margin-bottom: 2rem;
}
.footer-links-2 ul li{
    padding: 0 1rem;
    margin: 1rem 0;
    border-right: 1px solid #fff;
}
#footer .text{
    font-size: 1.3rem;
}


/* media qeries */

@media(min-width: 768px){
    /* news & reviews */
    #news article, #reviews article{
        display: grid;
        grid-template-columns: 2fr 3fr;
        -webkit-column-gap: 2rem;
           -moz-column-gap: 2rem;
                column-gap: 2rem;
    }
    #news article .item-img, #reviews article .item-img{
        height: 260px;
    }
    /* popular news */
    #news .news-popular article .item-img{
        height: 160px;
    }
    #news .news-popular .popular-list{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        -webkit-column-gap: 4rem;
           -moz-column-gap: 4rem;
                column-gap: 4rem;
    }
    #news .news-popular .popular-list article:first-child, #news .news-popular .popular-list article:last-child{
        margin-top: 0;
    }

    /* videos */
    #videos .container{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        -webkit-column-gap: 4rem;
           -moz-column-gap: 4rem;
                column-gap: 4rem;
    }
}

@media(min-width: 992px){
    .navbar-toggler-close, .navbar-toggler-open{
        display: none;
    }
    .navbar-collapse{
        width: 100%;
        right: 0;
        position: relative;
        background-color: transparent;
        padding: 0;
    }
    .navbar-nav{
        margin-top: 0;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-align: center;
            -ms-flex-align: center;
                align-items: center;
        -webkit-box-pack: end;
            -ms-flex-pack: end;
                justify-content: flex-end;
    }
    .nav-item{
        position: relative;
        margin: 0 2.4rem 0 0;
    }
    .nav-item-dropdown-content{
        position: absolute;
        top: 100%;
        right: 0;
        z-index: 10;
        background-color: var(--green-color);
        border-radius: .3rem;
    }
    .nav-item-dropdown-content li a{
        opacity: 1;
    }
    .nav-item-dropdown-content li a:hover{
        opacity: 0.8;
    }
    /* nav item dropdown show class */
    .show-dropdown{
        padding: 1.5rem;
    }
    .nav-link:hover, .nav-item-dropdown:hover{
        color: #fff;
        opacity: 0.8;
    }

    /* header */
    .header-content{
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: repeat(2, 1fr);
        gap: 2rem;
    }
    .header-item{
        height: 50vh;
    }

    .header-item:nth-child(1){
        grid-column: 1 / 5;
        grid-row: 1 / 2;
    }
    .header-item:nth-child(2){
        grid-column: 1 / 3;
        grid-row: 2 / 3;
    }
    .header-item:nth-child(3){
        grid-column: 3 / 5;
        grid-row: 2 / 3;
    }
}

@media(min-width: 1200px){
    /* header */
    .header-item:nth-child(1){
        grid-column: 1 / 3;
        grid-row: 1 / 3;
        height: 100%;
    }
    .header-item:nth-child(2){
        grid-column: 3 / 5;
        grid-row: 1 / 2;
    }
    .header-item:nth-child(3){
        grid-column: 3 / 5;
        grid-row: 2 / 3;
    }

    /* news  */
    #news .container{
        display: grid;
        grid-template-columns: auto 400px;
        -webkit-column-gap: 4rem;
           -moz-column-gap: 4rem;
                column-gap: 4rem;
    }
    /* news popular */
    #news .news-popular .popular-list{
        grid-template-columns: repeat(1, 1fr);
        -webkit-column-gap: 0;
           -moz-column-gap: 0;
                column-gap: 0;
    }
    /* video section */
    #videos .container{
        grid-template-columns: repeat(4, 1fr);
    }
    /* reviews section */
    #reviews .container{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
    }
}


/* transition and animation stopper while resizing window */
.resize-animation-stopper *{
    -webkit-animation: none!important;
            animation: none!important;
    -webkit-transition: none!important;
    -o-transition: none!important;
    transition: none!important;
}

@media(max-width: 400px){
    .header-item-text .text{
        display: none;
    }
}
  </style>
  