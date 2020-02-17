<!--css_fils = [u"/Users/mmw/sofastats/css/default.css"]-->
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html class="dj_gecko dj_contentbox"><head>
<meta http-equiv="P3P" content="CP=&quot;IDC DSP COR CURa ADMa OUR IND PHY ONL COM 
STA&quot;">
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<title>SOFA Statistics Report 2020-02-12_09:19:04</title>

<link rel="stylesheet" type="text/css" href="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/tundra.css">
<script src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/dojo.js"></script>
<script src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/sofastatsdojo_minified.js"></script>
<script src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/sofastats_charts.js"></script>
<script type="text/javascript">
get_ie_script = function(mysrc){
    var script = document.createElement('script');
    script.type = 'text/javascript';
    script.src = mysrc;
    document.getElementsByTagName('head')[0].appendChild(script); 
}
if(dojo.isIE){
    get_ie_script("sofastats_report_extras/arc.xd.js");
    get_ie_script("sofastats_report_extras/gradient.xd.js");
    get_ie_script("sofastats_report_extras/vml.xd.js");
}
makeObjects = function(){

    //n_charts_start
    var n_charts = 2;
    //n_charts_end
    for(var i=0;i<n_charts;i++){
        try{
            window["makechart" + String('00'+i).slice(-2)]();
        } catch(exceptionObject) {
            var keepGoing = true;
        }
    }
};
dojo.addOnLoad(makeObjects);

var DEFAULT_SATURATION  = 100,
DEFAULT_LUMINOSITY1 = 75,
DEFAULT_LUMINOSITY2 = 50,

c = dojox.color,

cc = function(colour){
    return function(){ return colour; };
},

hl = function(colour){

    var a = new c.Color(colour),
        x = a.toHsl();
    if(x.s == 0){
        x.l = x.l < 50 ? 100 : 0;
    }else{
        x.s = DEFAULT_SATURATION;
        if(x.l < DEFAULT_LUMINOSITY2){
            x.l = DEFAULT_LUMINOSITY1;
        }else if(x.l > DEFAULT_LUMINOSITY1){
            x.l = DEFAULT_LUMINOSITY2;
        }else{
            x.l = x.l - DEFAULT_LUMINOSITY2 > DEFAULT_LUMINOSITY1 - x.l 
                ? DEFAULT_LUMINOSITY2 : DEFAULT_LUMINOSITY1;
        }
    }
    return c.fromHsl(x);
}

getfainthex = function(hexcolour){
    var a = new c.Color(hexcolour)
    x = a.toHsl();
    x.s = x.s * 1.5;
    x.l = x.l * 1.25;
    return c.fromHsl(x);
}

makefaint = function(colour){
    var fainthex = getfainthex(colour.toHex());
    return new dojox.color.Color(fainthex);
}

var labelLineBreak = (dojo.isIE) ? "\n" : "<br>";

</script>

<style type="text/css">
<!--
    .dojoxLegendNode {
        border: 1px solid #ccc; 
        margin: 5px 10px 5px 10px; 
        padding: 3px
    }
    .dojoxLegendText {
        vertical-align: text-top; 
        padding-right: 10px
    }
    @media print {
        .screen-float-only{
        float: none;
        }
    }
    
    @media screen {
        .screen-float-only{
        float: left;
        }
    }
-->
</style>
<style type="text/css">
<!--

