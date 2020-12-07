<template>
 <div class="highlights-item col-md-4 col-sm-6 col-xs-12 border-left border-right border-top">
   <div>
     <fusioncharts
       :type="type"
       :width="width"
       :height="height"
       :containerbackgroundopacity="containerbackgroundopacity"
       :dataformat="dataformat"
       :datasource="datasource"
     >
     </fusioncharts>
     </div>
 </div>
</template>

<script>
export default {
 props: ["highlights"],
 components: {},
 methods: {
 setWindStatus: function (){
    var directionVal = void 0;
    var directionDisplay = void 0;
    var colorRangeArr = [{ "minValue": "0", "maxValue": "30", "code": this.highlights.p_color }, // s - south
    { "minValue": "30", "maxValue": "45", "code": this.highlights.s_color }, // ssw - south south west
    { "minValue": "45", "maxValue": "75", "code": this.highlights.s_color }, // sw - south west
    { "minValue": "75", "maxValue": "90", "code": this.highlights.s_color }, // wsw - west south west
    { "minValue": "90", "maxValue": "120", "code": this.highlights.s_color }, // w - west
    { "minValue": "120", "maxValue": "135", "code": this.highlights.s_color }, // wnw - west north west
    { "minValue": "135", "maxValue": "165", "code": this.highlights.s_color }, // nw - north west
    { "minValue": "165", "maxValue": "180", "code": this.highlights.s_color }, // nnw - north north west
    { "minValue": "180", "maxValue": "210", "code": this.highlights.s_color }, // n - north
    { "minValue": "210", "maxValue": "225", "code": this.highlights.s_color }, // nne - north north east
    { "minValue": "225", "maxValue": "255", "code": this.highlights.s_color }, // ne - north east
    { "minValue": "255", "maxValue": "270", "code": this.highlights.s_color }, // ene - east north east
    { "minValue": "270", "maxValue": "300", "code": this.highlights.s_color }, // e - east
    { "minValue": "300", "maxValue": "315", "code": this.highlights.s_color }, // ese - east south east
    { "minValue": "315", "maxValue": "345", "code": this.highlights.s_color }, // se - south east
    { "minValue": "345", "maxValue": "360", "code": this.highlights.s_color }];
    switch (this.highlights.windStatus.windDirection) {
        case "S":
            {
                // south
                for (var _i = 0; _i < colorRangeArr.length; _i++) {
                    if (_i === 0) {
                        colorRangeArr[_i].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i].code = this.highlights.s_color;
                    }
                }
                directionVal = "15";
                directionDisplay = "↓  S";
            }
            break;

        case "SSW":
            {
                // south south west
                for (var _i2 = 0; _i2 < colorRangeArr.length; _i2++) {
                    if (_i2 === 1) {
                        colorRangeArr[_i2].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i2].code = this.highlights.s_color;
                    }
                }
                directionVal = "37.5";
                directionDisplay = "↙ SSW";
            }
            break;

        case "SW":
            {
                // south west
                for (var _i3 = 0; _i3 < colorRangeArr.length; _i3++) {
                    if (_i3 === 2) {
                        colorRangeArr[_i3].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i3].code = this.highlights.s_color;
                    }
                }
                directionVal = "60";
                directionDisplay = "↙ SW";
            }
            break;

        case "WSW":
            {
                // west south west
                for (var _i4 = 0; _i4 < colorRangeArr.length; _i4++) {
                    if (_i4 === 3) {
                        colorRangeArr[_i4].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i4].code = this.highlights.s_color;
                    }
                }
                directionVal = "82.5";
                directionDisplay = "↙ WSW";
            }
            break;

        case "W":
            {
                // west
                for (var _i5 = 0; _i5 < colorRangeArr.length; _i5++) {
                    if (_i5 === 4) {
                        colorRangeArr[_i5].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i5].code = this.highlights.s_color;
                    }
                }
                directionVal = "105";
                directionDisplay = "← W";
            }
            break;

        case "WNW":
            {
                // west north west
                for (var _i6 = 0; _i6 < colorRangeArr.length; _i6++) {
                    if (_i6 === 5) {
                        colorRangeArr[_i6].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i6].code = this.highlights.s_color;
                    }
                }
                directionVal = "127.5";
                directionDisplay = "↖ WNW";
            }
            break;

        case "NW":
            {
                // north west
                for (var _i7 = 0; _i7 < colorRangeArr.length; _i7++) {
                    if (_i7 === 6) {
                        colorRangeArr[_i7].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i7].code = this.highlights.s_color;
                    }
                }
                directionVal = "150";
                directionDisplay = "↖ NW";
            }
            break;

        case "NNW":
            {
                // north north west
                for (var _i8 = 0; _i8 < colorRangeArr.length; _i8++) {
                    if (_i8 === 7) {
                        colorRangeArr[_i8].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i8].code = this.highlights.s_color;
                    }
                }
                directionVal = "172.5";
                directionDisplay = "↖ NNW";
            }
            break;

        case "N":
            {
                // north
                for (var _i9 = 0; _i9 < colorRangeArr.length; _i9++) {
                    if (_i9 === 8) {
                        colorRangeArr[_i9].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i9].code = this.highlights.s_color;
                    }
                }
                directionVal = "195";
                directionDisplay = "↑ N";
            }
            break;

        case "NNE":
            {
                // north north east
                for (var _i10 = 0; _i10 < colorRangeArr.length; _i10++) {
                    if (_i10 === 9) {
                        colorRangeArr[_i10].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i10].code = this.highlights.s_color;
                    }
                }
                directionVal = "217.5";
                directionDisplay = "↗ NNE";
            }
            break;

        case "NE":
            {
                // north east
                for (var _i11 = 0; _i11 < colorRangeArr.length; _i11++) {
                    if (_i11 === 10) {
                        colorRangeArr[_i11].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i11].code = this.highlights.s_color;
                    }
                }
                directionVal = "240";
                directionDisplay = "↗ NE";
            }
            break;

        case "ENE":
            {
                // east north east
                for (var _i12 = 0; _i12 < colorRangeArr.length; _i12++) {
                    if (_i12 === 11) {
                        colorRangeArr[_i12].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i12].code = this.highlights.s_color;
                    }
                }
                directionVal = "262.5";
                directionDisplay = "↗ ENE";
            }
            break;

        case "E":
            {
                // east
                for (var _i13 = 0; _i13 < colorRangeArr.length; _i13++) {
                    if (_i13 === 12) {
                        colorRangeArr[_i13].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i13].code = this.highlights.s_color;
                    }
                }
                directionVal = "285";
                directionDisplay = "→ E";
            }
            break;

        case "ESE":
            {
                // east south east
                for (var _i14 = 0; _i14 < colorRangeArr.length; _i14++) {
                    if (_i14 === 13) {
                        colorRangeArr[_i14].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i14].code = this.highlights.s_color;
                    }
                }
                directionVal = "307.5";
                directionDisplay = "↘ ESE";
            }
            break;

        case "SE":
            {
                // south east
                for (var _i15 = 0; _i15 < colorRangeArr.length; _i15++) {
                    if (_i15 === 14) {
                        colorRangeArr[_i15].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i15].code = this.highlights.s_color;
                    }
                }
                directionVal = "330";
                directionDisplay = "↘ SE";
            }
            break;

        case "SSE":
            {
                // south south east
                for (var _i16 = 0; _i16 < colorRangeArr.length; _i16++) {
                    if (_i16 === 15) {
                        colorRangeArr[_i16].code = this.highlights.p_color;
                    } else {
                        colorRangeArr[_i16].code = this.highlights.s_color;
                    }
                }
                directionVal = "352.5";
                directionDisplay = "↘ SSE";
            }
            break;

        default:
            alert("Please pass valid parameters");
            break;
    }
    this.datasource.colorRange.color = colorRangeArr;
    this.datasource.annotations.groups[0].items[0].text = this.highlights.windStatus.windGust;
    this.datasource.annotations.groups[0].items[0].color = this.p_color;
    this.datasource.annotations.groups[0].items[1].text = directionDisplay;
    this.datasource.annotations.groups[0].items[1].color = this.p_color;
    this.datasource.dials.dial[0].value = directionVal;
    this.datasource.trendpoints.point[0].startValue = directionVal;
    this.datasource.trendpoints.point[0].color = this.p_color;
    this.datasource.trendpoints.point[0].borderColor =this. p_color;
    //var data = JSON.parse(localStorage.getItem('dataForWindChart'));
    //data.dataSource = windStausChartData;
    //return data;
 }
 },
 computed: {},
 data() {
   return {
    type: 'angulargauge',
    width: '100%',
    height: '100%',
    containerBackgroundOpacity:'0.8',
    dataFormat: 'json',
    renderAt: 'chart-container',
    creditLabel: false,
    datasource: {
        chart: {
            caption: "Wind speed average2",
            bgColor:"#ffffff",
            bgAlpha:"0",
            manageresize: "1",
            gaugeStartAngle: "285",
            gaugeEndAngle: "-75",
            upperLimit: "360",
            lowerLimit: "0",
            gaugeFillMix: "{light+0}",
            showShadow: "0",
            showGaugeBorder: "0",
            showTickValues: "0",
            majorTMAlpha: "0",
            minorTMAlpha: "0",
            pivotRadius: "0",
            pivotBorderThickness: "0",
            gaugeInnerRadius:"65",
            gaugeOuterRadius:"80",
            baseFont:"Roboto",
            baseFontSize:"14",
            baseFontBold: "1",
            gaugeFillAlpha: "10",
            showBorder: "0",
            showToolTip: "0"
        },

        colorRange: {
            "color": ""
        },

        annotations: {
            groups: [{
                items: [{
                    id: "speeddesc",
                    type: "text",
                    text: "",
                    x: "$gaugeCenterX",
                    y: "$gaugeCenterY - 15",
                    color: "",
                    bold: "0",
                    fontSize: "16",
                    font: "Roboto"
                }, {
                    id: "speeddir",
                    type: "text",
                    text: "",
                    x: "$gaugeCenterX",
                    y: "$gaugeCenterY + 10",
                    color: "",
                    bold: "0",
                    fontSize: "16",
                    font: "Source Sans Pro Light"
                }]
            }]
        },

        dials: {
            dial: [
                {
                    value: "",
                    baseWidth: "0",
                    borderThickness: "0",
                    radius: "0",
                    baseRadius: "0"
                }
            ]
        },

        trendpoints: {
            point: [
                {
                    startValue: "",
                    displayValue: " ",
                    color: "",
                    borderColor: "",
                    thickness: "4.5",
                    alpha: "100",
                    useMarker: "1",
                    valueInside: "0",
                    innerRadius: "75",
                    markerRadius: "-7"
                }
            ]
        }
    }
}
},
 watch: {
   highlights: {
     handler: function() {
        this.setWindStatus();
        this.datasource.annotations[0].items[0].text = this.highlights.windStatus.windGust;
        this.datasource.annotations[0].items[2].text= this.highlights.windStatus.windDirection;
     },
     deep: true
   }
 }
 }
</script>
