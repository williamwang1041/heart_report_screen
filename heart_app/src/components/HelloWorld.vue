<template>
  <v-container fluid>
    <v-layout>
      <v-flex xs12 md3>
        <div class="heart-6_pic">
          <v-img
            contain
            src="../assets/heart-6 copy.png"
            overlap
            transition="scale-transition"
            width="689px"
            height="1143px"
          />
        </div>
        <div class="heart-8_pic">
          <v-img
            contain
            src="../assets/heart-8.png"
            overlap
            transition="scale-transition"
            width="331.9px"
            height="373px"
          />
        </div>
      </v-flex>
      <v-flex xs12 md9 mt-10 ml-12>
        <v-layout align-center wrap>
          <v-flex md1>
            <font size="5"><b>Inflammation</b></font>
          </v-flex>
          <v-flex xs12 md1 ml-12>
            <v-icon color="yellow darken-3">mdi-alert </v-icon>
          </v-flex>
          <v-flex xs12 md2 ml-5></v-flex>
          <v-flex xs12 md1 ml-12>
            <span
              ><font size="4"><b>Your Result:</b></font></span
            >
          </v-flex>
          <v-flex xs12 md1>
            <h2>
              <font color="#F5A623" size="4"><b>Moderate</b></font>
            </h2>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>

        <div class="inflammation-is-your-copy">
          <span>
            <p>
              Inflammation is your body’s response to infection or injury. It
              can affect many areas of the body and is a cause <br />
              of many major diseases, including cancer, ischemic heart disease,
              and autoimmune diseases. Inflammation in <br />
              the heart causes damage and can lead to serious health problems.
            </p>
          </span>
        </div>
        <div class="line"></div>
        <div class="slope"></div>
        <v-layout class="mt-10">
          <v-flex xs12 md1></v-flex>
          <v-flex ml-12>
            <v-card class="rounded-xl" color="grey darken-2" width="620px">
              <v-card-title> </v-card-title>
              <v-card-text>
                <span>
                  <font class="jane-caution-you">
                    <p>
                      Jane, caution. You have inflammation that may <br />damage
                      your artery wall lining. This is how <br />blockages can
                      form.
                    </p></font
                  >

                  <p>
                    <font class="if-you-have-a-bloack">
                      <p>
                        If you have a bloackage in your artery wall lining. it
                        may be cracking or shifting<br />
                        which may increase the rish of it breaking and forming a
                        clot. If your <br />inflammation is mot addressed this
                        can cause a heart attack or stroke.
                      </p></font
                    >
                  </p>
                </span>
              </v-card-text>
            </v-card>
          </v-flex>
        </v-layout>
        <v-layout class="mt-7"></v-layout>
        <v-layout class="mt-12">
          <v-flex xs12 md4 mt-10></v-flex>
          <v-flex xs12 md1>
            <v-chip color="#7ED321" label x-small></v-chip>
            In Control
          </v-flex>
          <v-flex xs12 md1>
            <v-chip color="#F8E71C" x-small label></v-chip>
            Moderate
          </v-flex>
          <v-flex xs12 md2>
            <v-chip color="#F06539" x-small label></v-chip>
            High Risk
          </v-flex>
        </v-layout>
        <v-layout wrap class="mt-1 ml-12">
          <div class="rounded_rect"></div>
          <div class="group-3-copy">
            <v-data-table 
            :headers="headers" 
            :items="test_list"
            hide-default-footer>
            
              <template v-slot:item.score="{ item }">
                <v-container>
                  <v-row class="mt-3" no-gutters>
                    <v-tooltip bottom color="white" :disabled="false"
                      ><font color="black">{{ item.test_result }}</font>
                      <template v-slot:activator="{ on, attrs }">
                        <v-col :cols="3" v-bind="attrs" v-on="on">
                          <v-card class="pa-2" outlined tile color="#7ED321">
                          </v-card>
                        </v-col>
                      </template>
                    </v-tooltip>

                    <v-tooltip bottom color="white" :disabled="false"
                      ><font color="black">{{ item.test_result }}</font>
                      <template v-slot:activator="{ on, attrs }">
                        <v-col :cols="6" v-bind="attrs" v-on="on">
                          <v-card class="pa-2" outlined tile color="#F8E71C">
                          </v-card>
                        </v-col>
                      </template>
                    </v-tooltip>

                    <v-col :cols="3">
                      <v-card class="pa-2" outlined tile color="#F06539">
                      </v-card>
                    </v-col>
                  </v-row>
                </v-container>
              </template>
            </v-data-table>
          </div>

          <!-- <v-container grid-list-md>
            <v-card class="white_card" color="#F6F8FA">
              <v-layout>
                <v-flex class="header">TEST NAME</v-flex>
                <v-flex class="header">TEST RESULT</v-flex>
                <v-flex class="header">TEST RANGE</v-flex>
                <v-flex class="header">SCORE</v-flex>
              </v-layout>
            </v-card>
            <v-card class="black_card">
              <v-layout>
                <v-flex my-5 class="plac">PLAC</v-flex>
                <v-flex my-5 md3>21</v-flex>
                <v-flex my-5 md2>>15</v-flex>
                <v-flex my-5 md4>
                  <v-container>
                    <v-row class="mt-3" no-gutters>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#7ED321">
                        </v-card>
                      </v-col>
                      <v-col :cols="6">
                        <v-card class="pa-2" outlined tile color="#F8E71C">
                        </v-card>
                      </v-col>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#F06539">
                        </v-card>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-flex>
              </v-layout>
              <v-divider></v-divider>
              <v-layout>
                <v-flex md3 my-5 class="plac"> Homocysteine (μmol/L) </v-flex>

                <v-flex md3 my-5>19</v-flex>
                <v-flex md2 my-5>16 ~ 31</v-flex>

                <v-flex md4>
                  <v-container>
                    <v-row class="mt-3" no-gutters>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#7ED321">
                        </v-card>
                      </v-col>
                      <v-col :cols="6">
                        <v-card class="pa-2" outlined tile color="#F8E71C">
                        </v-card>
                      </v-col>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#F06539">
                        </v-card>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-flex>
              </v-layout>
              <v-divider></v-divider>

              <v-layout>
                <v-flex md3 my-5 class="plac"> hs-CRP (mg/L) </v-flex>

                <v-flex md3 my-5>6</v-flex>
                <v-flex md2 my-5>1 ~ 19</v-flex>
                <v-flex md4>
                  <v-container>
                    <v-row class="mt-3" no-gutters>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#7ED321">
                        </v-card>
                      </v-col>
                      <v-col :cols="6">
                        <v-card class="pa-2" outlined tile color="#F8E71C">
                        </v-card>
                      </v-col>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#F06539">
                        </v-card>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-flex>
              </v-layout>
              <v-divider></v-divider>

              <v-layout>
                <v-flex md3 my-5 class="plac"> ox-LDL* (U/L) </v-flex>

                <v-flex md3 my-5>4.5</v-flex>
                <v-flex md2 my-5>0.03 ~ 6.8</v-flex>
                <v-flex md4>
                  <v-container>
                    <v-row class="mt-3" no-gutters>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#7ED321">
                        </v-card>
                      </v-col>
                      <v-col :cols="6">
                        <v-card class="pa-2" outlined tile color="#F8E71C">
                        </v-card>
                      </v-col>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#F06539">
                        </v-card>
                      </v-col>
                    </v-row>
                  </v-container> -->
          <!-- </v-flex>
              </v-layout>
              <v-divider></v-divider>

              <v-layout>
                <v-flex md3 mt-5 class="plac"> MPO* (pmol/L) </v-flex>

                <v-flex md3 mt-5>383</v-flex>
                <v-flex md2 mt-5>110 ~ 456</v-flex>
                <v-flex md4>
                  <v-container>
                    <v-row class="mt-3" no-gutters>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#7ED321">
                        </v-card>
                      </v-col>
                      <v-col :cols="6">
                        <v-card class="pa-2" outlined tile color="#F8E71C">
                        </v-card>
                      </v-col>
                      <v-col :cols="3">
                        <v-card class="pa-2" outlined tile color="#F06539">
                        </v-card>
                      </v-col>
                    </v-row>
                  </v-container>
                </v-flex>
              </v-layout>
            </v-card>
          </v-container> -->

          <v-flex xs12 md1></v-flex>
        </v-layout>
      </v-flex>
    </v-layout>
    <v-layout align-center wrap>
      <v-flex xs12 md1></v-flex>
      <v-flex xs12 md5>
        <div class="how-inflammation-inc">
          <p>How Inflammation increase geart disease risk</p>
        </div>

        <v-divider class="line-copy-2"></v-divider>

        <div class="plaque-buildup-insid">
          <span
            >Plaque buildup inside the arteries reduces the blood flow. A
            heart<br />
            attack may occur if the blood supply is reduced to the heart. A
            <br />
            damaged heart muscle may not pump as well. This can lead to heart
            <br />failure. A stroke may occur if the blood supply is cut off to
            the brain.<br />
            If the blood supply is reduced in the arms or legs, it may cause
            severe pain and destroy tissue.</span
          >
        </div>

        <div class="think-of-it-like-thi">
          <p>Think of it like this</p>
        </div>

        <v-divider class="line-copy-2"></v-divider>

        <div class="plaque-buildup-insid">
          <span
            >Plaque buildup inside the arteries reduces the blood flow. A
            heart<br />
            attack may occur if the blood supply is reduced to the heart. A
            <br />
            damaged heart muscle may not pump as well. This can lead to heart
            <br />failure. A stroke may occur if the blood supply is cut off to
            the brain.<br />
            If the blood supply is reduced in the arms or legs, it may cause
            severe pain and destroy tissue.</span
          >
        </div>
      </v-flex>
      <v-flex>
        <div class="heart-9_pic">
          <v-img
            contain
            src="../assets/HEART-9.png"
            overlap
            transition="scale-transition"
            width="400px"
            height="655px"
          />
        </div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import EventBus from "@/eventBus/eventBus";

