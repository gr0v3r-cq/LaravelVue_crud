<template>
    <div class="card">
        <div class="card-header">¿En que estas pensando ahora?</div>

        <div class="card-body">
            <!-- @if (session('status'))
            <div class="alert alert-success" role="alert">
                {{ session('status') }}
            </div>
            @endif -->


            <form action="" v-on:submit.prevent="newThought()">
                <div class="form-group">
                    <label for="thought"> Ahora estoy pensando en:</label>
                    <input type="text" class="form-control" name="thought" v-model="description">
                </div>
                <button type="submit" class="btn btn-primary">Enviar pensamiento</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {

    data(){
        return{
            description: ''
        }
    },

    methods:{
        newThought(){
            let thought = {
                id: 2,
                description: this.description,
                created_at: '11/11/1111'
            };
            this.$emit('new', thought);
            this.description = '';
            
        }
    },
    mounted() {
        console.log('Component mounted.')
    }
}
</script>
