<template>
    <div class="btn-group">
        <button v-for="btn in filterButton" :key="btn.name" class="btn"
            :class="[filterName === btn.name ? 'btn-dark' : 'btn-outline-dark']" @click="filterHandler(btn.name)">
            {{ btn.title }}

        </button>
        <!-- <button class="btn" :class="[filterName === 'all' ? 'btn-dark' : 'btn-outline-dark']"
            @click="filterHandler('all')" type="button">Barcha Kinolar</button>
        <button class=" btn" :class="[filterName === 'popular' ? 'btn-dark' : 'btn-outline-dark']"
            @click="filterHandler('popular')" type="button">Mashhur Kinolar</button>
        <button class="btn" type="button" :class="[filterName === 'Viewers' ? 'btn-dark' : 'btn-outline-dark']"
            @click="filterHandler('Viewers')">Sara Kinolar</button> -->
    </div>
</template>

<script >
export default {
    props: {
        updateFilterHandler: {
            type: Function,
            required: true,
        },
        filterName: {
            type: String,
            required: true,
        }
    },
    data() {
        return {
            filterButton: [
                {
                    title: 'Barcha Kinolar',
                    name: 'all'
                },
                {
                    title: 'Mashhur kinolar',
                    name: 'popular'
                },
                {
                    title: 'Sevimli Kinolar',
                    name: 'Viewers'
                },
            ],
            filter: 'all'
        }
    },
    methods: {
        filterHandler(filter) {
            this.filter = filter
            this.updateFilterHandler(this.filter)
        },
    },
}
</script>