export default {
  component: {},
  created() {
    this.fetchData();
    EventBus.$on("refreshData", () => {
      this.fetchData();
    });
  },
  computed: {
    tooltip_disabled_2(test_result) {
      if (test_result != 21) {
        return true;
      }
      return false;
    },
  },
  name: "HelloWorld",

  data() {
    return {
      test_list: [
        {
          test_name: "PLAC",
          test_result: 21,
          test_range: "< 15",
          score: "",
        },
        {
          test_name: "Homocysteine (μmol/L)",
          test_result: 19,
          test_range: "16 ~ 31",
          score: "",
        },

        {
          test_name: "hs-CRP (mg/L)",
          test_result: 6,
          test_range: "1 ~ 19",
          score: "",
        },
        {
          test_name: "ox-LDL* (U/L)",
          test_result: 4.5,
          test_range: "0.03 ~ 6.8",
          score: "",
        },
        {
          test_name: "MPO* (pmol/L)",
          test_result: 383,
          test_range: "110 ~ 456",
          score: "",
        },
      ],
      headers: [
        {
          text: "TEST NAME",
          value: "test_name",
          class: 'white black--text'
        },
        {
          text: "TEST RESULT",
          value: "test_result",
          class: 'white black--text',
          align: 'center' 

          
        },
        {
          text: "TEST RANGE",
          value: "test_range",
          class: 'white black--text',
          align: 'center' 

        },
        {
          text: "SCORE",
          value: "score",
          width: 250,
          class: 'white black--text',
          align: 'center' 
        },
      ],
    };
  },
};
</script>

