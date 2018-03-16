<template>
  <Layout>
    <Header>Header</Header>
    <Layout>
      <Sider>Sider</Sider>
      <Layout class="content-layout">
        <Header class="content-header">
            <ButtonGroup>
              <Button>Cancel</Button>
              <Button type="primary">Confirm</Button>
            </ButtonGroup>
            <ButtonGroup>
              <Button disabled>Yesterday</Button>
              <Button disabled>Today</Button>
              <Button disabled>Tomorrow</Button>
            </ButtonGroup>
            <ButtonGroup>
              <Button type="primary">L</Button>
              <Button>M</Button>
              <Button type="ghost">M</Button>
              <Button type="dashed">R</Button>
            </ButtonGroup>
        </Header>
        <Content  style="over-flow:scoll">
          <Breadcrumb separator=">" style="margin:10px 0 10px 10px">
            <BreadcrumbItem to="/">Home</BreadcrumbItem>
            <BreadcrumbItem to="/components/breadcrumb">Components</BreadcrumbItem>
            <BreadcrumbItem>Breadcrumb</BreadcrumbItem>
          </Breadcrumb>
          <Table  :height="tableHeight" :style="{'max-height':tableHeight}" size="small"  border :columns="fileTabelCols" :data="files"></Table>
        </Content>
      </Layout>
    </Layout>
  </Layout>
</template>
<script>
export default {
  name: 'Index',
  watch: {},
  methods: {
    getTableSize() {
      return window.innerHeight - 64 - 10 - 32 - 10 - 22 - 20;
    },
  },
  mounted() {
    this.tableHeight = this.getTableSize();
    window.onresize = () => {
      console.log(this.tableHeight);
      this.tableHeight = this.getTableSize();
      console.log(this.tableHeight);
    };
  },

  data() {
    return {
      tableHeight: 100,
      fileTabelCols: [
        {
          type: 'selection',
          width: 60,
          align: 'center',
        },
        {
          title: '文件名',
          key: 'fileName',
          ellipsis: 'true',
        },
        {
          title: '大小',
          key: 'size',
          width: '150px',
        },
        {
          title: '日期',
          key: 'time',
          width: '150px',
        },
      ],
      files: [
        {
          fileName:
            '文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1文件1',
          size: '100MB',
          time: '2018-12-13',
        },
      ],
    };
  },
};
</script>
<style>
.content-layout {
  padding: 10px;
  max-height: 100%;
}
.content-header {
  background: transparent;
  padding: 0;
  height: auto;
  line-height: 0;
}
.content-card {
  height: 100%;
}
</style>
