<template>
  <Tree :value="treeData">
    <template v-slot="{ node, path, tree }">
      <span>
        <b @click="tree.toggleFold(node, path)">
          {{node.$folded ? '+' : '-'}}
        </b>
        {{node.text}}
      </span>
    </template>
  </Tree>
</template>

<script setup>
/* eslint-disable */
import 'he-tree-vue/dist/he-tree-vue.css'
import {Tree as HeTree, Fold} from 'he-tree-vue'
const Tree = HeTree.mixPlugins([Fold])

const treeData = [{text: 'node 1'}, {text: 'node 2', children: [{text: 'node 2-1'}]}]
</script>
