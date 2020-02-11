<template>
  <div id="app">
    <div id="header-group">
        <h1>Sign-up Member</h1>
    </div>
    <div id="form-section" v-if="switchDisplay">
        <div class="form-group">
            <label for="input-first-name">First Name :</label>
            <input type="text" id="input-first-name" v-model="name.first">
        </div>
        <div class="form-group">
            <label for="input-last-name">Last Name :</label>
            <input type="text" id="input-last-name" v-model="name.last">
        </div>
        <div class="form-group">
            <label for="input-email">Email :</label>
            <input type="email" id="input-email" v-model="email">
        </div>
        <div class="form-group">
            <label for="input-password">Password :</label>
            <input type="password" id="input-password" v-model="password">
        </div>
        <div class="form-group">
            <label for="input-password">Save to Database :</label>
            <div class="checkbox-group">
                <input type="radio" name="saveDB" id="save-db-yes" value="Yes" v-model="isSave">
                <label for="save-db-yes">Yes</label>
            </div>
            <div class="checkbox-group">
                <input type="radio" name="saveDB" id="save-db-no"  value="No" v-model="isSave">
                <label for="save-db-no">No</label>
            </div>
        </div>
        <button class="btn btn-submit" @click="submitForm">Sign-up</button>
        <button class="btn btn-reset" @click="resetForm">Reset</button>
    </div>
    <div id="result-form" v-else>
        <div class="alert-success">
            <p>Thank you for Sign-up :)</p>
        </div>
        <div class="result-group">
            <h4>Full Name : </h4>
            <p>{{ fullName  }}</p>
        </div>
        <div class="result-group">
            <h4>Email : </h4>
            <p>{{ email  }}</p>
        </div>
        <div class="result-group">
            <h4>Password : </h4>
            <p>{{ password  }}</p>
        </div>
        <div class="result-group">
            <h4>Save to Database : </h4>
            <p>{{ isSave }}</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            name:{
                first: '',
                last: ''
            },
            email:'',
            password:'',
            isSave: '',
            switchDisplay: true       
        }
    },
    computed:{
        fullName(){
            return `${this.name.first} ${this.name.last}`;
        }
    },
    methods:{
        submitForm(){
            this.switchDisplay = false;
        },
        resetForm(){
            this.name = {
                first: '',
                last: ''
            }
            this.email = '';
            this.password = '';
            this.isSave = '';
        }
    }
}
</script>

<style>

</style>
