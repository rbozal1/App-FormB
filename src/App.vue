<template>
    <div class="container">
        <form >
            <h1 style="text-align:center">Fill Out the Form</h1>
            <div class="row" v-if="!submitted">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                   
                    <app-full-name v-model="fullName"></app-full-name>
                    <div class="form-group">
                        <label>Email</label>
                        <input type="email" class="form-control" v-model="email">
                    </div>
                    <div class="form-group">
                        <label>Password</label>
                        <input type="password" class="form-control" v-model="password">
                    </div>
                    <div class="form-group">
                        <label>
                            <input type="radio" value="yes" v-model="storeData"> Yes
                        </label>
                        <label>
                            <input type="radio" value="no" v-model="storeData"> No
                        </label>
                    </div>  
                    <button type="submit" @click.prevent="submitted= true" 
                     class="btn btn-primary">Submit</button> 
                     
                    
                    
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName}}</p>
                        <p>Mail: {{ email }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue';


    export default {
        data() {
            return {
                
                fullName: 'Steve Rogers',
                email:'',
                password: '',
                storeData: 'yes',
                submitted: false 

            }
        },
        components: {
            appFullName: FullName
        }
        
    }
</script>

<style>
</style>
