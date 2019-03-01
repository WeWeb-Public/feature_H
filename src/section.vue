<template>

    <div class="feature_H">

        <!-- wwManager:start -->
        <wwSectionEditMenu v-bind:section="section"></wwSectionEditMenu>
        <!-- wwManager:end -->

        <wwObject class="background" v-bind:ww-object="section.data.background" v-bind:section="section" ww-category="background">
        </wwObject>
        <div class="content">
            <div class="title-container">
                <div class="title" v-ww-vertical-align>
                    <wwObject v-bind:ww-object="section.data.title" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                </div>
                <div class="title-synopsis">
                    <wwObject v-bind:ww-object="section.data.titleSynopsis" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                </div>
                

            </div>
            <div class="card-container container">
                <div class="card-column">
                    <div class="card-outter card-1">
                        <wwObject class="card-title card-title-1" v-bind:ww-object="section.data.cardTitle1" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>

                        <div class="card-string"></div>
                        <!-- <div class="card" v-on:click="wwOnClickCard" data-card="1" ng-class="{'flipped':cardStatus[0].flipped}"> -->
                            <div class="card-content front">
                                <wwObject class="background" v-bind:ww-object="section.data.card1Bg" v-bind:section="section" ww-category="background">
                                </wwObject>
                                <wwObject class="content-title-1" v-bind:ww-object="section.data.contentTitle1" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                
                                <wwObject class="content-text" v-bind:ww-object="section.data.contentText1" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                <!-- <wwLayoutColumn tag="div" ww-default="ww-image" v-bind:ww-list="section.data.cardsWwObject[0]" class="ww-object-container">
                                    <wwObject v-for="wwObject in section.data.cardsWwObject[0]" :key="wwObject.uniqueId" v-bind:ww-object="wwObject" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                
                                </wwLayoutColumn> -->
                             
                            </div>

                        <!-- </div> -->
                    </div>
                    <div class="button-card button-card-1">
                                    <!-- <wwObject v-bind:ww-object="section.data.buttonCard" v-bind:section="section" ww-inside-ww-object="true" :ww-not-editable="textNotEditable" ww-default-object-type="ww-text" ww-object-types-allowed="['ww-text']"></wwObject> -->
                      <wwObject v-bind:ww-object="section.data.buttonCard" v-bind:section="section"></wwObject>
                    </div>
                </div>

                <div class="card-column">
                    <div class="card-outter card-2">
                        <wwObject class="card-title card-title-2" v-bind:ww-object="section.data.cardTitle2" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                        <div class="card-string"></div>
                        <!-- <div class="card" v-on:click="wwOnClickCard" data-card="2" ng-class="{'flipped':cardStatus[1].flipped}"> -->
                            <div class="card-content front">
                              <wwObject class="background" v-bind:ww-object="section.data.card2Bg" v-bind:section="section" ww-category="background">
                                </wwObject>
                                <wwObject class="content-title-2" v-bind:ww-object="section.data.contentTitle2" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>                              
                                
                                <wwObject class="content-text" v-bind:ww-object="section.data.contentText2" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                <!-- <div class="ww-object-container" v-for="wwObject in section.data.cardsWwObject[1]" :key="wwObject.uniqueId">
                                    <wwObject v-bind:ww-object="wwObject" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                </div> -->
                            </div>
                        <!-- </div> -->
                    </div>
                    <div class="button-card button-card-2">
                                    <wwObject v-bind:ww-object="section.data.buttonCard2" v-bind:section="section"></wwObject>
                                </div>
                </div>

                <div class="card-column">
                    <div class="card-outter card-3">
                        <wwObject class="card-title card-title-3" v-bind:ww-object="section.data.cardTitle3" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                        <div class="card-string"></div>
                        <!-- <div class="card" v-on:click.capture="wwOnClickCard" data-card="3" ng-class="{'flipped':cardStatus[2].flipped}"> -->
                            <div class="card-content front">
                                  <wwObject class="background" v-bind:ww-object="section.data.card3Bg" v-bind:section="section" ww-category="background">
                                </wwObject>
                                <wwObject class="content-title-3" v-bind:ww-object="section.data.contentTitle3" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                              <wwObject class="content-text" v-bind:ww-object="section.data.contentText3" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                <!-- <div class="ww-object-container" v-for="wwObject in section.data.cardsWwObject[2]" :key="wwObject.uniqueId">
                                    <wwObject v-bind:ww-object="wwObject" v-bind:section="section" ww-default-object-type="ww-text"></wwObject>
                                </div> -->
                        
                            </div>
                        
                        <!-- </div> -->
                    </div>
                    <div class="button-card button-card-3">
                      <wwObject v-bind:ww-object="section.data.buttonCard3" v-bind:section="section"></wwObject>
                    </div>
                </div>

                <div class="clearfix"></div>

            </div>
        </div>

    </div>
