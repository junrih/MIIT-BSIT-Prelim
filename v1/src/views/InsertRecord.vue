<template>
  <div class="wrapper">
    <Sidebar/>
    <div class="main-panel">
      <div class="p-5 w-50">
        <h1>Instruction:</h1>
        <p>
          <span>Use the below API link to insert record</span><br/>
          <span>https://api.jlipreso.com/miit/public/api/user/insertRecord/{fname}/{lname}/{age}</span>
        </p>
        <div class="card">
          <div class="card-body">
            <table class="table">
              <tbody>
                <tr>
                  <td>First name</td>
                  <td><input v-model="fname" class="form-control" type="text"></td>
                </tr>
                <tr>
                  <td>Last name</td>
                  <td><input v-model="lname" class="form-control" type="text"></td>
                </tr>
                <tr>
                  <td>Age</td>
                  <td><input v-model="age" class="form-control" type="number"></td>
                </tr>
                <tr>
                  <td></td>
                  <td><button class="btn btn-primary w-100" @click="insertRecord()">Submit</button></td>
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
  import axios from 'axios';
  import Sidebar from "@/components/Sidebar.vue";
  import Swal from 'sweetalert2'

  export default {
    name: "InsertRecord",
    components: { Sidebar },
    data() {
      return{
        fname: '',
        lname: '',
        age: 0
      }
    },
    methods: {
      async insertRecord(){
        await axios.get("https://api.jlipreso.com/miit/public/api/user/insertRecord/"+ this.fname+"/"+this.lname+"/"+this.age).then(async(response)=>{
          console.log(response.data);
          Swal.fire({
          position: "center",
          icon: "success",
          title: "User Inserted",
          showConfirmButton: false,
          timer: 1500
        });
        })
      }
    }
  
  }

</script>
