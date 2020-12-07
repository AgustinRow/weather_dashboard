<template>
 <div class="highlights-item col-md-4 col-sm-6 col-xs-12 border-top">
   <div>
     <fusioncharts
       :type="type"
       :width="width"
       :height="height"
       :containerbackgroundopacity="containerbackgroundopacity"
       :dataformat="dataformat"
       :datasource="datasource"
     ></fusioncharts>
   </div>
 </div>
</template>

<script>
export default {
 props: ["highlights"],
 components: {},
 data() {
   return {
     type: "angulargauge",
     width: "100%",
     height: "100%",
     containerbackgroundopacity: 0,
     dataformat: "json",
     datasource: {
       chart: {
         caption: "Wind speed average",
         captionFontBold: "0",
         captionFontColor: "#000000",
         captionPadding: "30",
         lowerLimit: "0",
         upperLimit: "50",
         lowerLimitDisplay: "1",
         upperLimitDisplay: "+50",
         showValue: "0",
         theme: "fusion",
         baseFont: "Roboto",
         bgAlpha: "0",
         canvasbgAlpha: "0",
         gaugeInnerRadius: "75",
         gaugeOuterRadius: "110",
         pivotRadius: "0",
         pivotFillAlpha: "0",
         valueFontSize: "20",
         valueFontColor: "#000000",
         valueFontBold: "1",
         tickValueDistance: "3",
         autoAlignTickValues: "1",
         majorTMAlpha: "20",
         chartTopMargin: "30",
         chartBottomMargin: "40"
       },
       colorrange: {
         color: [
           {
             minvalue: "0",
             maxvalue: this.highlights.windStatus.windGust,
             code: ""
           },
           {
             minvalue: this.highlights.windStatus.windGust,
             maxvalue: "50",
             code: "#D8EDFF"
           }
         ]
       },
       annotations: {
         groups: [
           {
             items: [
               {
                 id: "val-label",
                 type: "text",
                 text: this.highlights.windStatus.windGust + 'kn',
                 fontSize: "20",
                 font: "Source Sans Pro",
                 fontBold: "1",
                 fillcolor: "#212529",
                 x: "$gaugeCenterX",
                 y: "$gaugeCenterY"
               }
             ]
           }
         ]
       },
       dials: {
         dial: [
           {
             value: this.highlights.windStatus.windGust,
             baseWidth: "0",
             radius: "0",
             borderThickness: "0",
             baseRadius: "0"
           }
         ]
       }
     }
   };
 },
 methods: {},
 computed: {},
 watch: {
   highlights: {
     handler: function() {
         //this.highlights.windStatus.windGust=45;
       this.datasource.colorrange.color[0].maxvalue = this.highlights.windStatus.windGust;
       this.datasource.colorrange.color[1].minvalue = this.highlights.windStatus.windGust;
       this.datasource.annotations.groups[0].items[0].text = this.highlights.windStatus.windSpeed + ' /kn';
       if(this.highlights.windStatus.windGust <=8){
           this.datasource.colorrange.color[0].code= '#3cd5f1'
       } else{
           if(this.highlights.windStatus.windGust <= 12){
                this.datasource.colorrange.color[0].code= '#28f51b'
            } else {
                if(this.highlights.windStatus.windGust <= 16){
                    this.datasource.colorrange.color[0].code= ' #DAF7A6 '
                } else{
                    if(this.highlights.windStatus.windGust<= 20){
                        this.datasource.colorrange.color[0].code= ' #FFC300 '
                    }else{
                        if(this.highlights.windStatus.windGust<= 25){
                            this.datasource.colorrange.color[0].code= '#FF5733  '
                        }
                        else{
                            if(this.highlights.windStatus.windGust<= 30){
                                this.datasource.colorrange.color[0].code= ' #C70039   '
                            }else{
                                this.datasource.colorrange.color[0].code= ' #ea37ca   '
                            }   
                        }
                    }
                }
            }
       }
       
     },
     deep: true
   }
 },
};
</script>