</template>

<script>
export default {
  name: "feature_H",
  props: {
    section: Object
  },
  computed: {},
  methods: {
    wwOnScroll: function() {
      if (this.wwAnimStarted) {
        return;
      }

      var scrollTop = Math.max(
        document.body.scrollTop,
        document.documentElement.scrollTop
      );
      var sectionTop = this.$el.getBoundingClientRect().top;

      if (scrollTop >= sectionTop - window.innerHeight / 4) {
        this.wwRunAnim();
      }
    },
    wwRunAnim: function() {
      this.wwAnimStarted = true;

      const self = this;

      self.$el.querySelector(".card-1").classList.add("animate");

      setTimeout(function() {
        self.$el.querySelector(".card-2").classList.add("animate");

        setTimeout(function() {
          self.$el.querySelector(".card-3").classList.add("animate");
        }, 300);
      }, 300);
    },
    wwOnMousemove: function(event, factor) {
      factor = factor || 1;
      var offset = 0;

      var c = (event.target || event.srcElement).closest(".card");

      var index = 0;

      if (c.getAttribute("data-card") == "2") {
        index = 1;
      }
      if (c.getAttribute("data-card") == "3") {
        index = 2;
      }

      if (this.cardStatus[index].flipped) {
        offset = 180;
      }

      var parentOffset = c.parentElement.getBoundingClientRect();

      var x =
        ((event.pageX - parentOffset.left) / c.getBoundingClientRect().width) *
          2 -
        1;
      var y =
        (event.pageY - window.scrollY - parentOffset.top) /
        c.getBoundingClientRect().height;

      var rX = -y * 2 * factor;
      var rY = x * 2 * factor + offset;

      //c.css("-webkit-transition", "");
      //c.css("-moz-transition", "");
      //c.css("-o-transition", "");
      c.style.transition = "";

      //c.css("-webkit-transform", "perspective(600px) rotateX(" + rX + "deg) rotateY(" + rY + "deg)");
      //c.css("-moz-transform", "perspective(600px) rotateX(" + rX + "deg) rotateY(" + rY + "deg)");
      //c.css("-o-transform", "perspective(600px) rotateX(" + rX + "deg) rotateY(" + rY + "deg)");
      c.style.transform =
        "perspective(600px) rotateX(" + rX + "deg) rotateY(" + rY + "deg)";
    },
    wwOnMouseout: function(event) {
      var offset = 0;

      var c = (event.target || event.srcElement).closest(".card");

      var index = 0;

      if (c.getAttribute("data-card") == "2") {
        index = 1;
      }
      if (c.getAttribute("data-card") == "3") {
        index = 2;
      }

      if (this.cardStatus[index].flipped) {
        offset = 180;
      }

      //c.css("-webkit-transition", "all 0.3s ease");
      //c.css("-moz-transition", "all 0.3s ease");
      //c.css("-o-transition", "all 0.3s ease");
      c.style.transition = "all 0.3s ease";

      //c.css("-webkit-transform", "perspective(600px) rotateX(0deg) rotateY( " + offset + "deg)");
      //c.css("-moz-transform", "perspective(600px) rotateX(0deg) rotateY( " + offset + "deg)");
      //c.css("-o-transform", "perspective(600px) rotateX(0deg) rotateY( " + offset + "deg)");
      c.style.transform =
        "perspective(600px) rotateX(0deg) rotateY( " + offset + "deg)";
    },
    wwOnClickCard: function(event) {
      var c = (event.target || event.srcElement).closest(".card");

      var index = 0;

      if (c.getAttribute("data-card") == "2") {
        index = 1;
      }
      if (c.getAttribute("data-card") == "3") {
        index = 2;
      }

      var parentOffset = c.parentElement.getBoundingClientRect();

      var x =
        ((event.pageX - parentOffset.left) / c.getBoundingClientRect().width) *
          2 -
        1;

      c.removeEventListener("mousemove", this.wwOnMousemove);
      c.removeEventListener("mouseout", this.wwOnMouseout);

      //c.css("-webkit-transition", "1s all ease");
      //c.css("-moz-transition", "1s all ease");
      //c.css("-o-transition", "1s all ease");
      c.style.transition = "1s all ease";

      var offset = 0;
      if (!this.cardStatus[index].flipped) {
        offset = 180;
      }

      if (x > 0) {
        //c.css("-webkit-transform", "perspective(600px) rotateY(" + (-offset) + "deg)");
        //c.css("-moz-transform", "perspective(600px) rotateY(" + (-offset) + "deg)");
        //c.css("-o-transform", "perspective(600px) rotateY(" + (-offset) + "deg)");
        c.style.transform = "perspective(600px) rotateY(" + -offset + "deg)";
      } else {
        //c.css("-webkit-transform", "perspective(600px) rotateY(" + offset + "deg)");
        //c.css("-moz-transform", "perspective(600px) rotateY(" + offset + "deg)");
        //c.css("-o-transform", "perspective(600px) rotateY(" + offset + "deg)");
        c.style.transform = "perspective(600px) rotateY(" + offset + "deg)";
      }

      this.cardStatus[index].flipped = !this.cardStatus[index].flipped;

      const self = this;

      setTimeout(function() {
        c.addEventListener("mousemove", self.wwOnMousemove);
        c.addEventListener("mouseout", self.wwOnMouseout);
      }, 1050);
    }
  },
  beforeDestroy: function() {
    window.removeEventListener("scroll", this.wwOnScroll);

    this.$el
      .querySelector(".card-1 .card")
      .removeEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-1 .card")
      .removeEventListener("mouseout", this.wwOnMouseout);

    this.$el
      .querySelector(".card-2 .card")
      .removeEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-2 .card")
      .removeEventListener("mouseout", this.wwOnMouseout);

    this.$el
      .querySelector(".card-3 .card")
      .removeEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-3 .card")
      .removeEventListener("mouseout", this.wwOnMouseout);
  },
  created: function() {
    this.cardStatus = [
      {
        flipped: false
      },
      {
        flipped: false
      },
      {
        flipped: false
      }
    ];

    this.wwAnimStarted = false;

    // new

    if (!this.section.data.background) {
      this.section.data.background = wwLib.wwObject.getDefault({
        type: "ww-image",
        data: {
          url: "http://cdn.wewebapp.io/public/images/weweb-wp.png"
        }
      });
    }

    if (!this.section.data.title) {
      this.section.data.title = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Nos Métiers !",
            en: "Our Business !"
          },
          align: "center",
          size: 2,
          color: "white"
        }
      });
    }

    if (!this.section.data.titleSynopsis) {
      this.section.data.titleSynopsis = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Nous vous accompagnons au travers de nos 3 pôles!",
            en: "Nous vous accompagnons au travers de nos 3 pôles!"
          },
          align: "center",
          color: "white"
        }
      });
    }

    if (!this.section.data.cardTitle1) {
      this.section.data.cardTitle1 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Conseil",
            en: "Conseil"
          },
          align: "center",
          size: 1,
          color: "black"
        }
      });
    }
    if (!this.section.data.card1Bg) {
      this.section.data.card1Bg = wwLib.wwObject.getDefault({
        type: "ww-image",
        data: {
          url: "http://cdn.wewebapp.io/public/images/weweb-wp.png"
        }
      });
    }

    if (!this.section.data.contentTitle1) {
      this.section.data.contentTitle1 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Space Advisory",
            en: "Space Advisory"
          },
          align: "center",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.contentText1) {
      this.section.data.contentText1 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr:
              "Définir les meilleurs options pour votre projet immobiier investisseurs ou utilisateurs ",
            en:
              "Définir les meilleurs options pour votre projet immobiier investisseurs ou utilisateurs "
          },
          align: "justify",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.buttonCard) {
      this.section.data.buttonCard = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Voir le Pôle Conseil",
            en: "Voir le Pôle Conseil"
          },
          align: "center",
          color: "black"
        }
      });
    }

    if (!this.section.data.cardTitle2) {
      this.section.data.cardTitle2 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Contractant Général",
            en: "Contractant Général"
          },
          align: "center",
          size: 1,
          color: "black"
        }
      });
    }
    if (!this.section.data.card2Bg) {
      this.section.data.card2Bg = wwLib.wwObject.getDefault({
        type: "ww-image",
        data: {
          url: "http://cdn.wewebapp.io/public/images/weweb-wp.png"
        }
      });
    }

    if (!this.section.data.contentTitle2) {
      this.section.data.contentTitle2 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Plug and Play",
            en: "Plug and Play"
          },
          align: "center",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.contentText2) {
      this.section.data.contentText2 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr:
              "A vos côté depuis la conception jusau'à la réalisation de vos travaux clés en main",
            en:
              "A vos côté depuis la conception jusau'à la réalisation de vos travaux clés en main"
          },
          align: "justify",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.buttonCard2) {
      this.section.data.buttonCard2 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Voir le Pôle Contractant Général",
            en: "Voir le Pôle Contractant Général"
          },
          align: "center",
          size: 1,
          color: "black"
        }
      });
    }

    if (!this.section.data.cardTitle3) {
      this.section.data.cardTitle3 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Change",
            en: "Change"
          },
          align: "center",
          size: 1,
          color: "black"
        }
      });
    }
    if (!this.section.data.card3Bg) {
      this.section.data.card3Bg = wwLib.wwObject.getDefault({
        type: "ww-image",
        data: {
          url: "http://cdn.wewebapp.io/public/images/weweb-wp.png"
        }
      });
    }
    if (!this.section.data.contentTitle3) {
      this.section.data.contentTitle3 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "F.O.P",
            en: "F.O.P"
          },
          align: "center",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.contentText3) {
      this.section.data.contentText3 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr:
              "Focus On People, mettre les utilisateurs au cœur de la réflexion Workplace pour garentir le succè de votre pojet d'immobilier d'entreprise.",
            en:
              "Focus On People, mettre les utilisateurs au cœur de la réflexion Workplace pour garentir le succè de votre pojet d'immobilier d'entreprise."
          },
          align: "justify",
          size: 1,
          color: "white"
        }
      });
    }

    if (!this.section.data.buttonCard3) {
      this.section.data.buttonCard3 = wwLib.wwObject.getDefault({
        type: "ww-text",
        data: {
          text: {
            fr: "Voir le Pôle Change",
            en: "Voir le Pôle Change"
          },
          align: "center",
          size: 1,
          color: "black"
        }
      });
    }

    // end of new
    if (!this.section.data.cardsWwObject) {
      this.section.data.cardsWwObject = [];
    }

    while (this.section.data.cardsWwObject.length < 6) {
      this.section.data.cardsWwObject.push([]);
    }

    //Add scroll event
    window.addEventListener("scroll", this.wwOnScroll);

    //Trigger scroll at least once
    setTimeout(this.wwOnScroll, 200);

    let self = this;
  },
  mounted: function() {
    this.$el
      .querySelector(".card-1 .card")
      .addEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-1 .card")
      .addEventListener("mouseout", this.wwOnMouseout);

    this.$el
      .querySelector(".card-2 .card")
      .addEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-2 .card")
      .addEventListener("mouseout", this.wwOnMouseout);

    this.$el
      .querySelector(".card-3 .card")
      .addEventListener("mousemove", this.wwOnMousemove);
    this.$el
      .querySelector(".card-3 .card")
      .addEventListener("mouseout", this.wwOnMouseout);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.feature_H {
  position: relative;
}

.feature_H .background {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  z-index: -1;
}

.feature_H .content {
  position: relative;
  width: 100%;
  padding-bottom: 100px;
}

.feature_H .title-container {
  /*width: 100%;*/
  height: 130px;
  padding: 0 15%;
  position: relative;
}

.feature_H .content-title-1 {
  margin-bottom: 20px;
}

.feature_H .content-title-2 {
  margin-bottom: 20px;
}

.feature_H .content-title-3 {
  margin-bottom: 20px;
}

.feature_H .content-text {
  margin: 20px;
  text-justify: inter-word;
}

.feature_H .title {
  position: relative;
}

.feature_H .card-container {
  position: relative;
  margin-top: 60px;
}

.feature_H .card-column {
  width: 100%;
  float: left;
  padding: 0 20px;
}

.feature_H .card-outter {
  position: relative;
  margin-bottom: 40px;
}

.feature_H .card {
  -webkit-transform-style: preserve-3d;
  -moz-transform-style: preserve-3d;
  -o-transform-style: preserve-3d;
  transform-style: preserve-3d;

  width: 100%;
  position: relative;

  -webkit-transform-origin: 50% 20px;
  -moz-transform-origin: 50% 20px;
  -o-transform-origin: 50% 20px;
  transform-origin: 50% 20px;

  perspective: 600px;
}

.feature_H .card-content {
  padding-top: 40px;
  min-height: 100%;
  width: 100%;
  height: 250px;
  overflow: hidden;
  border-radius: 7px;

  -moz-box-shadow: 0px 10px 40px 0px #717c8933;
  -webkit-box-shadow: 0px 10px 40px 0px #717c8933;
  -o-box-shadow: 0px 10px 40px 0px #717c8933;
  box-shadow: 0px 10px 40px 0px #717c8933;
  filter: progid:DXImageTransform.Microsoft.Shadow(color=#717c8933, Direction=180, Strength=40);

  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -o-backface-visibility: hidden;
  backface-visibility: hidden;
  transform-style: preserve-3d;
}

.feature_H .card .front {
  position: relative;
}

.feature_H .ww-object-container {
  width: 100%;
  position: relative;
}

.feature_H .button-card {
  position: absolute;
  background-color: rgb(255, 255, 255);
  border-color: rgb(229, 115, 115);
  border-radius: 500px;
  border-style: solid;
  border-width: 2px;
  box-sizing: border-box;
  display: inline-block;
  line-height: 20px;
  padding: 5px 10px 10px 5px;
  height: 36px;
  bottom: 25px;
}

@media (max-width: 450px) {
  .feature_H .button-card {
    font-size: 14px;
  }

  .feature_H .button-card-1 {
    width: 170px;
    margin-left: 25%;
    top: 250px;
  }

  .feature_H .button-card-2 {
    width: 250px;
    margin-left: 15%;
    bottom: 330px;
  }

  .feature_H .button-card-3 {
    width: 170px;
    margin-left: 25%;
    bottom: 20px;
  }
}

@media (min-width: 768px) {
  .feature_H .card-column {
    width: 33.3333%;
    margin-top: 120px;
  }

  .feature_H .card-title {
    position: absolute;
    width: 60%;
    height: 50px;
    top: -130px;
    font-size: 13px;
    background-color: white;
    line-height: 50px;
    z-index: 2;
  }

  .feature_H .card-title-1 {
    left: 22%;
  }

  .feature_H .card-title-2 {
    left: 22%;
  }

  .feature_H .card-title-3 {
    left: 22%;
  }

  .feature_H .card-outter {
    opacity: 0;
  }
  .feature_H .card-outter.animate {
    opacity: 1;
    animation: feature_H-bounce 2s;
  }
  .feature_H .card-1.animate .card-string {
    animation: feature_H-anti-bounce-1 2s;
    height: 200px;
  }
  .feature_H .card-2.animate .card-string {
    animation: feature_H-anti-bounce-2 2s;
    height: 200px;
  }
  .feature_H .card-3.animate .card-string {
    animation: feature_H-anti-bounce-3 2s;
    height: 200px;
  }
  @keyframes feature_H-bounce {
    0% {
      -moz-transform: translateY(-60px);
      -ms-transform: translateY(-60px);
      -webkit-transform: translateY(-60px);
      transform: translateY(-60px);
      opacity: 0;
    }
    20%,
    60% {
      -moz-transform: translateY(0);
      -ms-transform: translateY(0);
      -webkit-transform: translateY(0);
      transform: translateY(0);
      opacity: 1;
    }
    40% {
      -moz-transform: translateY(-15px);
      -ms-transform: translateY(-15px);
      -webkit-transform: translateY(-15px);
      transform: translateY(-15px);
    }
  }
  @keyframes feature_H-anti-bounce-1 {
    0% {
      height: 240px;
    }
    20%,
    60% {
      height: 300px;
    }
    40% {
      height: 285px;
    }
  }
  @keyframes feature_H-anti-bounce-2 {
    0% {
      height: 240px;
    }
    20%,
    60% {
      height: 300px;
    }
    40% {
      height: 285px;
    }
  }
  @keyframes feature_H-anti-bounce-3 {
    0% {
      height: 240px;
    }
    20%,
    60% {
      height: 300px;
    }
    40% {
      height: 285px;
    }
  }
  .feature_H .card-string {
    position: absolute;
    width: 0;
    height: 100px;
    left: 50%;
    -webkit-transform: translateY(-100%);
    -moz-transform: translateY(-100%);
    -o-transform: translateY(-100%);
    transform: translateY(-100%);
    border-left: 1px #000000 solid;
    z-index: 1;
  }

  .feature_H .card-1 {
    margin-top: 100px;
  }
  .feature_H .card-1 .card-string {
    height: 200px;
  }
  .feature_H .card-2 {
    margin-top: 100px;
  }
  .feature_H .card-2 .card-string {
    height: 200px;
  }
  .feature_H .card-3 {
    margin-top: 100px;
  }
  .feature_H .card-3 .card-string {
    height: 200px;
  }

  .feature_H .button-card {
    font-size: 9px;
  }
  .feature_H .button-card-1 {
    width: 15%;
    margin-left: 8%;
  }

  .feature_H .button-card-2 {
    width: 22%;
    margin-left: 4%;
  }

  .feature_H .button-card-3 {
    width: 15%;
    margin-left: 7%;
  }

  @media (min-width: 1180px) {
    .feature_H .button-card {
      font-size: 15px;
    }
  }
}
</style>
