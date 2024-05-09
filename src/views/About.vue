<template>
  <div class="about">
    <h1>{{ $t('about') }}</h1>
    <el-button type="primary" @click="() => $router.go(-1)">返回</el-button>
  </div>
</template>
