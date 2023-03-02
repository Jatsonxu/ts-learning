<template>

</template>

<script setup lang="ts">
/**
 * 数据类型定义
 */
// 布尔值
let isDone: boolean = false
// 数字
let decLiteral: number = 6
// 字符串
let name: number = 123
// 数组
let list: number[] = [1, 2, 3]
// 元组 Tuple
let coordinate: [number, number]

// 枚举: 默认从 0 开始为元素编号
enum Color {Red, Green, Blue}

let c: Color = Color.Green
console.log(`枚举 c 的值:${c}`) // 1
// 查找枚举的名字
enum Color2 {Red = 1, Green = 2, Blue = "xx"}

let colorRedName: string = Color2[1]
let colorGreenName: string = Color2[2]
let colorBlueName: string = Color2[3]
console.log({colorRedName, colorGreenName, colorBlueName})
console.log(Color2.Blue) // xx
// {
//   "colorRedName": "Red",
//   "colorGreenName": "Green",
//   "colorBlueName": undefined
// }

// any
let notSure: any = 4

// void
function warnUser(): void {
  console.log("warn message!")
}

// null | undefined
let u: undefined = undefined
let n: null = null
let nameData: string | null | undefined
if (nameData) {
  nameData.toString()
}
// 指定了--strictNullChecks标记
// null和undefined只能赋值给void和它们各自

// never: 永不存在的值的类型
// 总是会抛出异常或根本就不会有返回值的函数表达式或箭头函数表达式的返回值类型
// 变量:永不为真

function error(message: string): never {
  throw new Error(message)
}

// 推断的返回值类型为 never
function fail() {
  return error("Something failed!");
}

// 返回never的函数必须存在无法达到的终点
function infiniteLoop(): never {
  while (true) {
  }
}

// Object: 为什么会有这个类型?
// 表示非原始类型，也就是除number，string，boolean，symbol，null或undefined之外的类型。
// 使用object类型，就可以更好的表示像Object.create这样的API。例如：
// declare function create(o: Object | null): void;
//
//
// create({prop: 0})
// create(null)
// create(42) // Error
// create("string") // Error

/**
 declare声明一个变量
 有一句说法我蛮喜欢的：
 declare就是告诉TS编译器你担保这些变量和模块存在，
 并声明了相应类型，编译的时候不需要提示错误
 */

// 类型断言
let someValue: any = "this is a string"
let strLength: number = (someValue as string).length
let strLength2: number = (<string>someValue).length
</script>