<style scoped>
.rectangle-copy {
  height: 255px;
  width: 671px;
  opacity: 0.3;
  border-radius: 13px;
  background-color: #ffffff;
}
.group-3-copy {
  height: 445px;
  width: 795px;
  margin-left: -45px;
}
.heart-6_pic {
  position: absolute;
  margin-top: -74px;
  margin-bottom: -74px;
  margin-left: -233px;
  margin-right: -233px;
}
.heart-8_pic {
  position: absolute;
  margin-top: 170.96px;
  margin-bottom: 170.96px;
  margin-left: 262.12px;
  margin-right: 262.12px;
  z-index: 2;
}
.how-inflammation-inc {
  height: 44px;
  width: 763px;
  color: #eff5fc;
  font-family: Helvetica;
  font-size: 26px;
  font-weight: bold;
  letter-spacing: 0;
  line-height: 31px;
}
.think-of-it-like-thi {
  height: 44px;
  width: 763px;
  color: #eff5fc;
  font-family: Helvetica;
  font-size: 26px;
  font-weight: bold;
  letter-spacing: 0;
  line-height: 31px;
}
.line-copy-2 {
  box-sizing: border-box;
  height: 1px;
  width: 794px;
  border: 1px solid #c2c4ca;
}
.plaque-buildup-insid {
  margin-top: 20px;
  height: 171px;
  width: 486px;
  color: #eff5fc;
  font-family: Helvetica;
  font-size: 16px;
  letter-spacing: 0;
  line-height: 19px;
}
.inflammation-is-your-copy {
  height: 87px;
  width: 783px;
  color: #eff5fc;
  font-family: Helvetica;
  font-size: 16px;
  letter-spacing: 0;
  line-height: 19px;
  margin-top: 21px;
}