body {
    background-color: #ffffff;
}
td, th {
    background-color: white;
}
/*
dojo_style_start
outer_bg = u"white"
inner_bg = u"#f2f1f0" # u"#e0d9d5"
axis_label_font_colour = u"#423126"
major_gridline_colour = u"#b8a49e"
gridline_width = 1
stroke_width = 3
tooltip_border_colour = u"#736354"
colour_mappings = [(u"#e95f29", u"#ef7d44"),
    (u"#f4cb3a", u"#f7d858"),
    (u"#4495c3", u"#62add2"),
    (u"#44953a", u"#62ad58"),
    (u"#f43a3a", u"#f75858"),
    ]
connector_style = u"defbrown"
dojo_style_end
*/
    body{
        font-size: 12px;
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
    }
    h1, h2{
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
        font-weight: bold;
    }
    h1{
        font-size: 18px;
    }
    h2{
        font-size: 16px;
    }
    .gui-msg-medium, gui-msg-small{
        color: #29221c;
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
    }
    .gui-msg-medium{
        font-size: 16px;
    }
    *html .gui-msg-medium{
        font-weight: bold;
        font-size: 18px;
    }
    .gui-msg-small{
        font-size: 13px;
        line-height: 150%;
    }
    .gui-note{
        background-color: #e95829;
        color: white;
        font-weight: bold;
        padding: 2px;
    }
    tr, td, th{
        margin: 0;
    }

    .tbltitle0, .tblsubtitle0{
        margin: 0;
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
        font-weight: bold;
        font-size: 14px;
    }
    .tbltitle0{ /*spans*/
        padding: 0;
        font-size: 18px;
    }
    .tblsubtitle0{
        padding: 12px 0px 0px 0px;
        font-size: 14px;
    }
    .tblcelltitle0{ /*th*/
        text-align: left;
        border: none;
        padding: 0px 0px 12px 0px;
        margin: 0;
    }

    th, .rowvar0, .rowval0, .datacell0, .firstdatacell0 {
        border: solid 1px #A1A1A1;
    }
    th{
        margin: 0;
        padding: 0px 6px;
    }
    td{
        padding: 2px 6px;
        border: solid 1px #c0c0c0;
        font-size: 13px;
    }
    .rowval0{
        margin: 0;
    }
    .datacell0, .firstdatacell0{
        text-align: right;
        margin: 0;
    }
    .firstcolvar0, .firstrowvar0, .spaceholder0 {
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
        font-weight: bold;
        font-size: 14px;
        color: white;
    }
    .firstcolvar0, .firstrowvar0{
        background-color: #333435;
    }
    .firstrowvar0{
        border-left: solid 1px #333435;
        border-bottom:  solid 1px #333435;
    }
    .topline0{
        border-top: 2px solid #c0c0c0;
    }
    .spaceholder0 {
        background-color: #CCD9D7;
    }
    .firstcolvar0{
        padding: 9px 6px;
        vertical-align: top;
    }
    .rowvar0, .colvar0{
        font-family: Ubuntu, Helvetica, Arial, sans-serif;
        font-weight: bold;
        font-size: 14px;
        color: #333435;
        background-color: white;
    }
    .colvar0{
        padding: 6px 0px;            
    } 
    .colval0, .measure0{
        font-size: 12px;
        vertical-align: top;
    }
    table {
        border-collapse: collapse;
    }
    tr.total-row0 td{
        font-weight: bold;
        border-top: solid 2px black;
        border-bottom: double 3px black;
    }
    .page-break-before0{
        page-break-before: always;
        border-bottom: none; /*3px dotted #AFAFAF;*/
        width: auto;
        height: 18px;
    }
    td.lbl0{
        text-align: left;
        background-color: #F5F5F5;
    }
    td.right0{
        text-align: right;
    }
    .ftnote-line{
        /* for hr http://www.w3schools.com/TAGS/att_hr_align.asp*/
        width: 300px;
        text-align: left; /* IE and Opera*/
        margin-left: 0; /* Firefox, Chrome, Safari */
    }
    .tbl-header-ftnote0{
        color: white;
    }
    .ftnote{
        color: black;
    }
    /* Tool tip connector arrows */
    .dijitTooltipBelow-defbrown {
	
	    padding-top: 13px;
    }
    .dijitTooltipAbove-defbrown {
	
	    padding-bottom: 13px;
    }
    .tundra .dijitTooltipBelow-defbrown .dijitTooltipConnector {
	
	    top: 0px;
	    left: 3px;
	    background: url("sofastats_report_extras/tooltipConnectorUp-defbrown.png") no-repeat top left !important;
	    width:16px;
	    height:14px;
    }
    .dj_ie .tundra .dijitTooltipBelow-defbrown .dijitTooltipConnector {
	
	    background-image: url("sofastats_report_extras/tooltipConnectorUp-defbrown.gif") !important;
    }
    .tundra .dijitTooltipAbove-defbrown .dijitTooltipConnector {
	
	    bottom: 0px;
	    left: 3px;
	    background:url("sofastats_report_extras/tooltipConnectorDown-defbrown.png") no-repeat top left !important;
	    width:16px;
	    height:14px;
    }
    .dj_ie .tundra .dijitTooltipAbove-defbrown .dijitTooltipConnector {
	    background-image: url("sofastats_report_extras/tooltipConnectorDown-defbrown.gif") !important;
    }
    .dj_ie6 .tundra .dijitTooltipAbove-defbrown .dijitTooltipConnector {
	    bottom: -3px;
    }
    .tundra .dijitTooltipLeft-defbrown {
	    padding-right: 14px;
    }
    .dj_ie6 .tundra .dijitTooltipLeft-defbrown {
	    padding-left: 15px;
    }
    .tundra .dijitTooltipLeft-defbrown .dijitTooltipConnector {
	
	    right: 0px;
	    bottom: 3px;
	    background:url("sofastats_report_extras/tooltipConnectorRight-defbrown.png") no-repeat top left !important;
	    width:16px;
	    height:14px;
    }
    .dj_ie .tundra .dijitTooltipLeft-defbrown .dijitTooltipConnector {
	    background-image: url("sofastats_report_extras/tooltipConnectorRight-defbrown.gif") !important;
    }
    .tundra .dijitTooltipRight-defbrown {
	    padding-left: 14px;
    }
    .tundra .dijitTooltipRight-defbrown .dijitTooltipConnector {
	
	    left: 0px;
	    bottom: 3px;
	    background:url("sofastats_report_extras/tooltipConnectorLeft-defbrown.png") no-repeat top left !important;
	    width:16px;
	    height:14px;
    }
    .dj_ie .tundra .dijitTooltipRight-defbrown .dijitTooltipConnector {
	    background-image: url("sofastats_report_extras/tooltipConnectorLeft-defbrown.gif") !important;
    }

