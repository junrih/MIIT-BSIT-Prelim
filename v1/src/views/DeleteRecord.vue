<template>
  <div class="wrapper">
    <Sidebar/>
    <div class="main-panel">
      <div class="p-5">
        <h1>Instruction:</h1>
        <p>
          <span>Update Age using the below link:</span><br/>
          <span>https://api.jlipreso.com/miit/public/api/user/deleteByID/{id}</span>
        </p>
        <div class="card w-25">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td style="width: 50px;">ID</td>
                  <td><input v-model="dataid" class="form-control" type="number"></td>
                  <td><button class="btn  btn-danger" @click="deleteRecord()" >Delete</button></td>
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
  import axios from "axios";
  import Swal from "sweetalert2";
  import Sidebar from "@/components/Sidebar.vue";

  export default {
    name: "DeleteRecord",
    components: { Sidebar },
    data() {  
      return{
        dataid: ''
      }
    },
    methods: {
      async deleteRecord(){
        Swal.fire({
        title: "confirmation",
        text: "Delete this user?",
        icon: "warning",
        showCancelButton: true,
        confirmButtonText: "Yes, delete it!",
        cancelButtonText: "No, cancel!",
        reverseButtons: true
      }).then(async(result)=>{
        if (result.isConfirmed){
          await axios.get("https://api.jlipreso.com/miit/public/api/user/deleteByID/" + this.dataid).then(async()=>{
          });
          if (result.isConfirmed) {
            Swal.fire({
              title: "Deleted!",
              text: "Your file has been deleted.",
              icon: "success"
            });
          }
          
        }
      });


      }
      
    }
  }

</script>
