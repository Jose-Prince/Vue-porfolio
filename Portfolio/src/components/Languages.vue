<script>
export default {
    data() {
        return {
            langs: [
                { image: "https://upload.wikimedia.org/wikipedia/commons/thumb/4/4c/Typescript_logo_2020.svg/1200px-Typescript_logo_2020.svg.png", percentage: 93 },
                { image: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Unofficial_JavaScript_logo_2.svg/800px-Unofficial_JavaScript_logo_2.svg.png", percentage: 93 },
                { image: "https://www.manualweb.net/img/logos/java.png", percentage: 88 },
                { image: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Python.svg/640px-Python.svg.png", percentage: 90 },
                { image: "https://upload.wikimedia.org/wikipedia/commons/7/74/Kotlin_Icon.png", percentage: 85 },
                { image: "https://static-00.iconduck.com/assets.00/file-type-css-icon-451x512-eftbqujz.png", percentage: 69 },
                { image: "https://www.freecodecamp.org/news/content/images/2021/01/rust-mascot.png", percentage: 59 },
            ]
        };
    },
    methods: {
        getProgressColorClass(percentage) {
            if (percentage < 30) {
                return 'progress-red';
            } else if (percentage < 70) {
                return 'progress-orange';
            } else {
                return 'progress-green';
            }
        }
    }
};
</script>

<template>
    <div class="languages-display">
        <div v-for="(item, rowIndex) in langs" :key="rowIndex" class="language-row">
            <div class="image-item">
                <img :src="item.image" alt="language" class="image-style"/>
            </div>
            <div class="percentage-item">
                <div class="progress-container">
                    <progress :value="item.percentage" max="100" :class="getProgressColorClass(item.percentage)"></progress>
                    <span class="tooltip">{{ item.percentage }}%</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.languages-display {
    display: flex;
    flex-direction: column;
    width: 100%;
    gap: 5px;
 
}

.language-row {
    display: flex;
    gap: 10px;
}

.image-style {
    height: 30px;
}

.image-item {
    display: flex;
    justify-content: center;
    min-width: 40px;
}

.percentage-item {
    display: flex;
    align-items: center;
    width: 100%;
}

.progress-container {
    position: relative;
    width: 95%;
}

progress {
    width: 100%;
    height: 20px;
    border-radius: 5px;
    appearance: none;
    overflow: hidden;
}

.tooltip {
    position: absolute;
    top: -2px; /* Ajusta para mover el tooltip encima de la barra */
    left: 50%;
    transform: translateX(-50%);
    color: black;
    padding: 3px 7px;
    border-radius: 3px;
    font-size: 12px;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.2s ease-in-out;
}

.progress-container:hover .tooltip {
    opacity: 1;
    visibility: visible;
}

.progress-red::-moz-progress-bar {
    background-color: red;
}

.progress-orange::-moz-progress-bar {
    background-color: orange;
}

.progress-green::-moz-progress-bar {
    background-color: green;
}
</style>
