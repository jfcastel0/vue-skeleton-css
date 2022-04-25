<template>
    <div :class="`${cols} columns offset-by-${offset}`">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'Col',

        props: {
            cols: String,
            offset: String
        }
    }
</script>
