<template>
  
  <div class="diagnosticSection p-5 position-relative text-center">
    <div class="container content p-3">
      <h1 class="serviceTitle fw-bold mb-4 ">Chantier</h1>
      <p class="serviceDescribtion my-4">Lorem ipsum dolor sit, amet consectetur adipisicing elit. Facere veritatis quisquam ipsam deleniti numquam tempora, porro dolore assumenda aliquam, architecto provident itaque! Eius officia iusto sint iste sapiente ratione hic?
        amet consectetur adipisicing elit. Facere veritatis quisquam ipsam deleniti numquam tempora, porro dolore assumenda aliquam, architecto provident itaque! Eius officia iusto sint iste sapiente ratione hic?
      </p>
      <div class="services row">
        <div class="col-lg-4 col-md-6" data-aos="fade-up">
          <div class="icon-box">
            <div class="icon"><i class="icofont-computer"></i></div>
            <h4 class="title"><a href="">Lorem Ipsum</a></h4>
            <p class="description">Voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident</p>
          </div>
        </div>
        <div class="col-lg-4 col-md-6" data-aos="fade-up" data-aos-delay="100">
          <div class="icon-box">
            <div class="icon"><i class="icofont-chart-bar-graph"></i></div>
            <h4 class="title"><a href="">Dolor Sitema</a></h4>
            <p class="description">Minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat tarad limino ata</p>
          </div>
        </div>
        <div class="col-lg-4 col-md-6" data-aos="fade-up" data-aos-delay="200">
          <div class="icon-box">
            <div class="icon"><i class="icofont-earth"></i></div>
            <h4 class="title"><a href="">Sed ut perspiciatis</a></h4>
            <p class="description">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur</p>
          </div>
        </div>
        <div class="col-lg-4 col-md-6" data-aos="fade-up" data-aos-delay="300">
          <div class="icon-box">
            <div class="icon"><i class="icofont-image"></i></div>
            <h4 class="title"><a href="">Magni Dolores</a></h4>
            <p class="description">Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum</p>
          </div>
        </div>
        <div class="col-lg-4 col-md-6" data-aos="fade-up" data-aos-delay="400">
          <div class="icon-box">
            <div class="icon"><i class="icofont-settings"></i></div>
            <h4 class="title"><a href="">Nemo Enim</a></h4>
            <p class="description">At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque</p>
          </div>
        </div>
        <div class="col-lg-4 col-md-6" data-aos="fade-up" data-aos-delay="500">
          <div class="icon-box">
            <div class="icon"><i class="icofont-tasks-alt"></i></div>
            <h4 class="title"><a href="">Eiusmod Tempor</a></h4>
            <p class="description">Et harum quidem rerum facilis est et expedita distinctio. Nam libero tempore, cum soluta nobis est eligendi</p>
          </div>
        </div>
      </div>
    </div>

  </div>

</template>

<style>
.diagnosticSection{
overflow: hidden;
background: url(@/assets/newYork1.jpg);
background-size: cover;

}

/*
.diagnosticSection::before{
content: '';
position: absolute;
bottom: 100%;
left: 0;
width: 100%;
height: 100%;
background: #fff;
transform-origin: left;
transform: skewY(8deg);
}
*/

.diagnosticSection::before{
  content: "";
  background: rgba(184, 91, 4, 0.4);
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;

}

.diagnosticSection .content{
z-index: 2;
}

.services .icon-box {
padding: 50px 20px;
margin-top: 35px;
margin-bottom: 25px;
text-align: center;
height: 200px;
position: relative;
background: #fff;
box-shadow: 0px 2px 15px rgba(0, 0, 0, 0.1);
}

.services .icon {
position: absolute;
top: -36px;
left: calc(50% - 36px);
transition: 0.2s;
border-radius: 50%;
border: 6px solid #fff;
display: flex;
justify-content: center;
align-items: center;
flex-direction: column;
text-align: center;
width: 72px;
height: 72px;
background: #ff5821;
}

.services .icon i {
color: #fff;
font-size: 24px;
}

.services .title {
font-weight: 700;
margin-bottom: 15px;
font-size: 18px;
text-transform: uppercase;
}

.services .title a {
color: #343a40;
}

.services .icon-box:hover .icon {
background: #fff;
border: 2px solid #ff5821;
}

.services .icon-box:hover .icon i {
color: #ff5821;
}

.services .icon-box:hover .title a {
color: #ff5821;
}

.services .description {
line-height: 24px;
font-size: 14px;
}

</style>
