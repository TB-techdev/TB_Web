<script lang="ts">
export default {
  props: { contacts: { type: Object, required: true } },
}
</script>

<template>
  <div class="wrapper">
    <div class="padding">
      <h4>{{ $t('Contact Us') }}</h4>
      <div class="contacts" data-test="contacts">
        <div v-for="(value, key) in contacts" :key="key">
          <p>{{ $t(key) }}: {{ value }}</p>
        </div>
      </div>
    </div>
    <hr style="width: 100%" />
    <div class="padding">
      <a href="http://google.com" target="_blank" rel="noopener noreferrer">
        <!-- TODO: change terms and condition to proper one -->
        {{ $t('Terms and Conditions') }}
      </a>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  color: var(--white);
  margin-bottom: 4rem;
}

.contacts {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}

.padding {
  width: 100%;
  padding: 2rem 1rem;
}

@media only screen and (max-width: 768px) {
  .padding {
    padding: 1rem 0;
  }
}
</style>
