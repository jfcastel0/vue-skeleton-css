<template>
    <div :class="`${cols} ${cols === 'one' ? 'column' : 'columns'}`">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'Col',

        props: {
            cols: String
        }
    }
</script>
