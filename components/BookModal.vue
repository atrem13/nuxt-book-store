<template>
    <v-dialog max-width="500px" v-model="open">
        <v-card class="p-5">
            <v-card-title primary-title>
                Add Books
            </v-card-title>
            <v-form>
                <v-select
                    :items="categories"
                    v-model="category"
                    label="Select A Category"
                ></v-select>
                <v-text-field
                    v-model="title"
                    label="Enter Book Title"
                ></v-text-field>
                <v-text-field
                    v-model="author"
                    label="Enter Book Author"
                ></v-text-field>
                <v-text-field
                    v-model="description"
                    label="Enter Book Description"
                ></v-text-field>
            </v-form>
            <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn @click.stop="saveBook" color="info">Add</v-btn>
            </v-card-actions>
        </v-card>
    </v-dialog>
</template>
<script>
import { eventBus } from "@/eventBus";
export default {
    created() {
        eventBus.$on("open-add-book-modal", this.open = true);
    },
    data(){
        return{
            open: "false",
            category: "",
            title: "",
            author: "",
            description: "",
            categories: ["Recently read books", "Favourite books", "Best of the best"],

        }
    },
}
</script>