<template>
    <div>
        Jokes!
    </div>
</template>

<script>
import axios from 'axios'

export default {
    data() {
        return {
            jokes: []
        }
    },

    async created() {
        const config = {
            headers: {
                Accept: 'application/json'
            }
        };

        try {
            const res = await axios.get('https://icanhazdadjoke.com/search', config);
            this.jokes = res.data.results;
        } catch (err) {
            console.log(err)
        }
    },

    head() {
        return {
            title: 'Dad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: "We've cornered the dad joke market"
                }
            ]
        }
    }
}
</script>

<style>

</style>