<script lang="ts" setup>
import type { Connection, OnConnectStartParams, VueFlowStore } from '@vue-flow/core'
import { VueFlow, useVueFlow } from '@vue-flow/core'
import CustomInput from './CustomInput.vue'
import CustomNode from './CustomNode.vue'

const { addEdges } = useVueFlow({
  nodes: [
    { id: '0', type: 'custominput', position: { x: 0, y: 150 }, isValidTargetPos: (connection) => connection.target === 'B' },
    {
      id: 'A',
      type: 'customnode',
      position: { x: 250, y: 0 },
      isValidSourcePos: () => false,
    },
    { id: 'B', type: 'customnode', position: { x: 250, y: 150 }, isValidSourcePos: (connection) => connection.target === 'B' },
    { id: 'C', type: 'customnode', position: { x: 250, y: 300 }, isValidSourcePos: (connection) => connection.target === 'B' },
  ],
})
const onLoad = (flowInstance: VueFlowStore) => flowInstance.fitView()
const onConnectStart = ({ nodeId, handleType }: OnConnectStartParams) => console.log('on connect start', { nodeId, handleType })
const onConnectEnd = (event: MouseEvent) => console.log('on connect end', event)

const onConnect = (params: Connection) => {
  console.log('on connect', params)
  addEdges([params])
}
</script>

<template>
  <VueFlow
    :select-nodes-on-drag="false"
    class="validationflow"
    @connect="onConnect"
    @pane-ready="onLoad"
    @connect-start="onConnectStart"
    @connect-end="onConnectEnd"
  >
    <template #node-custominput="props">
      <CustomInput v-bind="props" />
    </template>
    <template #node-customnode="props">
      <CustomNode v-bind="props" />
    </template>
  </VueFlow>
</template>

<style>
@import 'validation.css';
</style>
