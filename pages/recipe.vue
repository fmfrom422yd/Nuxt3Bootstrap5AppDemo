<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <NuxtLink to="/#" class="navbar-brand">レシピ</NuxtLink>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <NuxtLink to="/#"  class="text-decoration-none text-reset mx-2">No.1</NuxtLink>
        <NuxtLink to="/kansei" class="text-decoration-none text-reset mx-2">No.2</NuxtLink>
        <NuxtLink to="/recipe" class="text-decoration-none text-reset mx-2">No.3</NuxtLink>
      </div>
    </div>
  </div>
</nav>

  <div class="container text-center my-5">
    <h1>{{ data.title }}</h1>
    <div class="alert alert-primary" role="alert">{{ data.description }}</div>
  </div>
  <div class="container mb-5">
    <div class="card mb-3 mx-auto">
      <div class="row g-0">
        <div class="col-md-5">
          <img
            src="~assets/chiken.webp" class="img-fluid" alt="...">
        </div>
        <div class="col-md-7">
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