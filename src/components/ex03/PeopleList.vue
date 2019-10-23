 <template>
  <div class="card-content">
    <b-field label="แสดงรายชื่อทั้งหมด" v-if="people.length">
       <b-table @dblclick="deletePerson" :data="people" :columns="columns"
        :selected.sync="selected"
        focusable></b-table>
    </b-field>
  </div>
</template>
<script>
import { mapState } from "vuex";

export default {

  created() {
    this.$store.dispatch("people/getPeople");
  },
  
  data() {
    Array.map(child => {
    return {
      thumbnail: child.data.thumbnail,
      title: child.data.title,
    };
  });
  },
  computed: {
    ...mapState("people", ["people"])
  },

   methods: {
    deletePerson() {
      this.$store.dispatch("people/deletePerson", this.selected );
    }
  }


};
</script>