-->
</style>
</head>
<body class="tundra">












<p>N.B. Source edited to reduce redundancy in footnotes (now appearing only at the end of the file) and eliminate the display of multiple copies of the same graph. M. Wanderley on February 13 2020.</p>



<br><br>
<hr style="clear: both;  page-break-before: always ">


<br><br>
<hr style="clear: both; ">

<p>From sofa_db.table04_VP_Ajin_Exp1 on 12/02/2020 at 09:10 am</p>
<p>All data in table included - no filtering</p>



<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<p>Although the distribution of Asynchrony_ is not perfectly 'normal', 
it may still be 'normal' enough for use. View graph to decide. Skew 
(lopsidedness) is 0.86 which is probably a great sign. Kurtosis 
(peakedness or flatness) is 0.0 which is probably a great sign.</p>

<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/000.png">
<!-- _ITEM_TITLE_START --><!--Histogram_Normality check histogram--><!-- _SOFASTATS_ITEM_DIVIDER -->




<br><br>
<hr style="clear: both; ">

<p>From sofa_db.table04b_VP_Ajin_Exp1 on 13/02/2020 at 03:33 pm</p>
<p>All data in table included - no filtering</p>
<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<p>Although the distribution of Ioi_Deviation is not perfectly 'normal',
 it may still be 'normal' enough for use. View graph to decide. Skew 
(lopsidedness) is 0.564 which is probably a great sign. Kurtosis 
(peakedness or flatness) is -0.334 which is probably a great sign.</p>

<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/000b.png">
<!-- _ITEM_TITLE_START --><!--Histogram_Normality check histogram--><!-- _SOFASTATS_ITEM_DIVIDER -->






<br><br>
<hr style="clear: both;  page-break-before: always ">



<br><br>
<hr style="clear: both;  page-break-before: always ">





<p>From sofa_db.table04_VP_Ajin_Exp1 on 12/02/2020 at 09:13 am</p>
<p>All data in table included - no filtering</p>
<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START --><h2>Results of ANOVA test of average Asynchrony_ for Condition groups from "Dl" to "R"</h2><!-- _TBL_TITLE_END -->

