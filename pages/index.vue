<template>
  <div>
    <v-row>
      <v-col md="4">
        <h2 class="text-center mb-5">Recently Read Book</h2>
        <v-row v-for="(item, index) in recentBooks" :key="index">
          <BookCard
            class="mb-5"
            :bookTitle="item.title"
            :bookAuthor="item.author"
            :bookDescription="item.description"
          >
            <template v-slot:button>
              <v-btn @click.stop="edit(item, index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
      <v-col md="4">
        <h2 class="text-center mb-5">Favourite Book</h2>
        <v-row v-for="(item, index) in favoriteBooks" :key="index">
          <BookCard
            class="mb-5"
            :bookTitle="item.title"
            :bookAuthor="item.author"
            :bookDescription="item.description"
          >
            <template v-slot:button>
              <v-btn @click.stop="edit(item, index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
      <v-col md="4">
        <h2 class="text-center mb-5">Best of the Best</h2>
        <v-row v-for="(item, index) in bestOfTheBest" :key="index">
          <BookCard
            class="mb-5"
            :bookTitle="item.title"
            :bookAuthor="item.author"
            :bookDescription="item.description"
          >
            <template v-slot:button>
              <v-btn @click.stop="edit(item, index)">
                Edit
              </v-btn>
              <v-btn @click.stop="remove(item.category, index)">
                Remove
              </v-btn>
            </template>
          </BookCard>
        </v-row>
      </v-col>
    </v-row>
  </div>
</template>
<script>
import BookCard from "@/components/BookCard.vue"
export default {
  components: {
    BookCard,
  },
  data(){
    return {
      recentBooks: [],
      favoriteBooks: [],
      bestOfTheBest: [],
    }
  },
}
</script>