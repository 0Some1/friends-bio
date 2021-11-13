<template>

  <div class="wrap mt-4">
    <div class="bg-white w-75 yyy m-auto ">
      <b-form @submit="onSubmit" @reset="onReset">
        <b-form-group id="input-group-1" label="Name:" label-for="input-1">
          <b-form-input
              id="input-1"
              v-model="comment.name"
              type="text"
              placeholder="Enter name"
              required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Your comment:" label-for="input-2">
          <b-form-input
              id="input-2"
              v-model="comment.text"
              placeholder="Enter text"
              required
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" class="mr-2" variant="primary">Submit</b-button>
        <b-button type="reset" variant="danger">Reset</b-button>
      </b-form>
      <b-card class="mt-3" header="Comments :">
        <div v-for="comment1 in comments" class="w-100">
          <b-row class="align-content-between">
            <b-col class="rounded"  sm="12"><b>{{ comment1.name }} </b></b-col>
            <div class="w-100"></div>
            <b-col class=" rounded" lg="8" md="6" sm="6">{{ comment1.text }}</b-col>
            <b-col class="ml-auto" md="auto" sm="auto">
                <b-button class="mr-1" variant="danger" @click="DeleteComment($event,comment1.ID)">Delete</b-button>
                <b-button variant="secondary" @click="OpenModal($event,comment1.ID)">Edit</b-button>
            </b-col>
          </b-row>

        </div>
      </b-card>
    </div>


    <b-modal @ok="UpdateComment"  id="modal-center" centered title="Edit Comment:">
      <b-form-input
          v-model="comment2.name"
          placeholder="Enter name"
          required
          class="mb-2"
      ></b-form-input>
      <b-form-input
          id="input-2"
          v-model="comment2.text"
          placeholder="Enter text"
          required
      ></b-form-input>
    </b-modal>

  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      comment: {
        id:0,
        name: '',
        text: '',

      },
      comment2: {
        id:0,
        name: '',
        text: '',

      },
      comments: [],
    }
  },
  methods: {
    onSubmit(event) {

      event.preventDefault()
      axios.post('https://simple-crud998.herokuapp.com/comment', this.comment)
          .then(response => {
            this.getComments()
          })
          .catch(error => console.log(error))
    },
    onReset(event) {
      event.preventDefault()
      this.comment.name = ''
      this.comment.text = ''
    },
    getComments() {
      axios.get('https://simple-crud998.herokuapp.com/comment')
          .then(response => {
            this.comments = response.data
          })
          .catch(error => console.log(error))
    },
    DeleteComment(event,id) {
      console.log(id)
      event.preventDefault()
      axios.delete('https://simple-crud998.herokuapp.com/comment/' + id)
          .then(response => {
            this.getComments()
          })
          .catch(error => console.log(error))
    },
    UpdateComment() {
      console.log("update:"+ this.comment.id)
      axios.put('https://simple-crud998.herokuapp.com/comment/' + this.comment2.id,this.comment2)
          .then(response => {
            this.getComments()
            this.comment2 = {}
          })
          .catch(error => console.log(error))
    },
    OpenModal(event, id){
      this.comment2.id = id;
      this.$bvModal.show('modal-center')
    }
  },
  created() {
    this.getComments()
  }
}
</script>

<style scoped>
.yyy {
  text-align: left;
}

</style>