.rectangle-green {
  box-sizing: border-box;
  height: 15px;
  width: 68px;
  background-color: #7ed321;
  border: 2px solid black;
}
.header {
  height: 17px;
  width: 92.93px;
  color: #4a4a4a;
  font-family: Helvetica;
  font-size: 14px;
  font-weight: bold;
  letter-spacing: 0;
  line-height: 17px;
}
.white_card {
  height: 39px;
  width: 795px;

  padding-left: 22px;
  padding-top: 13px;
}
/* .theme--dark.v-sheet {
  background-color: #F6F8FA;
} */
.black_card {
  height: 445px;
  width: 795px;
}
.plac {
  height: 19px;
  width: 214.34px;
  color: #ffffff;
  font-family: Helvetica;
  font-size: 16px;
  letter-spacing: 0;
  line-height: 19px;
  margin-left: 32px;
}
.heart-9-pic {
  position: absolute;
}
.tooltip {
  position: relative;
  display: inline-block;
}
.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  background-color: lightgrey;
  color: black;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;

  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: 100%;
  left: 50%;
  margin-left: -60px;
}
.tooltip .tooltiptext::after {
  content: " ";
  position: absolute;
  bottom: 100%; /* At the top of the tooltip */
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent grey transparent;
}

.tooltip:hover .tooltiptext {
  visibility: visible;
}
.line {
  width: 50px;
  height: 47px;
  border-bottom: 2px solid #ffffff;
  position: absolute;
  z-index: 3;
  margin-left: 100px;
  margin-top: 50px;
}
.slope {
  width: 80px;
  margin-top: 112px;
  margin-left: 24px;
  border-bottom: 2px solid #ffffff;
  -o-transform: rotate(155deg); /* IE 9 */
  transform: rotate(155deg);
  position: absolute;
}
.control {
  height: 5px;
  width: 5px;
}
.rounded_rect {
  border-radius: 10px;
  border: 1px solid yellow;
  padding: 20px;
  width: 97px;
  height: 41px;
  position: absolute;
  margin-left: 215px;
  margin-top: 53px;
}
.jane-caution-you {
  height: 94px;
  width: 598px;
  color: #f06539;
  font-family: Helvetica;
  font-size: 24px;

  font-weight: bold;
  letter-spacing: 0;
  line-height: 29px;
}
.if-you-have-a-bloack {
  height: 57px;
  width: 573px;
  color: white;
  font-family: Helvetica;
  font-size: 16px;
  font-style: oblique;
  letter-spacing: 0;
  line-height: 19px;
}
.jane_card {
  height: 255px;
  width: 600px;

  
}
</style>