<h3><!-- _TBL_SUBTITLE_START -->Analysis of variance table<!-- _TBL_SUBTITLE_END --></h3>
<!-- _REPORT_TABLE_START --><table cellspacing="0">
<thead>
<tr><th class="firstcolvar0">Source</th>
<th class="firstcolvar0">Sum of Squares</th>
<th class="firstcolvar0">df</th>
<th class="firstcolvar0">Mean Sum of Squares</th>
<th class="firstcolvar0">F</th>
<th class="firstcolvar0">p<a class="tbl-header-ftnote0" href="#ft1"><sup>1</sup></a></th></tr>
</thead>
<tbody>
<tr><td>Between</td><td class="right0">16629.553</td><td class="right0">2</td><td class="right0">8314.776</td><td class="right0">19.954</td><td>&lt; 0.001 (4.781e-6)</td></tr>
<tr><td>Within</td><td class="right0">11251.093</td><td class="right0">27</td><td class="right0">416.707</td><td></td><td></td></tr>
</tbody>
</table><!--_REPORT_TABLE_END -->
<!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average As_Analysis of Var--><!-- _SOFASTATS_ITEM_DIVIDER -->
<p>O'Brien's test for homogeneity of variance: 9.507e-3 <a href="#ft2"><sup>2</sup></a></p><!-- _TBL_TITLE_START --><!-- _TBL_TITLE_END -->

<h3><!-- _TBL_SUBTITLE_START -->Group summary details<!-- _TBL_SUBTITLE_END --></h3>
<!-- _REPORT_TABLE_START --><table cellspacing="0">
<thead>
<tr><th class="firstcolvar0">Group</th>
<th class="firstcolvar0">N</th>
<th class="firstcolvar0">Mean</th>
<th class="firstcolvar0">CI 95%<a class="tbl-header-ftnote0" href="#ft3"><sup>3</sup></a></th>
<th class="firstcolvar0">Standard Deviation<a class="tbl-header-ftnote0" href="#ft4"><sup>4</sup></a></th>
<th class="firstcolvar0">Min</th>
<th class="firstcolvar0">Max</th><th class="firstcolvar0">Kurtosis<a class="tbl-header-ftnote0" href="#ft5"><sup>5</sup></a></th><th class="firstcolvar0">Skew<a class="tbl-header-ftnote0" href="#ft6"><sup>6</sup></a></th><th class="firstcolvar0">p abnormal<a class="tbl-header-ftnote0" href="#ft7"><sup>7</sup></a></th></tr>
</thead>
<tbody>
<tr><td class="lbl0">Dl</td><td class="right0">10</td><td class="right0">157.559</td><td class="right0">139.442 - 175.676</td><td class="right0">29.230</td><td class="right0">120.53</td><td class="right0">197.64</td><td class="right0">-1.561</td><td class="right0">0.075</td><td class="right0">0.1812</td></tr>
<tr><td class="lbl0">P</td><td class="right0">10</td><td class="right0">119.879</td><td class="right0">110.582 - 129.176</td><td class="right0">15.000</td><td class="right0">94.78</td><td class="right0">140.52</td><td class="right0">-0.916</td><td class="right0">-0.199</td><td class="right0">0.8722</td></tr>
<tr><td class="lbl0">R</td><td class="right0">10</td><td class="right0">100.909</td><td class="right0">92.811 - 109.007</td><td class="right0">13.066</td><td class="right0">79.32</td><td class="right0">122.37</td><td class="right0">-0.587</td><td class="right0">0.056</td><td class="right0">0.9852</td></tr>
</tbody>
</table><!--_REPORT_TABLE_END -->

<!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Asyn_Group Summary--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/001.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Asynchrony_ for_Dl--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/002.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Asynchrony_ for _P--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/003.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Asynchrony_ for _R--><!-- _SOFASTATS_ITEM_DIVIDER -->





<br><br>
<hr style="clear: both;  page-break-before: always ">


<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Asynchrony_" for Condition groups "Dl" vs "R"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: &lt; 0.001 (2.609e-5) <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 5.595</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 4.840e-3 <a href="#ft2"><sup>2</sup></a></p>







