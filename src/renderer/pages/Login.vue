<template>
  <Row name="Login">
    <Col span="6" offset="9" class="loginForm">
      <Form ref="formInline" :model="loginForm">
        <FormItem prop="user">
            <Input type="text" v-model="loginForm.username" placeholder="用户名">
                <Icon type="ios-person-outline" slot="prepend"></Icon>
            </Input>
        </FormItem>
        <FormItem prop="password">
            <Input type="password" v-model="loginForm.password" placeholder="密码">
                <Icon type="ios-locked-outline" slot="prepend"></Icon>
            </Input>
        </FormItem>
        <FormItem style="text-align:center">
            <Button type="primary" @click="login">登录</Button>
        </FormItem>
      </Form>
    </Col>
  </Row>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      loginForm: {
        username: '',
        password: '',
      },
    };
  },
  methods: {
    login() {},
  },
};
</script>

<style>
.loginForm{
  margin-top: 20%;
  border: 1px bisque solid;
  padding: 30px;
  border-radius: 5px

}
</style>
