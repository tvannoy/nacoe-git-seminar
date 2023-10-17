<template>
  <a :href="href">{{ url }}</a>
</template>

<script>
  export default {
    data() {
        return {
          href: window.location.origin + window.location.pathname,
          url: window.location.host + window.location.pathname
        };
    },
  }
</script>
