<template>
  <span open-helppie-widget>
    <slot></slot>
  </span>
</template>

<script>
export default {
  name: "HelppieWidget",
  props: ["widgetId"],
  created() {
    !(function(e, t, p, a, i) {
      (e.helppieData = e.helppieData || []),
        (e.helppie = function() {
          helppieData.push(arguments);
        });
      const n = t.createElement("script"),
        c = t.getElementsByTagName("script")[0];
      (n.type = "application/javascript"),
        (n.src = "https://cdn.helppie.me/widget.js"),
        (n.async = !0),
        c.parentNode.insertBefore(n, c);
    })(window, document);
  },
  mounted() {
    helppie(this.widgetId);
  },
};
</script>
