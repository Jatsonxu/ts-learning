<template>

</template>

<script setup lang="ts">
//  接口 interface
interface SquareConfig {
  color?: string // 可选属性
  width?: number
  readonly x: number // 只读属性
  readonly y: number

  [propName: string]: any; // 额外属性检查
}

interface SearchFunc {
  (source: string, subString: string): boolean
}

let mySearch: SearchFunc
// mySearch = function (src: string, sub: string): boolean {
//   let result = src.search(sub)
//   return result > -1;
// }
mySearch = function (src, sub) {
  let result = src.search(sub)
  return result > -1;
}

type RestArg = number | string | null

function buildRect(name: string, ...restArg: RestArg[]): string {
  return ""
}

buildRect("大魔王", 1, "2", null)
</script>

