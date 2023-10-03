<template>
  <div class="header">
    <div class="container mx-auto flex items-center justify-between p-4">
      <div></div>
      <div class="flex items-center space-x-4">
        <button class="bg-gray-200/25 p-2 rounded-lg">
          <BellIcon />
        </button>
        <button class="bg-gray-200/25 p-2 rounded-lg">
          <BookmarkIcon />
        </button>
        <div class="flex items-center bg-gray-200/25 p-2 rounded-lg">
          <SearchIcon />
          <input type="text" placeholder="Search" class="bg-transparent" />
          <div class="dropdown">
            <button class="p-2 rounded-full">
              <DownArrowIcon />
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
<script>
import BellIcon from '../components/icons/BellIcon.vue';
import BookmarkIcon from '../components/icons/BookmarkIcon.vue';
import SearchIcon from '../components/icons/SearchIcon.vue';
import DownArrowIcon from '../components/icons/DownArrowIcon.vue';

export default {
  name: "AppHeader",
  components: {
    BellIcon,
    BookmarkIcon,
    SearchIcon,
    DownArrowIcon,
  }
};
</script>
  
<style scoped>
.header {
  background-color: #cd7228;
}
</style>
  