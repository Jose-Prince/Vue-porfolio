<script>
export default {
    data() {
        return {
            jobs: [
                {name: "Profesor Auxiliar 1", beginDate: "01/24", endDate: "06/24"},
                {name: "Profesor Auxiliar 2", beginDate: "06/24", endDate: "06/24"},
                {name: "Profesor Auxiliar 2", beginDate: "06/24", endDate: "06/24"},
                {name: "Profesor Auxiliar 2", beginDate: "06/24", endDate: "06/24"},
                {name: "Profesor Auxiliar 2", beginDate: "06/24", endDate: "06/24"}
            ]
        }
    }
}
</script>

<template>
    <div id="job-list">
        <h2 class="title-displayment">
            My Jobs
        </h2>
        <div class="divider"></div>
        <div class="job-container">
            <div class="job-list">
                <div v-for="(item, rowIndex) in jobs" :key="rowIndex" >
                    <div id="simple-display">
                        <h3>
                            {{ item.name }}
                        </h3>
                        <div>
                            {{ item.beginDate + "-" + item.endDate }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>

    #simple-display {
        display: flex;
        justify-content: space-between;
        align-items: center;
        border: 0.5px solid #999;
        padding-left: 10px;
        padding-right: 10px;
    }

    #job-list {
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
        max-height: 300px;
        border: white solid 1px;
        border-radius: 15px;
        overflow-y: auto;
    }

    .title-displayment {
        display: flex;
        justify-content: center;
        margin: 0;
    }

    .divider {
        margin: 0;
        width: 100%;
        height: 1.5px;
        background-color: white;
    }

    .job-container {
        display: flex;
        flex-direction: column;
        width: 100%;
        height: 100%;
        max-height: 300px;
        overflow-y: auto;
    }
</style>