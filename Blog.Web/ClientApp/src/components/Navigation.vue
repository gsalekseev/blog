<template>
    <nav class="fixed-top navigation">
        <div class="container">
            <button class="navbar-toggler" type="button" v-on:click="toggleMenu">
                Меню
            </button>
            <div class="navbar-collapse" id="main_navigation" v-bind:class="{show: this.menuShown}" >
                <ul class="navbar-list text-uppercase ml-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="#home">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="" href="#about">About Us</a>
                    </li>
                    <li class="nav-item">
                        <a class="" href="#services">Services</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#portfolio">Portfolio</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#testimonials">Testimonials</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#blog">Blog</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#contact">Contect Us</a>
                    </li>
                </ul>
            </div>
        </div>


    </nav>
        
</template>

<script>
    export default {
        name: 'blog-navigation',
        data() {
            return {
                menuShown: false
            }
        },
        mounted() {
            window.addEventListener('scroll', function(e) {
                   const navbar = document.getElementById('main_navigation');
                   if(document.body.scrollTop > navbar.offsetHeight || document.documentElement.scrollTop > navbar.offsetHeight){
                       navbar.classList.add('navbar-shrink');    
                   }else {
                       navbar.classList.remove('navbar-shrink');
                   }
            })
        },
        methods:{
            toggleMenu(){
                this.menuShown = !this.menuShown;
                // some code to filter users
            }    
        }
    };
</script>

<style>

    .show{
        
    }
    .navbar-list{
        flex-wrap: wrap;
        justify-content: space-between;
        padding: .5rem 1rem;
        overflow: hidden;
		transition: background-color 0.5s;
        max-width: 840px;
        display: flex;
        list-style: none;
        align-items: center;
    }

    .navbar-shrink {
        background-color: #212121;
		transition: background-color 0.5s;
    }
    
    .fixed-top {
        position: fixed;
        top: 0;
        right: 0;
        left: 0;
        z-index: 1;
        width: 100%; /* Full width */
    }

    .navbar-collapse {
        flex-basis: 100%;
        flex-grow: 1;
        height: 100%;
        transition: height 2s ease;
    }

    @media (min-width: 992px)  {
        .navbar-nav .nav-link{
            padding-right: .5rem;
            padding-left: .5rem;
        }
    }

    @media (min-width: 767px){
        .navbar-toggler {
            display: none;
        }
    }
    
    .navbar-toggler:not(:disabled):not(.disabled) {
        cursor: pointer;
    }
    
    @media (max-width: 991px) and (min-width: 768px){
        .navbar-dark .navbar-toggler {
            color: rgba(255,255,255,1);
            border-color: rgba(255,255,255,1);
        }
    }
    .navbar-toggler {
        padding: .25rem .75rem;
        font-size: 1.25rem;
        line-height: 1;
        background-color: transparent;
        border: 1px solid transparent;
        border-radius: .25rem;
    }

    .navbar-toggler {
        padding: .25rem .75rem;
        font-size: 1.25rem;
        line-height: 1;
        background-color: transparent;
        border: 1px solid white;
        color: white;
        border-radius: .25rem;
    }
    .nav-item .nav-link {
        padding-right: 0;
        padding-left: 0;
    }
    @media (max-width: 767px){
        .navigation {
            background-color: #333333;
        }
        
        /* Когда меню показано по кнопке, то оно должно отображаться вертикально */
        .show .navbar-list {
            flex-direction: column;
            padding-left: 0;
            margin-bottom: 0;
            list-style: none;
            align-items: center;
            display: list-item;
        }
        
        .navbar-collapse:not(.show) {
            height: 0;
            display: none;
        }

    }
</style>
