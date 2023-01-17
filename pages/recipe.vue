<template>
  <div class="container text-center my-5">
    <h1>{{ data.title }}</h1>
    <div class="alert alert-primary" role="alert">{{ data.description }}</div>
  </div>
  <div class="container mb-5">
    <div class="card mb-3 mx-auto">
      <div class="row g-0">
        <div class="col-md-4">
          <img
            src="@/curry.jpg" alt="...">
        </div>
        <div class="col-md-8">
          <div class="card-body">
            <h2 class="card-title">{{data.headline}}</h2>
            <div class="card-text">
              <ul>
                <li v-for="item in data.material">{{ item.text }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="container mb-5">
    <h2>{{data.headline2}}</h2>
      <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4">
      <div class="col boder p-2" v-for="(todoL,index) in data.todoList.items" :key="todoL.id" :text="todoL.text">
        <div class="msg-wrapper">
          <div class="mb-2">{{todoL.id}}
          </div>
      <p>{{todoL.text}}</p>
        </div>
      </div>
    </div>
  </div>
  <div class="container mb-5">
    <div class="row gx-5">
      <div class="col-sm">
        <h3>{{data.headline3}}</h3>
        <p v-for="point in data.points">{{point.text}}</p>
      </div>
      <div class="col-sm">
        <h3>{{data.headline4}}</h3>
      <p v-for="origin in data.origins">
      {{origin.text}}</p>
        
      </div>
    </div>
  </div>
</template>
<script setup>
  const data = useRecipe()
</script>