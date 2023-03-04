<template>

</template>

<script setup lang="ts">

// ※ 声明函数

/**
 * 声明一个 SUM 函数
 */

interface SumFun {
  (n1: number, n2: number): number
}

let sumFun: SumFun
sumFun = function (n1, n2) {
  return n1 + n2
}
// Anonymous function
const sumFun2: SumFun = (n1, n2) => n1 + n2

// Named Function
function sumFun3(n1: number, n2: number): number {
  return n1 + n2
}


function foo(type: string = "normal", name: string, age?: number, ...rest: string[]): any {

}

interface Deck {
  suits: string[];
  cards: number[]
}

interface Response<T> {
  code: number;
  message: string;
  data: T
}

interface UserResponse {
  username: string;
  password: string;

  [propName: string]: any;
}

let data: Response<UserResponse> = {
  code: 200,
  message: "success",
  data: {
    username: "admin",
    password: "123456"
  }
}


interface Shape {
  // 宽度
  width: string;
  height: string;
}

interface Square extends Shape {
  fill: string;
}

let square: Square = {
  width: "100",
  height: "100",
  fill: "100",
}

interface External extends String {
  length: number
}

function foo2<T extends External>(name: T): T {
  console.log(name.length)
  return name;
}

function isString(pet: string | number): pet is string {
  return (<string>pet) !== undefined
}


namespace AdminUser {
  export interface Profile {
    username: string;
    password: string;
  }
}
// let user: AdminUser.Profile = {
//   xx: 123
// }
//
// user.password = 123
</script>
