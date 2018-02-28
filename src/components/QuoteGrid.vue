<template>
    <div class="row">
        <!-- v for loop of that array of quotes -->
        <!--  .native is a event modifier. -->
        <!-- with native it is possible to use event handler on the component and it treats it as it clicks on the template, as the tempkate is linked to the DOM. not the component -->
        <Quote v-for="(quote, index) in quotes" @click.native="deleteQuote">
            {{ quote }} {{ index }}
        </Quote>
    </div>
</template>

<script>

import Quote from './Quote.vue';
export default {
    props: ['quotes'],
    components: {
        Quote
    },
    methods: {
        deleteQuote(index) {
            console.log('index', index)
            this.$emit('quoteDeleted', index);
        }
    }
}
</script>

<style>

</style>
