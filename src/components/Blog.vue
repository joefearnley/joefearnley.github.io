<template>
  <div>
    <div class="section">
      <div class="container">
        <div class="content">
          <div v-for="post in posts" :key="post.id" class="post-list">
            <div class="post">
              <h2 class=""><a href="#">{{ post.title }}</a></h2>
              <p>{{ post.excerpt }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Blog',
  mounted: function () {
    this.loadPosts();
  },
  data () {
    return {
      posts: []
    }
  },
  methods: {
    loadPosts: function() {
      this.posts = [
        {
          id: 1,
          title: 'Hello World',
          excerpt: 'This is the first post of many.',
          body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ut dolor sit amet quam elementum egestas. Donec luctus, nunc at eleifend ullamcorper, neque est malesuada tellus, nec gravida est sem eget lectus. Pellentesque consectetur tellus felis, eu suscipit lorem pharetra et. Morbi aliquet lorem quis tincidunt molestie. Aliquam volutpat non ante non blandit. Pellentesque maximus sit amet dolor vel scelerisque. Sed malesuada eu metus eu ornare. Morbi eu molestie felis. Donec sodales libero mauris, a pharetra felis dignissim at. Praesent gravida massa sem, at feugiat leo efficitur a.',
          published: true,
          publishedDate: '5/9/2018'
        },{
          id: 2,
          title: 'Building a Twitter Bot with Node.js',
          excerpt: 'Let\'s create a twitter account that tweets out sweet movie posters.',
          body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ut dolor sit amet quam elementum egestas. Donec luctus, nunc at eleifend ullamcorper, neque est malesuada tellus, nec gravida est sem eget lectus. Pellentesque consectetur tellus felis, eu suscipit lorem pharetra et. Morbi aliquet lorem quis tincidunt molestie. Aliquam volutpat non ante non blandit. Pellentesque maximus sit amet dolor vel scelerisque. Sed malesuada eu metus eu ornare. Morbi eu molestie felis. Donec sodales libero mauris, a pharetra felis dignissim at. Praesent gravida massa sem, at feugiat leo efficitur a.',
          published: true,
          publishedDate: '6/9/2018'
        },{
          id: 3,
          title: 'Scrapping a Website using Node.js and It\'s Cheario library',
          excerpt: 'Scrap a website to score a free ebook everyday.',
          body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ut dolor sit amet quam elementum egestas. Donec luctus, nunc at eleifend ullamcorper, neque est malesuada tellus, nec gravida est sem eget lectus. Pellentesque consectetur tellus felis, eu suscipit lorem pharetra et. Morbi aliquet lorem quis tincidunt molestie. Aliquam volutpat non ante non blandit. Pellentesque maximus sit amet dolor vel scelerisque. Sed malesuada eu metus eu ornare. Morbi eu molestie felis. Donec sodales libero mauris, a pharetra felis dignissim at. Praesent gravida massa sem, at feugiat leo efficitur a.',
          published: true,
          publishedDate: '6/9/2018'
        }
      ];
    }
  }
}
</script>