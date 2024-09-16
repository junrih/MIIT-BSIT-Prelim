<template>
  <div class="wrapper">
    <Sidebar/>
    <div class="main-panel">
      <div class="p-5 w-75">
        <h1>Instruction:</h1>
        <p>
          <span>Update Age using the below link:</span><br/>
          <span>https://api.jlipreso.com/miit/public/api/user/updateRecord/{id}/{age}</span>
        </p>
        <div class="card">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td style="width: 50px;">ID</td>
                  <td><input v-model="dataid" class="form-control" type="text"></td>
                  <td style="width: 50px;">Age</td>
                  <td><input v-model="age" class="form-control" type="number"></td>
                  <td><button class="btn  btn-primary" @click="updateAge()">Update Age</button></td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">

  import Sidebar from "@/components/Sidebar.vue";
import axios from "axios";
import Swal from "sweetalert2";

  export default {
    name: "EditRecord",
    components: { Sidebar },
    data(){
      return{
        dataid: '',
        age: 0
      }
    },
    methods: {
      async updateAge(user: any){
        await axios.get ("https://api.jlipreso.com/miit/public/api/user/updateRecord/"+this.dataid+"/"+this.age).then(async(response)=>{
          Swal.fire({
              title: "Do you want to save the changes?",
              showDenyButton: true,
              showCancelButton: true,
              confirmButtonText: "Save",
              denyButtonText: `Don't save`
          }).then((result) => {
 
          if (result.isConfirmed) {
            Swal.fire("Saved!", "", "success");
          } else if (result.isDenied) {
            Swal.fire("Changes are not saved", "", "error");
  }
});
        });
      }
    }
  }

</script>
