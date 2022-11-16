<template>
  <div class="container">
        <div class="row">
            <div class="col-12 col-sm-6 col-md-4 col-lg-3">
                <div class="character" v-for="(item,index) in characters" :key="item.id">
                    <img :src="item.img" :alt="item.name">
                    <h1>{{item.name}}</h1>
                    <h3>{{item.status}}</h3>
                </div>
            </div>
        </div>
  </div>
</template>

<script>
export default {
    name: 'ListCharacters',
    props: ['characters']

};

</script>

<style lang="scss" scoped>


</style>
