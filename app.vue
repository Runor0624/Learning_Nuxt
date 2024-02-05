<script setup lang="ts"> {/* 스크립트는 타입스크립트를 사용할꺼다. */}
interface Post {
  userId: number
  id: number 
  title: string
  body: string 
}

const { data } = await useFetch<Post[]>('https://jsonplaceholder.typicode.com/posts') 
</script>

<template>
  <div>
    <div v-for="post in data" :key="post.id"> <!-- v-for : React의 map 처럼 반복하여 렌더링하는 역할을 담당함.-->
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>