<br><br>
<hr style="clear: both;  page-break-before: always ">


<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Asynchrony_" for Condition groups "Dl" vs "P"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: 1.929e-3 <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 3.627</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 9.507e-3 <a href="#ft2"><sup>2</sup></a></p>




<br><br>
<hr style="clear: both;  page-break-before: always ">

<
<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Asynchrony_" for Condition groups "P" vs "R"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: 7.428e-3 <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 3.016</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 0.6270 <a href="#ft2"><sup>2</sup></a></p>





<br><br>
<hr style="clear: both;  page-break-before: always ">


<br><br>
<hr style="clear: both;  page-break-before: always ">




<p>From sofa_db.table04_VP_Ajin_Exp1 on 12/02/2020 at 09:14 am</p>
<p>All data in table included - no filtering</p>
<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START --><h2>Results of ANOVA test of average Ioi_Deviation for Condition groups from "Dl" to "R"</h2><!-- _TBL_TITLE_END -->

<h3><!-- _TBL_SUBTITLE_START -->Analysis of variance table<!-- _TBL_SUBTITLE_END --></h3>
<!-- _REPORT_TABLE_START --><table cellspacing="0">
<thead>
<tr><th class="firstcolvar0">Source</th>
<th class="firstcolvar0">Sum of Squares</th>
<th class="firstcolvar0">df</th>
<th class="firstcolvar0">Mean Sum of Squares</th>
<th class="firstcolvar0">F</th>
<th class="firstcolvar0">p<a class="tbl-header-ftnote0" href="#ft1"><sup>1</sup></a></th></tr>
</thead>
<tbody>
<tr><td>Between</td><td class="right0">940.472</td><td class="right0">2</td><td class="right0">470.236</td><td class="right0">2.172</td><td>0.1334</td></tr>
<tr><td>Within</td><td class="right0">5845.310</td><td class="right0">27</td><td class="right0">216.493</td><td></td><td></td></tr>
</tbody>
</table><!--_REPORT_TABLE_END -->
<!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Io_Analysis of Var--><!-- _SOFASTATS_ITEM_DIVIDER -->
<p>O'Brien's test for homogeneity of variance: 0.02742 <a href="#ft2"><sup>2</sup></a></p><!-- _TBL_TITLE_START --><!-- _TBL_TITLE_END -->

<h3><!-- _TBL_SUBTITLE_START -->Group summary details<!-- _TBL_SUBTITLE_END --></h3>
<!-- _REPORT_TABLE_START --><table cellspacing="0">
<thead>
<tr><th class="firstcolvar0">Group</th>
<th class="firstcolvar0">N</th>
<th class="firstcolvar0">Mean</th>
<th class="firstcolvar0">CI 95%<a class="tbl-header-ftnote0" href="#ft3"><sup>3</sup></a></th>
<th class="firstcolvar0">Standard Deviation<a class="tbl-header-ftnote0" href="#ft4"><sup>4</sup></a></th>
<th class="firstcolvar0">Min</th>
<th class="firstcolvar0">Max</th><th class="firstcolvar0">Kurtosis<a class="tbl-header-ftnote0" href="#ft5"><sup>5</sup></a></th><th class="firstcolvar0">Skew<a class="tbl-header-ftnote0" href="#ft6"><sup>6</sup></a></th><th class="firstcolvar0">p abnormal<a class="tbl-header-ftnote0" href="#ft7"><sup>7</sup></a></th></tr>
</thead>
<tbody>
<tr><td class="lbl0">Dl</td><td class="right0">10</td><td class="right0">85.168</td><td class="right0">71.957 - 98.379</td><td class="right0">21.315</td><td class="right0">57.25</td><td class="right0">116.5</td><td class="right0">-1.437</td><td class="right0">-0.117</td><td class="right0">0.3181</td></tr>
<tr><td class="lbl0">P</td><td class="right0">10</td><td class="right0">78.808</td><td class="right0">71.619 - 85.997</td><td class="right0">11.598</td><td class="right0">58.36</td><td class="right0">97.64</td><td class="right0">-0.599</td><td class="right0">-0.251</td><td class="right0">0.8976</td></tr>
<tr><td class="lbl0">R</td><td class="right0">10</td><td class="right0">71.465</td><td class="right0">66.638 - 76.292</td><td class="right0">7.788</td><td class="right0">58.23</td><td class="right0">83.49</td><td class="right0">-0.746</td><td class="right0">-0.176</td><td class="right0">0.9471</td></tr>
</tbody>
</table><!--_REPORT_TABLE_END -->

