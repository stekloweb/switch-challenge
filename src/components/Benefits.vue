<script>
    import json from '../assets/benefits.json'
    export default{
        data(){
            return{
                data: json
            }
        }
    }
</script>

<template>
    <div class="grid" v-for="benefits in data">
        <div class="card" v-for="benefit in benefits">
            <div>
                <h3 class="card-title">{{benefit.title}}</h3>
                <p class="card-desc">{{benefit.description}}</p>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
    .grid {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-gap: 2em;
    }

    .card {
        border: 1px solid var(--border);
        background-color: white;
        transition: all 333ms ease-in-out;
    }

    .card-title {
        font-size: 1em;
        font-weight: 700;
        color: white;
        background-color: var(--red);
        padding: 0.5em 1em;
        transition: background-color 333ms ease-in-out;
    }

    .card-desc {
        padding: 1.5em 1.25em;
        line-height: 1.25em;
    }

    @media (max-width: 1024px) {
        .grid {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media (max-width: 767px) {
        .grid {
            grid-template-columns: repeat(1, 1fr);
        }
    }

    .dark {
        .card {
            background-color: var(--dark-card-bg);
            color: white;

            &-title {
                background-color: var(--dark-red);
            }
        }
    }
</style>