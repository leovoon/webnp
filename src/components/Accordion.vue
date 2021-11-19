<template>
  <div class="Expander">
    <div
      class="Expander__trigger"
      :class="isOpen ? 'active':'beforeBorder'"
      @click="isOpen = !isOpen"
    >
      <carbon-chevron-down v-if="!isOpen" class="text-xl mx-2" />
      <carbon-chevron-up v-if="isOpen" class="text-xl mx-2" />
      {{ title }}
    </div>
    <transition :name="animation">
      <div v-show="isOpen" class="Expander__body">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script setup lang='ts'>
const isOpen = ref(false)
defineProps({
  title: {
    type: String,
    default: 'title',
  },
  animation: {
    type: String,
    default: 'bottomToTop',
  },
})
</script>

<style scoped>
.beforeBorder {
    @apply relative;
}
.beforeBorder:before {
@apply absolute border-b-px;
transition: opacity 0.1s linear, transform 0.5s ease-in-out;
  position: absolute;
  border-bottom: 1px solid currentColor;
  content: '';
  width: 100%;
  left: 0;
  bottom: -1px;
}
.beforeBorder:not(:hover)::before {
  transform: scaleX(0);
  opacity: 0;
}
.Accordion {
  background: #fff;
  box-shadow: 0 1px 12px 1PX rgba(0,0,0,0.25);
  overflow: hidden;
}
.Expander__trigger {
  cursor: pointer;
  padding: 0.7rem 0.5rem;
  border-bottom: 1px solid #efefef;
  @apply flex justify-start items-center;
}
.Expander__trigger:hover {
  @apply text-green-600 dark:(text-green-300)
}
.Expander__trigger.active {
  @apply border-b-green-600;
}

.Expander__body {
  padding: 1rem 1.5rem;
  background: #eff0f2;
  @apply dark:(bg-gray-600 bg-opacity-20)  bg-opacity-30 bg-green-200
}

.bottomToTop-enter-active {
  animation: bottomToTop 0.35s forwards;
}

@-moz-keyframes bottomToTop {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}
@-webkit-keyframes bottomToTop {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}
@-o-keyframes bottomToTop {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}
@keyframes bottomToTop {
  0% {
    opacity: 0;
    transform: translateY(100%);
  }
  100% {
    transform: translateY(0);
  }
}

</style>
