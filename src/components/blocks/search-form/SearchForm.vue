<template>
  <form class="b-search-form">
    <div class="b-search-bar">
      <AppIcon
        class="b-search-icon"
        :icon-class="searchIcon"
      />
      <input
        v-model="searchMsg"
        class="b-search-form__input"
        :type="type"
        :placeholder="placeholder"
      >
      <AppIcon
        v-show="isTyping"
        class="b-search-icon"
        :icon-class="closeIcon"
        @click.native="initMsg"
      />
    </div>
  </form>
</template>

<script>
import AppIcon from '@/components/elements/AppIcon.vue';
export default {
  components: {
    AppIcon,
  },
  data() {
    return {
      searchIcon:'gg-search',
      type: 'string',
      placeholder: '스택/기업을 입력해주세요.',
      closeIcon: 'gg-close-o',
      searchMsg: '',
    };
  },
  computed: {
    isTyping() {
      if (this.searchMsg) {
        return true;
      } else {
        return false;
      }
    },
  },
  methods: {
    initMsg() {
      this.searchMsg = '';
    },
  },
};
</script>

<style lang="scss" scoped>
.b-search-form {
  &__input {
    border: none;
    background-color: #F3F3F3;
    margin: 0;
    padding: 0;
  }
}
.b-search-bar {
  display: grid;
  align-items: center;
  grid-template-columns: 32px 1fr 32px;
  background-color: #F3F3F3;
  height: 100%;
  border-radius: 4px;
}
.b-search-icon {
  margin: 0 auto;
}
// 전체가 100%일때 -40px 
</style>
