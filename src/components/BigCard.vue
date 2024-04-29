<template>
  <div
    class="bg-white q-pa-lg column"
    style="
      border-radius: 12px;
      gap: 36px;
      box-shadow: rgba(0, 0, 0, 0.12) 0px 15px 24px 0px;
    "
  >
    <div class="column items-center" style="gap: 16px">
      <div style="position: relative">
        <q-avatar style="font-size: 120px">
          <img :src="props.testimoni.avatar" />
        </q-avatar>
        <img
          src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAASCAYAAACuLnWgAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAACPSURBVHgB7ZUxCsJgDIW/hB6gIt0d6nW8gmfwBOoNPJnoLthdkH8W6tMiVBHEpSki/aaEPHghb4hpX8xrsRGe0zGOKjetrN4VR8GEOJIHGzTkTg8MJr9nkoHaxnh2r/W3GW+6K4/tW305W37Sd0Z2OI2J5o+CLy9norHtaBoefG+ZJGJpfgqL+9UqYkgS6xt2UiXTpL5DFAAAAABJRU5ErkJggg=="
          style="position: absolute; bottom: 0px; right: 14px"
        />
      </div>
      <div class="column items-center">
        <div class="text-color-2f" style="font-size: 24px; font-weight: 900">
          {{ props.testimoni.name }}
        </div>
        <div class="text-color-ff" style="font-size: 16px">
          {{ props.testimoni.role }}
        </div>
      </div>
    </div>
    <div class="text-color-f column" style="gap: 4px; font-size: 16px">
      <div class="column items-center" style="gap: 4px">
        <div
          class="q-py-xs q-px-sm"
          style="
            border: solid;
            width: fit-content;
            border-radius: 6px;
            border-color: #c1c5cf;
          "
        >
          {{ props.testimoni.skills[0] }}
        </div>
        <div
          class="q-py-xs q-px-sm"
          style="
            border: solid;
            width: fit-content;
            border-radius: 6px;
            border-color: #c1c5cf;
          "
        >
          {{ props.testimoni.skills[1] }}
        </div>
      </div>
      <div class="row justify-center" style="gap: 4px">
        <div
          class="q-py-xs q-px-sm"
          style="
            border: solid;
            width: fit-content;
            border-radius: 6px;
            border-color: #c1c5cf;
          "
        >
          {{ props.testimoni.skills[2] }}
        </div>
        <div
          class="q-py-xs q-px-sm"
          style="
            border: solid;
            width: fit-content;
            border-radius: 6px;
            border-color: #c1c5cf;
          "
        >
          {{ props.testimoni.skills[3] }}
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Testimoni } from './models';

interface Props {
  testimoni: Testimoni;
}

const props = withDefaults(defineProps<Props>(), {});

defineOptions({
  name: 'BigCard',
});
</script>