<!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Ioi__Group Summary--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/004.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Ioi_Deviation f_Dl--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/005.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Ioi_Deviation fo_P--><!-- _SOFASTATS_ITEM_DIVIDER -->
<img src="SOFA%20Statistics%20Report%202020-02-12_09%2019%2004b_files/006.png"><!-- _ITEM_TITLE_START --><!--Results of ANOVA test of average Ioi_Deviation fo_R--><!-- _SOFASTATS_ITEM_DIVIDER -->



<br><br>
<hr style="clear: both;  page-break-before: always ">

<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Ioi_Deviation" for Condition groups "Dl" vs "R"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: 0.07226 <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 1.91</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 4.983e-3 <a href="#ft2"><sup>2</sup></a></p>




<br><br>
<hr style="clear: both;  page-break-before: always ">

<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Ioi_Deviation" for Condition groups "Dl" vs "P"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: 0.4181 <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 0.829</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 0.02742 <a href="#ft2"><sup>2</sup></a></p>




<br><br>
<hr style="clear: both;  page-break-before: always ">

<!-- _VISUAL_DIVIDER_BEFORE_THIS -->
<!-- _TBL_TITLE_START -->
<h2>Results of Independent Samples t-test of average "Ioi_Deviation" for Condition groups "P" vs "R"</h2>
<!-- _TBL_TITLE_END -->
<!-- _TBL_SUBTITLE_START --><!-- _TBL_SUBTITLE_END -->

<p>p value: 0.1138 <a href="#ft1"><sup>1</sup></a></p>

<p>t statistic: 1.662</p>

<p>Degrees of Freedom (df): 18</p>

<p>O'Brien's test for homogeneity of variance: 0.2439 <a href="#ft2"><sup>2</sup></a></p>






<br><br>
<hr style="clear: both;  page-break-before: always ">

<br><br>
<hr style="clear: both;  page-break-before: always ">

<p><a id="ft1"></a><sup>1</sup> If p is small, e.g. less than 0.01, or 
0.001, you can assume the result is statistically significant i.e. there
 is a difference between at least two groups. Note: a statistically 
significant difference may not necessarily be of any practical 
significance.</p>
<p><a id="ft2"></a><sup>2</sup> If the value is small, e.g. less than 0.01, or 0.001, you can assume there is a difference in variance.</p>
<p><a id="ft3"></a><sup>3</sup> There is a 95% chance the population 
mean is within the confidence interval calculated for this sample. Don't
 forget, of course, that the population mean could lie well outside the 
interval bounds. Note - many statisticians argue about the best wording 
for this conclusion.</p>
<p><a id="ft4"></a><sup>4</sup> Standard Deviation measures the spread of values.</p>
<p><a id="ft5"></a><sup>5</sup> Kurtosis measures the peakedness or 
flatness of values.  Between -2 and 2 means kurtosis is unlikely to be a
 problem. Between -1 and 1 means kurtosis is quite unlikely to be a 
problem.</p>
<p><a id="ft6"></a><sup>6</sup> Skew measures the lopsidedness of 
values.  Between -2 and 2 means skew is unlikely to be a problem. 
Between -1 and 1 means skew is quite unlikely to be a problem.</p>
<p><a id="ft7"></a><sup>7</sup> This provides a single measure of 
normality. If p is small, e.g. less than 0.01, or 0.001, you can assume 
the distribution is not strictly normal. Note - it may be normal enough 
though.</p>


<div style="position: absolute; left: -10000px; top: 0px; border-width: 0px; margin: 0px; padding: 0px; outline: currentcolor none 0px; font: 10pt Arial;" class=""><br>DL<br>P<br>R<br></div></body></html>
