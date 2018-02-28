<template>
    <div class="container">
        <!--  listening on the event emitted in child component -->
        <Header :quoteCount="quotes.length" :maxQuotes="maxQuotes" />
        <NewQuote @quoteAdded="newQuote"/>
        <QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote" />
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Click on quote to delete
                </div>
            </div>
        </div>
    </div>
</template>

<script>

    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
        data() {
            return {
                quotes: [
                    'Some quote to see sth here'
                ],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete some quotes')
                }
                this.quotes.push(quote)
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            }
        },
        components: {
            QuoteGrid,
            NewQuote,
            Header
        }
    }
</script>

<style>
</style>
