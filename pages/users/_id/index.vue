<template>
    <div>
        <h2>This user's id is {{$route.params.id}}</h2>
    </div>
</template>

<script>
    export default {
        validate(context) {
            return /^\d+$/.test(context.params.id)
        }
    }

</script>