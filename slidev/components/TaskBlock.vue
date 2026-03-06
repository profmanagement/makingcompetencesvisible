<template>
  <div :class="['scholarly-block', 'block-task', { 'block-compact': compact }]">
    <div v-if="title" class="block-header">
      <span class="block-title">{{ title }}</span>
    </div>
    <div class="block-content">
      <slot />
    </div>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title?: string
  compact?: boolean
}

withDefaults(defineProps<Props>(), {
  compact: false
})
</script>

<style scoped>
.scholarly-block {
  margin: 1rem 0;
  border-radius: 0.5rem;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.scholarly-block.block-compact {
  margin: 0.5rem 0;
}

.block-header {
  padding: 0.5rem 1rem;
  font-weight: 600;
  font-size: 1rem;
}

.block-content {
  padding: 0.75rem 1rem;
  line-height: 1.6;
}

.block-content :deep(p) {
  margin: 0.5rem 0;
}

.block-content :deep(p:first-child) {
  margin-top: 0;
}

.block-content :deep(p:last-child) {
  margin-bottom: 0;
}

.block-content :deep(ul),
.block-content :deep(ol) {
  margin: 0.5rem 0;
  padding-left: 1.5rem;
}

/* Task (grüne Pastellfarbe) */
.block-task .block-header {
  background: linear-gradient(to right, #34d399, #6ee7b7);
  color: #064e3b;
}

.block-task .block-content {
  background: rgba(52, 211, 153, 0.1);
  border: 1px solid rgba(52, 211, 153, 0.3);
  border-top: none;
}

/* Without title - single colored block */
.scholarly-block:not(:has(.block-header)) .block-content {
  border-radius: 0.5rem;
  border-top: 1px solid;
}

.block-task:not(:has(.block-header)) .block-content {
  border-left: 4px solid #6ee7b7;
}
</style>
