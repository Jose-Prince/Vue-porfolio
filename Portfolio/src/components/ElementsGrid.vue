<script>

</script>

<template>
    <div class="grid-element">
        <div class="grid-item">
            <div class="container container-style">
                <img class="position-img" src="../assets/mail_icon.jpg"/>
            </div>
            <div class="first-back back-style"></div>
        </div>
        <div class="grid-item">
            <div class="container container-style">
                <img class="position-img" src="../assets/cv_icon.jpg"/>
            </div>
            <div class="back back-style"></div>
        </div>
        <div class="grid-item">
            <a class="container container-style" href="https://github.com/cmd-AJ/Ing-Software/commit/71c1edbf92d643d06ffeb49c79b0413b19e393eb">
                <img class="position-img" src="../assets/github_icon.jpg"/>
            </a>
            <div class="back back-style"></div>
        </div>
        <div class="grid-item">
            <div class="container container-style">
                <img class="position-img" src="../assets/linkedin_icon.jpg"/>
            </div>
            <div class="last-back back-style"></div>
        </div>
    </div>
</template>

<style>
    :root {
        --width-square-size: 12vw
    }

    .grid-element {
        display: grid;
        grid-template-rows: 25% 25% 25% 25%;
        height: inherit;
    }

    .grid-item {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .container {
        position: absolute;
        width: 80%;
        height: 80%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .back {
        position: absolute;
        width: 40%;
        height: 100%;
    }

    .first-back {
        position: absolute;
        width: 40%;
        height: 100%;
        margin-top: 50%;
    }

    .last-back {
        position: absolute;
        width: 40%;
        height: 100%;
        margin-bottom: 50%;
    }

    .container-style {
        position: absolute;
        background-color: black;
        border: white solid 1px;
        z-index: 2;
        outline-width: 1px;
        outline-offset: 0;
        outline-style: solid;
        transition: width 0.3s ease, height 0.3s ease;
    }

    .back-style {
        z-index: 1;
    }

    .container-style:hover {
        background-color: black;
        width: 105%;
        height: 105%;
        animation: animateOutline 2s ease-in-out forwards
    }

    .position-img {
        width: 50%;
        height: 100%;
    }

    @media screen and (max-width: 814px) {
        .position-img {
            height: 100%;
            width: 100%;
        }
    }

    @keyframes animateOutline {
        0% {
            outline-width: 1px;
            outline-offset: 0;
            outline-color: rgba(0, 130, 206, 0);
          }
        
          10% {
            outline-color: rgba(0, 130, 206, 0.75);
          }
        
          /* The animation finishes at 50% */
          50% {
            outline-width: 7px;
            outline-offset: 4px;
            outline-color: rgba(0, 130, 206, 0);
            border-color: rgba(0, 130, 206, 0.75);
          }
        
          100% {
            outline-width: 7px;
            outline-offset: 4px;
            outline-color: rgba(102, 102, 102, 0);
            border-color: rgba(0, 130, 206, 0.75);
          }
    }
</style>