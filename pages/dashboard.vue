<template>
  <div>
    <Header
      backgroundUrl="https://expsystem.com/wp-content/uploads/2020/09/bg-sdd.jpg"
      title="Dashboard"
      description="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s."
      imageUrl="https://image.freepik.com/free-vector/operating-system-concept-illustration_114360-2195.jpg"
    />
    <Sidebar/>
    <Content
      title1="Dashboard 1"
      description1="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl1="https://image.freepik.com/free-vector/operating-system-concept-illustration_114360-2195.jpg"
      title2="Dashboard 2"
      description2="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl2="https://image.freepik.com/free-vector/operating-system-concept-illustration_114360-2195.jpg"
      title3="Dashboard 3"
      description3="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
      imageUrl3="https://image.freepik.com/free-vector/operating-system-concept-illustration_114360-2195.jpg"
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