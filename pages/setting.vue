<template>
  <div>
    <Header
      backgroundUrl="https://expsystem.com/wp-content/uploads/2020/09/bg-sdd.jpg"
      title="Setting"
      description="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s."
      imageUrl="https://image.freepik.com/free-vector/settings-concept-illustration_114360-3056.jpg"
    />
    <Sidebar/>
    <Content
      title1="Setting 1"
      description1="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl1="https://image.freepik.com/free-vector/settings-concept-illustration_114360-3056.jpg"
      title2="Setting 2"
      description2="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl2="https://image.freepik.com/free-vector/settings-concept-illustration_114360-3056.jpg"
      title3="Setting 3"
      description3="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl3="https://image.freepik.com/free-vector/settings-concept-illustration_114360-3056.jpg"
    />
    <Footer/>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Sidebar from '@/components/Sidebar'
import Content from '@/components/Content'
import Footer from '@/components/Footer'
export default {
  components:{
    Header,
    Sidebar,
    Content,
    Footer
  }
}
</script>