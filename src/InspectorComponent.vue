<script setup>
import { ref } from "vue"
import { LINE_WIDTHS } from "./constants.ts";

const currentType = ref('')

const renderEmptyContainer = () => {
  currentType.value = ''
}

const refresh = (obj) => {
  currentType.value = obj.objectType
}
</script>
<template>
  <InspectorComponent :refresh="refresh" class="vjs-flowchart-inspector"
                      :renderEmptyContainer="renderEmptyContainer">

    <div v-if="currentType==='Node'">
      <div class="vjs-inspector-section">
        <div>Label</div>
        <input type="text" vjs-att="label" vjs-focus/>
      </div>
      <div class="vjs-inspector-section">
        <div>Fill Color</div>
        <ColorPickerComponent propertyName="fill"/>
      </div>

      <div class="vjs-inspector-section">
        <div>Text Color</div>
        <ColorPickerComponent propertyName="color"/>
      </div>

      <div class="vjs-inspector-section">
        <div>Outline Color</div>
        <ColorPickerComponent propertyName="outline"/>
      </div>

      <div class="vjs-inspector-section">
        <div>Outline width</div>
        <select vjs-att="outlineWidth" vjs-datatype="integer">
          <option v-for="lw in LINE_WIDTHS" :value="lw">{{lw}}</option>
        </select>
      </div>

    </div>

    <div v-if="currentType==='Edge'">
      <div class="vjs-inspector-section">
        <div>Label</div>
        <input type="text" vjs-att="label"/>
      </div>
      <div class="vjs-inspector-section">
        <div>Line style</div>
        <EdgeTypePickerComponent propertyName="lineStyle"/>
      </div>
      <div class="vjs-inspector-section">
        <div>Markers</div>
        <EdgeTypePickerComponent propertyName="markers"/>
      </div>
      <div class="vjs-inspector-section">
        <div>Line width</div>
        <select vjs-att="lineWidth" vjs-datatype="integer">
          <option v-for="lw in LINE_WIDTHS" :value="lw">{{lw}}</option>
        </select>
      </div>
    </div>

  </InspectorComponent>
</template>
