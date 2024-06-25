<template>
  <div>
    <HeaderComp />
    <!-- heaeder -->
    <div class="container_baner_project">
      <div class="baner_project">
        <div class="title_baner_project_container">
          <div class="title_baner_project">
            <h2 class="header_baner_blog">Наш проект</h2>
            <div class="text_baner_blog">
              <a href="#">Домой</a>
              <span>/</span>
              <a href="#">Проект</a>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- main -->
    <CategoryFilterProject :selectedCategory="selectedCategory" @category-selected="filterItems"/>
    <div class="container_project">
      <div class="progect_item_card" v-for="item in filteredItems" :key="item.id">
        <img :src="item.image" alt="">
        <div class="sub_content_project">
            <div class="sub_content_left">
              <h3>{{ item.title }}</h3>
              <span>{{ item.desc_text }}</span>
            </div>
            <div class="sub_content_right">
              <a href="#"></a>
            </div>
          </div>
      </div>
    </div>
      <PaginationComp />
    <FooterComp />
  </div>
</template>

<script>
import CategoryFilterProject from './CategoryFilterProject.vue'
import FooterComp from './FooterComp.vue'
import HeaderComp from './HeaderComp.vue'
import PaginationComp from './PaginationComp.vue'

export default {
  name: 'ProjectComp',
  data () {
    return {
      items_project: [
        {
          id: 1,
          image: '/img_project/project_badroom_1.jpeg',
          title: 'Минималистичная спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 2,
          image: '/img_project/project_badroom_2.jpeg',
          title: 'Минималистичная спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 3,
          image: '/img_project/project_badroom_3.jpeg',
          title: 'Классическая спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 4,
          image: '/img_project/project_badroom_4.jpeg',
          title: 'Современная спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 5,
          image: '/img_project/project_badroom_5.jpeg',
          title: 'Минималистичный прикроватный столик',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 6,
          image: '/img_project/project_badroom_6.jpeg',
          title: 'Столы и столики',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 7,
          image: '/img_project/project_badroom_7.jpeg',
          title: 'Современная спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        },
        {
          id: 8,
          image: '/img_project/project_badroom_8.jpeg',
          title: 'Современная спальня',
          desc_text: 'Декор / Планировка',
          category: 'Спальня'
        }
      ],
      selectedCategory: 'Спальня'
    }
  },
  computed: {
    filteredItems () {
      if (this.selectedCategory === 'Все виды') {
        return this.items_project
      }
      return this.items_project.filter(item => item.category === this.selectedCategory)
    }
  },
  methods: {
    filterItems (category) {
      this.selectedCategory = category
    }
  },
  components: { HeaderComp, FooterComp, PaginationComp, CategoryFilterProject }
}
</script>

<style lang="scss" scoped>
.baner_project {
  background-image: url(/public/img_project/header_photo_project_badroom.jpeg);
  width: 100%;
  height: 356px;
  background-repeat: no-repeat;
  background-position: center;
  margin-top: 20px;
  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.title_baner_project_container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  width: 500px;
  height: 160px;
  border-radius: 37px 37px 0 0;
}
.container_project {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  padding: 20px;
  max-width: 1200px;
  margin: 60px auto 0;
}
</style>
