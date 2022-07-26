<template>
  <transition :name="transition">
    <div v-show="visible" class="carouselSlide">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      index: 0,
    };
  },
  mounted: function() {
  },
  computed: {
    transition() {
      return 'slide-' + this.$parent.direction
    },
    visible() {
      return this.index === this.$parent.index;
    },
  },
};
</script>

<style>
.slide-right-enter-active {
  animation: slideRightIn 0.5s;
}

.slide-right-leave-active {
  position: absolute;
  top: 0;
  left: 0;
  animation: slideRightOut 0.5s;
}

.slide-left-enter-active {
  animation: slideLeftIn 0.5s;
}

.slide-left-leave-active {
  position: absolute;
  top: 0;
  left: 0;
  animation: slideLeftOut 0.5s;
}

@keyframes slideRightIn {
  from {
    transform: translateX(100%);
  }

  to {
    transform: translateX(0);
  }
}

@keyframes slideRightOut {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(-100%);
  }
}


@keyframes slideLeftIn {
  from {
    transform: translateX(-100%);
  }

  to {
    transform: translateX(0);
  }
}

@keyframes slideLeftOut {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(100%);
  }
}
</style>
