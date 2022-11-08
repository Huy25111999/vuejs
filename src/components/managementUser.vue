<template>
    <div>
        <b-button v-b-modal.modal-lg variant="primary">Thêm mới</b-button>

        <b-modal id="modal-lg" size="lg" title="Quản lý người dùng" footer="" hide-footer>
            <b-form @submit="onSubmit" @reset="onReset" v-if="show">
                <b-form-group                
                id="fieldset-1"
                label="Tên người dùng"
                :invalid-feedback = "invalidFeedback"
                :state = "state"
                label-for="username">
                    <b-form-input v-model="form.username"
                        id="input-1"
                        type="text" :state = "state" trim
                        placeholder="Nhập tên người dùng">
                    </b-form-input>
                </b-form-group>    

                <b-form-group 
                id="" label="Email"
                label-for="email">
                    <b-form-input v-model="form.email"
                    type="text" 
                    placeholder="Nhập email">
                    </b-form-input>
                </b-form-group> 

                <b-form-group 
                id="" label="Số điện thoại"
                label-for="phone">
                    <b-form-input v-model="form.phone"
                    type="text" 
                    placeholder="Nhập số điện thoại">
                    </b-form-input>
                </b-form-group> 

                <b-button class="btn-submit" type="submit" variant="primary">Submit</b-button>
                <b-button class="btn-submit" type="reset" variant="danger">Reset</b-button>
                <b-button class="btn-submit" aria-label="Close" data-bs-dismiss="modal" variant="dark">Huỷ</b-button>
            </b-form>
        </b-modal>
    </div>
</template>

<!-- 
<template>
    <div class="container p-5">
        <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
            User Login
        </button>

        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
            <div class="modal-dialog">
                <div class="modal-content">
                    <form>
                        <div class="modal-header">
                            <h5 class="modal-title text-danger" id="exampleModalLabel">Quản lý người dùng</h5>
                            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                        </div>
                        <div class="modal-body">
                        
                            <div class="mb-3">
                                <label for="exampleInputEmail1" class="form-label">Email address</label>
                                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
                                <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
                            </div>
                            <div class="mb-3">
                                <label for="exampleInputPassword1" class="form-label">Password</label>
                                <input type="password" class="form-control" id="exampleInputPassword1">
                            </div>
                            
                    
                        </div>
                        <div class="modal-footer">
                        <button type="button" class="btn btn-warning" data-bs-dismiss="modal">Close</button>
                        <b-button variant="success">Lưu</b-button>
                        </div>
                    </form> 
                </div>
            </div>
        </div>
   </div>
</template> -->

<script>
    export default{
        data(){
            return{
                form:{
                    username:'',
                    email:'',
                    phone : ''
                },
                show: true
            }
        },
        coputed:{
            state(){
                return this.form.username.length >= 4
            },
            invalidFeedback(){
                if (this.formData.length >0 ){
                    return "Tên người dùng ít nhất 4 ký tự"
                }
                return "tên người dùng không được để trống"
            }
        },
        methods:{
            onSubmit(e){
                e.preventDefault();
                console.log(JSON.stringify(this.form));
            },

            onReset(e){
                e.preventDefault();
                this.form.username = '';
                this.form.email = '';
                this.form.phone = '';
                this.show = false;
                this.$nextTick(()=>{
                    this.show = true
                })
            }
        }
    }
</script>

<style scoped>
    .btn-submit {
        float: right;
        margin-left: 16px;
    }
</style>