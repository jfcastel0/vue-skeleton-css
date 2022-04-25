<template>
    <component :is="size">
        <slot></slot>
    </component>
</template>

<script>
    export default {
        name: 'Heading',
        
        props: {
            size: {
                type: String,
                default: 'h1'
            }
        }
    }
</script>
