<template>
	<nav class="col-md-8 col-md-offset-2" :class="{'nav-background':!responseIcon}">
        <div class="nav-section" :class="{'nav-show':!responseIcon}">
          <a href="/">Home</a>
          <a href="#skillset">Skils</a>
          <a href="#content-section">O mnie</a>
          <a href="#contact">Kontakt</a>
        </div>
        <div class="nav-section" :class="{'nav-show':!responseIcon}">
          <a href="https://www.linkedin.com/in/bart%C5%82omiej-p%C5%82aza-89407792/"><i class="fa fa-linkedin" aria-hidden="true"></i> LinkedIn</a>
          <span>
            <a href="https://github.com/BartPlaza"><i class="fa fa-github"  aria-hidden="true"></i> GitHub</a>
            <i class="fa fa-eject response-menu" aria-hidden="true" @click="showMenu" v-show="!responseIcon"></i>
          </span>
        </div>
        <i class="fa fa-bars response-menu" @click="showMenu" v-show="responseIcon" aria-hidden="true"></i>
  </nav>

</template>
<script>
export default {
	data: function(){
      return {
        responseIcon: true
      }
    },
    methods: {
      showMenu: function(){
        this.responseIcon = !this.responseIcon;
      }
    }
}
</script>
<style lang="scss">
$sm: "only screen and (max-width: 768px)";
$md: "only screen and (max-width: 1080px)";

nav {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  font-size: 22px;

  @media #{$sm}{
      flex-direction: column;      
      padding-bottom: 15px;
    }

    @media #{$md}{
      font-size: 18px;
    }
}

.nav-section{
  display: flex;
  flex-direction: row;

  @media #{$sm}{
      flex-direction: column;
      display: none;
    }
}

.nav-section > span {
  display: flex;
  justify-content: space-between;
  padding: 0;
}

.nav-section > span > i {
  padding: 0px;
}

nav a {
  color: white;
  display: block;
  padding: 20px;
  text-decoration: none !important;


  @media #{$sm}{
      padding: 5px;
    }
}

nav a:hover {
  color: black;
  border-bottom: 2px solid #152034;
  padding-bottom: 18px;
  box-sizing: border-box;
}

.response-menu {
  padding: 20px;
  font-size: 30px;
  display: none;

  @media #{$sm}{
      display: flex;
      align-self: flex-end;
    }
}

.response-menu:hover {
  cursor: pointer;
}

.nav-show {
  @media #{$sm}{
      display: block;
    }
}

.nav-background {
  @media #{$sm}{
      background-color: rgba(162,148,163, 0.8);
      box-shadow: 0 4px 8px -3px black;
    }
}

</style>