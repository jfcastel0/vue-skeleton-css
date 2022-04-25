<template>
    <div class="row">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: 'Row',

        mounted() {
            const colLengths = [
                'one',
                'two',
                'three',
                'four',
                'five',
                'six',
                'seven',
                'eight',
                'nine',
                'ten',
                'eleven',
                'twelve'
            ]

            let columnsDeclared = false

            this.$slots.default.forEach((node) => {
                colLengths.forEach((length) => {
                    if (node.elm.classList.contains(length)) {
                        columnsDeclared = true
                    }
                })
            })

            if (!columnsDeclared) {
                const totalColumns = this.$slots.default.length
                const columns = Math.floor(12 / totalColumns)
                this.$slots.default.forEach((node) => {
                    node.elm.classList.add(colLengths[columns - 1])
                })
            }
        }
    }
</script>
