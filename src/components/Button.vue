<template>
    <button 
        :class="primary && 'button-primary'"
        :type="type"
        :autofocus="autofocus"
        :disabled="disabled"
        @click="$emit('click')"
    >
        <div class="content-container">
            <div class="spinner" :style="`visibility: ${spinnerVis}`">
                <div class="double-bounce1"></div>
                <div class="double-bounce2"></div>
            </div>
            <div :style="`visibility: ${textVis}`">
                <slot></slot>
            </div>
        </div>
    </button>
</template>

<script>
    export default {
        name: 'Button',

        props: {
            primary: Boolean,
            autofocus: Boolean,
            disabled: Boolean,
            loading: Boolean,
            type: {
                type: String,
                default: 'button'
            }
        },

        computed: {
            spinnerVis() {
                return this.loading ? 'visible' : 'hidden'
            },
            textVis() {
                return this.loading ? 'hidden' : 'visible'
            }
        }
    }
</script>

<style scoped>
    /* Standard Button */
    button[disabled], button:disabled {
        filter: brightness(25%);
        opacity: 25%;
    }
    button[disabled]:hover, button:disabled:hover {
        filter: brightness(25%);
        opacity: 25%;
    }

    /* Primary Button */
    .button-primary[disabled], .button-primary:disabled {
        filter: brightness(100%);
        opacity: 35%;
    }
    .button-primary[disabled]:hover, .button-primary:disabled:hover {
        background-color: #33C3F0 !important;
        border-color: #33C3F0 !important;
        filter: brightness(100%);
        opacity: 35%;
    }

    .content-container {
        width: max-content;
        position: relative;
    }



    .spinner {
  width: 25px;
  height: 25px;

  position: absolute;
  top: calc(50% - 12.5px);
  left: calc(50% - 12.5px);
  /* margin: 100px auto; */
}

.double-bounce1, .double-bounce2 {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #333;
  opacity: 0.6;
  position: absolute;
  top: 0;
  left: 0;
  
  -webkit-animation: sk-bounce 2.0s infinite ease-in-out;
  animation: sk-bounce 2.0s infinite ease-in-out;
}

.double-bounce2 {
  -webkit-animation-delay: -1.0s;
  animation-delay: -1.0s;
}

@-webkit-keyframes sk-bounce {
  0%, 100% { -webkit-transform: scale(0.0) }
  50% { -webkit-transform: scale(1.0) }
}

@keyframes sk-bounce {
  0%, 100% { 
    transform: scale(0.0);
    -webkit-transform: scale(0.0);
  } 50% { 
    transform: scale(1.0);
    -webkit-transform: scale(1.0);
  }
}
</style>
