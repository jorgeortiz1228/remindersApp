<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Reminder</label>
                <textarea rows="3" class="form-control" v-model="quote"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Reminder</button>
            </div>
        </form>
    </div>
</template>

<script>


export default {
    data: function() {
        return {
            quote: ''
        };
    },
    methods: {
        createNew() {
            this.$emit('quoteAdded', this.quote);
            this.quote = '';
        }
    }
}
</script>