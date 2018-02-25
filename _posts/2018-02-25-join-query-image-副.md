---
layout:         post
title:          数据库中的插入查询
subtitle:       
card-image:     http://www.antchenxi.com/images/2018-2-25/1.png
date:           2018-02-25 12:12:56
tags:           数据库
post-card-type: image
---



<html>
  <head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <title>数据库应用系统生命周期</title>
    <style>
        body{
            margin: 0;
        }
        #content-info{
            width: auto;
            margin: 0 auto;
            text-align: center;
        }
        #author-info{
            white-space: nowrap;
            text-overflow: ellipsis;
            overflow: hidden;
        }
        #title{
            text-overflow: ellipsis;
            white-space: nowrap;
            overflow: hidden;
            padding-top: 10px;
            margin-bottom: 2px;
            font-size: 34px;
            color: #505050;
        }
        .text{
            white-space:nowrap;
            text-overflow: ellipsis;
            display: inline-block;
            margin-right: 20px;
            margin-bottom: 2px;
            font-size: 20px;
            color: #8c8c8c;
        }
        #navBar{
            width: auto;
            height: auto;
            position: fixed;
            right:0;
            bottom: 0;
            background-color: #f0f3f4;
            overflow-y: auto;
            text-align: center;
        }
        #svg-container{
            width: 100%;
            overflow-x: scroll;
            min-width: 0px;
            margin: 0 10px;
        }
        #nav-thumbs{
            overflow-y: scroll;
            padding: 0 5px;
        }
        .nav-thumb{
            position: relative;
            margin: 10px auto;
        }
        .nav-thumb >p{
            text-align: center;
            font-size: 12px;
            margin: 4px 0 0 0;
        }
        .nav-thumb >div{
            position: relative;
            display: inline-block;
            border: 1px solid #c6cfd5;
        }
        .nav-thumb img{
            display: block;
        }
        #main-content{
            bottom: 0;
            left: 0;
            right: 0;
            background-color: #d0cfd8;
            display: flex;
            height: auto;
            flex-flow: row wrap;
            text-align:center;
        }
        #svg-container >svg{
            display: block;
            margin:10px auto;
            margin-bottom: 0;
        }
        #copyright{
            bottom: 0;
            left: 50%;
            margin: 5px auto;
            font-size: 16px;
            color: #515151;
        }
        #copyright >a{
            text-decoration: none;
            color: #77C;
        }
        .number{
            position: absolute;
            top:0;
            left:0;
            border-top:22px solid #08a1ef;
            border-right: 22px solid transparent;
        }
        .pagenum{
            font-size: 12px;
            color: #fff;
            position: absolute;
            top: -23px;
            left: 2px;
        }
            #navBar::-webkit-scrollbar{
            width: 8px;
            background-color: #f5f5f5;
        }
            #navBar::-webkit-scrollbar-track{
            -webkit-box-shadow: inset 0 0 4px rgba(0,0,0,.3);
            border-radius: 8px;
            background-color: #fff;
        }
            #navBar::-webkit-scrollbar-thumb{
            border-radius: 8px;
            -webkit-box-shadow: inset 0 0 4px rgba(0,0,0,.3);
            background-color: #6b6b70;
        }
        #navBar::-webkit-scrollbar-thumb:hover{
            background-color: #4a4a4f;
        }
</style>
  </head>
  <body>
    <div id="main-area">
      <div id="content-info">
        <div id="content-info">
          <div id="title">数据库应用系统生命周期</div>
        </div>
        <div id="author-info">
          <div class="text" id="author-name">LonelyAnt</div>
          <div class="text" id="share-time">2018-02-25</div>
        </div>
      </div>
      <div id="main-content">
        <div id="svg-container"><svg xmlns="http://www.w3.org/2000/svg" ed:name="Page-1" viewBox="0 0 1622 2286" id="page1" xmlns:xlink="http://www.w3.org/1999/xlink" height="2285" width="1622" ed:vSpacing="30" preserveAspectRadio="xMinYMin meet" xmlns:ed="http://www.edrawsoft.cn/xml/2017/SVGExtensions/" xmlns:ev="http://www.w3.org/2001/xml-events" ed:hSpacing="30">
    <style type="text/css"><![CDATA[
g[ed\:togtopicid],g[ed\:hyperlink],g[ed\:comment],g[ed\:note] {cursor:pointer;}
g[id] {-moz-user-select: none;-ms-user-select: none;user-select: none;}
svg text::selection,svg tspan::selection{background-color: #4285f4;color: #ffffff;fill: #ffffff;}
.st1 {fill:#f96628;font-family:微软雅黑;font-size:9pt}
.st3 {fill:#ffffff;font-family:微软雅黑;font-size:11pt}
.st5 {fill:#ffffff;font-family:微软雅黑;font-size:14pt}
.st4 {fill:#ffffff;font-family:微软雅黑;font-size:9pt}
.st2 {fill:#ffffff}
]]></style>
    <defs>
        <linearGradient y2="100%" y1="0%" id="lg1" x1="0%" x2="0%">
            <stop offset="0" stop-color="#ffffff"/>
            <stop offset="0.25" stop-color="#f0f5f0"/>
            <stop offset="0.75" stop-color="#e1ebe1"/>
            <stop offset="1" stop-color="#c8d7c8"/>
        </linearGradient>
    </defs>
    <rect height="2286" width="1622" x="0" fill="#1e242f" y="0"/>
    <path id="317" stroke-linejoin="round" transform="translate(831,1581.7)" stroke="#e0a7d3" ed:type="summary" ed:idlist="271,273,275,277,279,281,283,285,287,289,291,301,303,305,307,309,311,313,293,295,297,299" ed:parentid="271,283,291,293" fill="none" d="M0,0C0,0,5.2,-0.7,6.6,62.4C8,125.5,4.7,165.2,5.9,215C7,264.8,12,276.4,12,276.4C12,276.4,7.1,286.6,5.9,338C4.6,389.3,8,427.7,6.6,490.6C5.2,553.5,0,552.9,0,552.9"/>
    <g id="164" transform="translate(759.35,669.55)" ed:width="299" ed:topictype="callout" ed:parentid="153" ed:layout="rightmap" ed:height="69">
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,0L47.3,-0L-80.2,-54.1L75.3,0L299,0L299,69L0,69L0,0z"/>
        <text class="st1">
            <tspan class="st2" style="white-space:pre" x="17" y="21.5">数据需求分析是从对数据进行组织与存储的角度</tspan>
            <tspan class="st2" style="white-space:pre" x="17" y="38.5">从用户视图出发，分析与辨识应用领域所管理的</tspan>
            <tspan class="st2" style="white-space:pre" x="17" y="55.5">各类数据项和数据结构，形成</tspan>
            <tspan style="white-space:pre">数据字典</tspan>
            <tspan class="st2" style="white-space:pre">的主要内容</tspan>
        </text>
    </g>
    <g id="102" transform="translate(478,328.45)" ed:width="208" ed:parentid="101" ed:height="42">
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,0L208,0L208,42L0,42L0,0z"/>
        <path id="103" stroke-linejoin="round" transform="translate(-97,417.67)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M34,396.7L61.3,396.7L61.3,-390.7C61.3,-394,64,-396.7,67.3,-396.7L97,-396.7"/>
        <text class="st3">
            <tspan style="white-space:pre" textLength="165" lengthAdjust="spacing" x="22" y="26.5">项目规划（规划与分析）</tspan>
        </text>
    </g>
    <g id="104" transform="translate(478,804.7)" ed:width="103" ed:parentid="101" ed:height="42">
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,0L103,0L103,42L0,42L0,0z"/>
        <path id="105" stroke-linejoin="round" transform="translate(-97,179.55)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M34,158.5L61.3,158.5L61.3,-152.5C61.3,-155.9,64,-158.5,67.3,-158.5L97,-158.5"/>
        <text class="st3">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="22" y="26.5">需求分析</tspan>
        </text>
    </g>
    <g id="106" transform="translate(478,1442.05)" ed:width="118" ed:parentid="101" ed:height="42">
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,0L118,0L118,42L0,42L0,0z"/>
        <path id="107" stroke-linejoin="round" transform="translate(-97,-139.13)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M34,-160.1L61.3,-160.1L61.3,154.1C61.3,157.4,64,160.1,67.3,160.1L97,160.1"/>
        <text class="st3">
            <tspan style="white-space:pre" textLength="75" lengthAdjust="spacing" x="22" y="26.5">实现与部署</tspan>
        </text>
    </g>
    <g id="108" transform="translate(478,1202.95)" ed:width="103" ed:parentid="101" ed:height="42">
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,0L103,0L103,42L0,42L0,0z"/>
        <path id="109" stroke-linejoin="round" transform="translate(-97,-19.58)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M34,-40.6L61.3,-40.6L61.3,34.6C61.3,37.9,64,40.6,67.3,40.6L97,40.6"/>
        <text class="st3">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="22" y="26.5">系统设计</tspan>
        </text>
    </g>
    <g id="110" transform="translate(478,1837.15)" ed:width="118" ed:parentid="101" ed:height="42">
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,0L118,0L118,42L0,42L0,0z"/>
        <path id="111" stroke-linejoin="round" transform="translate(-97,-336.67)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M34,-357.7L61.3,-357.7L61.3,351.7C61.3,355,64,357.7,67.3,357.7L97,357.7"/>
        <text class="st3">
            <tspan style="white-space:pre" textLength="75" lengthAdjust="spacing" x="22" y="26.5">运行与维护</tspan>
        </text>
    </g>
    <g id="112" transform="translate(610,1119.1)" ed:width="56" ed:parentid="108" ed:height="22.5">
        <path id="113" stroke-linejoin="round" transform="translate(-14.5,63.67)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,41.2L2.6,41.2L2.6,-35.2C2.6,-38.5,5.3,-41.2,8.6,-41.2L14.5,-41.2"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">概念设计</tspan>
        </text>
    </g>
    <g id="114" transform="translate(610,1197.1)" ed:width="56" ed:parentid="108" ed:height="22.5">
        <path id="115" stroke-linejoin="round" transform="translate(-14.5,24.67)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,2.2L2.6,2.2C2.6,-0.2,5.3,-2.2,8.6,-2.2L14.5,-2.2"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">逻辑设计</tspan>
        </text>
    </g>
    <g id="116" transform="translate(610,1290.7)" ed:width="56" ed:parentid="108" ed:height="22.5">
        <path id="117" stroke-linejoin="round" transform="translate(-14.5,-22.13)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,-44.6L2.6,-44.6L2.6,38.6C2.6,41.9,5.3,44.6,8.6,44.6L14.5,44.6"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">物理设计</tspan>
        </text>
    </g>
    <g id="118" transform="translate(715,197.8)" ed:width="92" ed:parentid="102" ed:height="22.5">
        <path id="119" stroke-linejoin="round" transform="translate(-14.5,87.08)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,64.6L2.6,64.6L2.6,-58.6C2.6,-61.9,5.3,-64.6,8.6,-64.6L14.5,-64.6"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">系统规划与定义</tspan>
        </text>
    </g>
    <g id="120" transform="translate(715,322.6)" ed:width="68" ed:parentid="102" ed:height="22.5">
        <path id="121" stroke-linejoin="round" transform="translate(-14.5,24.68)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,2.2L2.6,2.2C2.6,-0.2,5.3,-2.2,8.6,-2.2L14.5,-2.2"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">可行性分析</tspan>
        </text>
    </g>
    <g id="122" transform="translate(715,463)" ed:width="56" ed:parentid="102" ed:height="22.5">
        <path id="123" stroke-linejoin="round" transform="translate(-14.5,-45.52)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-68L2.6,-68L2.6,62C2.6,65.3,5.3,68,8.6,68L14.5,68"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">项目规划</tspan>
        </text>
    </g>
    <g id="124" transform="translate(836,151)" ed:width="56" ed:parentid="118" ed:height="22.5">
        <path id="125" stroke-linejoin="round" transform="translate(-14.5,45.9)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,23.4L2.6,23.4L2.6,-17.4C2.6,-20.7,5.3,-23.4,8.6,-23.4L14.5,-23.4"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">任务陈述</tspan>
        </text>
        <g ed:note="&lt;body style=&quot; font-family:'SimSun'; font-size:9pt; font-weight:400; font-style:normal;&quot;>&lt;p style=&quot; margin-top:0px; margin-bottom:0px; margin-left:0px; margin-right:0px; -qt-block-indent:0; text-indent:0px; line-height:100%;&quot;>&lt;span style=&quot; font-family:'Arial';&quot;>描述所要开发的DBAS的总体目标&lt;/span>&lt;/p>&lt;/body>">
            <use xlink:href="#note" transform="translate(40,-16)"/>
        </g>
    </g>
    <g id="126" transform="translate(836,182.2)" ed:width="80" ed:parentid="118" ed:height="22.5">
        <path id="127" stroke-linejoin="round" transform="translate(-14.5,30.3)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,7.8L2.6,7.8L2.6,-1.8C2.6,-5.1,5.3,-7.8,8.6,-7.8L14.5,-7.8"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">确定任务目标</tspan>
        </text>
    </g>
    <g id="128" transform="translate(836,244.6)" ed:width="80" ed:parentid="118" ed:height="22.5">
        <path id="129" stroke-linejoin="round" transform="translate(-14.5,-0.9)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-23.4L2.6,-23.4L2.6,17.4C2.6,20.7,5.3,23.4,8.6,23.4L14.5,23.4"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">确定用户视图</tspan>
        </text>
    </g>
    <g id="130" transform="translate(812,307)" ed:width="68" ed:parentid="120" ed:height="22.5">
        <path id="131" stroke-linejoin="round" transform="translate(-14.5,30.3)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,7.8L2.6,7.8L2.6,-1.8C2.6,-5.1,5.3,-7.8,8.6,-7.8L14.5,-7.8"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">技术可行性</tspan>
        </text>
    </g>
    <g id="132" transform="translate(812,275.8)" ed:width="68" ed:parentid="120" ed:height="22.5">
        <path id="133" stroke-linejoin="round" transform="translate(-14.5,45.9)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,23.4L2.6,23.4L2.6,-17.4C2.6,-20.7,5.3,-23.4,8.6,-23.4L14.5,-23.4"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">经济可行性</tspan>
        </text>
    </g>
    <g id="134" transform="translate(812,338.2)" ed:width="68" ed:parentid="120" ed:height="22.5">
        <path id="135" stroke-linejoin="round" transform="translate(-14.5,14.7)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-7.8L2.6,-7.8L2.6,1.8C2.6,5.1,5.3,7.8,8.6,7.8L14.5,7.8"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">操作可行性</tspan>
        </text>
    </g>
    <g id="136" transform="translate(812,369.4)" ed:width="80" ed:parentid="120" ed:height="22.5">
        <path id="137" stroke-linejoin="round" transform="translate(-14.5,-0.9)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-23.4L2.6,-23.4L2.6,17.4C2.6,20.7,5.3,23.4,8.6,23.4L14.5,23.4"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">开发方案选择</tspan>
        </text>
    </g>
    <g id="138" transform="translate(800,400.6)" ed:width="56" ed:parentid="122" ed:height="22.5">
        <path id="139" stroke-linejoin="round" transform="translate(-14.5,53.7)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,31.2L2.6,31.2L2.6,-25.2C2.6,-28.5,5.3,-31.2,8.6,-31.2L14.5,-31.2"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">项目团队</tspan>
        </text>
    </g>
    <g id="140" transform="translate(800,431.8)" ed:width="56" ed:parentid="122" ed:height="22.5">
        <path id="141" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">项目环境</tspan>
        </text>
    </g>
    <g id="142" transform="translate(800,463)" ed:width="56" ed:parentid="122" ed:height="22.5">
        <path id="143" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-0L2.6,-0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">项目活动</tspan>
        </text>
    </g>
    <g id="144" transform="translate(800,494.2)" ed:width="56" ed:parentid="122" ed:height="22.5">
        <path id="145" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">成本预算</tspan>
        </text>
    </g>
    <g id="146" transform="translate(800,525.4)" ed:width="56" ed:parentid="122" ed:height="22.5">
        <path id="147" stroke-linejoin="round" transform="translate(-14.5,-8.7)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-31.2L2.6,-31.2L2.6,25.2C2.6,28.5,5.3,31.2,8.6,31.2L14.5,31.2"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">进度计划</tspan>
        </text>
    </g>
    <g id="148" transform="translate(836,213.4)" ed:width="92" ed:parentid="118" ed:height="22.5">
        <path id="149" stroke-linejoin="round" transform="translate(-14.5,14.7)" stroke="#a5c44c" stroke-linecap="round" fill="none" d="M-14.5,-7.8L2.6,-7.8L2.6,1.8C2.6,5.1,5.3,7.8,8.6,7.8L14.5,7.8"/>
        <path stroke-linejoin="round" stroke="#a5c44c" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">确定范围和边界</tspan>
        </text>
        <g ed:note="&lt;body style=&quot; font-family:'SimSun'; font-size:9pt; font-weight:400; font-style:normal;&quot;>&lt;p style=&quot; margin-top:0px; margin-bottom:0px; margin-left:0px; margin-right:0px; -qt-block-indent:0; text-indent:0px; line-height:100%;&quot;>&lt;span style=&quot; font-family:'Arial';&quot;>系统范围和边界定义了DBAS做什么，不做什么，做到什么程度，是DBAS需求分析和系统设计等后续开发步骤的设计依据&lt;/span>&lt;/p>&lt;/body>">
            <use xlink:href="#note" transform="translate(76,-16)"/>
        </g>
    </g>
    <g id="153" transform="translate(610,592.9)" ed:width="80" ed:parentid="104" ed:height="22.5">
        <path id="154" stroke-linejoin="round" transform="translate(-14.5,127.65)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,105.1L2.6,105.1L2.6,-99.1C2.6,-102.5,5.3,-105.1,8.6,-105.1L14.5,-105.1"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">数据需求分析</tspan>
        </text>
    </g>
    <g id="155" transform="translate(610,802)" ed:width="224" ed:parentid="104" ed:height="22.5">
        <path id="156" stroke-linejoin="round" transform="translate(-14.5,23.1)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,0.6L2.6,0.6C2.6,-0.1,5.3,-0.6,8.6,-0.6L14.5,-0.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L224,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="216" lengthAdjust="spacing" x="4" y="15.8">功能需求分析，描述一个系统应该做什么</tspan>
        </text>
    </g>
    <g id="165" transform="translate(1087.35,692.8)" ed:width="56" ed:parentid="164" ed:height="22.5">
        <path id="178" stroke-linejoin="round" transform="translate(-14.5,16.88)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-5.6L2.6,-5.6L2.6,-0.4C2.6,2.9,5.3,5.6,8.6,5.6L14.5,5.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">数据字典</tspan>
        </text>
    </g>
    <g id="166" transform="translate(1172.35,630.4)" ed:width="125" ed:parentid="165" ed:height="22.5">
        <path id="167" stroke-linejoin="round" transform="translate(-14.5,53.7)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,31.2L2.6,31.2L2.6,-25.2C2.6,-28.5,5.3,-31.2,8.6,-31.2L14.5,-31.2"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L125,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="117" lengthAdjust="spacing" x="4" y="15.8">数据项（Data Item）</tspan>
        </text>
        <g ed:note="&lt;body style=&quot; font-family:'SimSun'; font-size:9pt; font-weight:400; font-style:normal;&quot;>&lt;p style=&quot; margin-top:0px; margin-bottom:0px; margin-left:0px; margin-right:0px; -qt-block-indent:0; text-indent:0px; line-height:100%;&quot;>&lt;span style=&quot; font-family:'Arial';&quot;>数据的最小组成单位&lt;/span>&lt;/p>&lt;/body>">
            <use xlink:href="#note" transform="translate(109,-16)"/>
        </g>
    </g>
    <g id="170" transform="translate(1172.35,661.6)" ed:width="56" ed:parentid="165" ed:height="22.5">
        <path id="171" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">数据结构</tspan>
        </text>
        <g ed:note="&lt;body style=&quot; font-family:'SimSun'; font-size:9pt; font-weight:400; font-style:normal;&quot;>&lt;p style=&quot; margin-top:0px; margin-bottom:0px; margin-left:0px; margin-right:0px; -qt-block-indent:0; text-indent:0px; line-height:100%;&quot;>&lt;span style=&quot; font-family:'Arial';&quot;>若干个数据项可以组成一个数据结构&lt;/span>&lt;/p>&lt;/body>">
            <use xlink:href="#note" transform="translate(40,-16)"/>
        </g>
    </g>
    <g id="172" transform="translate(1172.35,692.8)" ed:width="44" ed:parentid="165" ed:height="22.5">
        <path id="173" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-0L2.6,-0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L44,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="36" lengthAdjust="spacing" x="4" y="15.8">数据流</tspan>
        </text>
    </g>
    <g id="174" transform="translate(1172.35,724)" ed:width="56" ed:parentid="165" ed:height="22.5">
        <path id="175" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">数据存储</tspan>
        </text>
    </g>
    <g id="176" transform="translate(1172.35,755.2)" ed:width="56" ed:parentid="165" ed:height="22.5">
        <path id="177" stroke-linejoin="round" transform="translate(-14.5,-8.7)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-31.2L2.6,-31.2L2.6,25.2C2.6,28.5,5.3,31.2,8.6,31.2L14.5,31.2"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">处理过程</tspan>
        </text>
    </g>
    <g id="179" transform="translate(610,895.6)" ed:width="236" ed:parentid="104" ed:height="22.5">
        <path id="180" stroke-linejoin="round" transform="translate(-14.5,-23.7)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-46.2L2.6,-46.2L2.6,40.2C2.6,43.5,5.3,46.2,8.6,46.2L14.5,46.2"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L236,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="228" lengthAdjust="spacing" x="4" y="15.8">性能需求分析，描述系统应该做到什么程度</tspan>
        </text>
    </g>
    <g id="181" transform="translate(610,1004.8)" ed:width="80" ed:parentid="104" ed:height="22.5">
        <path id="182" stroke-linejoin="round" transform="translate(-14.5,-78.3)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-100.8L2.6,-100.8L2.6,94.8C2.6,98.1,5.3,100.8,8.6,100.8L14.5,100.8"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">其他需求分析</tspan>
        </text>
    </g>
    <g id="183" transform="translate(863,786.4)" ed:width="104" ed:parentid="155" ed:height="22.5">
        <path id="184" stroke-linejoin="round" transform="translate(-14.5,30.3)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,7.8L2.6,7.8L2.6,-1.8C2.6,-5.1,5.3,-7.8,8.6,-7.8L14.5,-7.8"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L104,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="96" lengthAdjust="spacing" x="4" y="15.8">数据处理需求分析</tspan>
        </text>
    </g>
    <g id="185" transform="translate(863,817.6)" ed:width="104" ed:parentid="155" ed:height="22.5">
        <path id="186" stroke-linejoin="round" transform="translate(-14.5,14.7)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-7.8L2.6,-7.8L2.6,1.8C2.6,5.1,5.3,7.8,8.6,7.8L14.5,7.8"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L104,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="96" lengthAdjust="spacing" x="4" y="15.8">业务规则需求分析</tspan>
        </text>
    </g>
    <g id="187" transform="translate(875,848.8)" ed:width="224" ed:parentid="179" ed:height="22.5">
        <path id="188" stroke-linejoin="round" transform="translate(-14.5,45.9)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,23.4L2.6,23.4L2.6,-17.4C2.6,-20.7,5.3,-23.4,8.6,-23.4L14.5,-23.4"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L224,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="216" lengthAdjust="spacing" x="4" y="15.8">数据操作响应时间，或数据访问响应时间</tspan>
        </text>
    </g>
    <g id="189" transform="translate(875,880)" ed:width="404" ed:parentid="179" ed:height="22.5">
        <path id="190" stroke-linejoin="round" transform="translate(-14.5,30.3)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,7.8L2.6,7.8L2.6,-1.8C2.6,-5.1,5.3,-7.8,8.6,-7.8L14.5,-7.8"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L404,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="396" lengthAdjust="spacing" x="4" y="15.8">系统吞吐量，指系统在单位时间内可以完成的数据库事务或数据查询的数量</tspan>
        </text>
    </g>
    <g id="191" transform="translate(875,911.2)" ed:width="596" ed:parentid="179" ed:height="22.5">
        <path id="192" stroke-linejoin="round" transform="translate(-14.5,14.7)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-7.8L2.6,-7.8L2.6,1.8C2.6,5.1,5.3,7.8,8.6,7.8L14.5,7.8"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L596,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="588" lengthAdjust="spacing" x="4" y="15.8">允许并发访问的最大用户数，指在保证单个用户查询响应时间的前提下，系统最多允许多少用户同时访问数据库</tspan>
        </text>
    </g>
    <g id="195" transform="translate(875,942.4)" ed:width="233" ed:parentid="179" ed:height="22.5">
        <path id="196" stroke-linejoin="round" transform="translate(-14.5,-0.9)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-23.4L2.6,-23.4L2.6,17.4C2.6,20.7,5.3,23.4,8.6,23.4L14.5,23.4"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L233,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="225" lengthAdjust="spacing" x="4" y="15.8">每TPS代价值，用于衡量系统性价比的指标</tspan>
        </text>
    </g>
    <g id="197" transform="translate(719,973.6)" ed:width="80" ed:parentid="181" ed:height="22.5">
        <path id="198" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">存储需求分析</tspan>
        </text>
    </g>
    <g id="199" transform="translate(719,1004.8)" ed:width="92" ed:parentid="181" ed:height="22.5">
        <path id="200" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">安全性需求分析</tspan>
        </text>
    </g>
    <g id="201" transform="translate(719,1036)" ed:width="116" ed:parentid="181" ed:height="22.5">
        <path id="202" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#7dbd8d" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#7dbd8d" fill="none" d="M0,22.5L116,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="108" lengthAdjust="spacing" x="4" y="15.8">备份和恢复需求分析</tspan>
        </text>
    </g>
    <g id="203" transform="translate(695,1103.5)" ed:width="116" ed:parentid="112" ed:height="22.5">
        <path id="204" stroke-linejoin="round" transform="translate(-14.5,30.3)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,7.8L2.6,7.8L2.6,-1.8C2.6,-5.1,5.3,-7.8,8.6,-7.8L14.5,-7.8"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L116,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="108" lengthAdjust="spacing" x="4" y="15.8">数据库概念模型设计</tspan>
        </text>
    </g>
    <g id="205" transform="translate(695,1134.7)" ed:width="80" ed:parentid="112" ed:height="22.5">
        <path id="206" stroke-linejoin="round" transform="translate(-14.5,14.7)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,-7.8L2.6,-7.8L2.6,1.8C2.6,5.1,5.3,7.8,8.6,7.8L14.5,7.8"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">系统总体设计</tspan>
        </text>
    </g>
    <g id="207" transform="translate(695,1165.9)" ed:width="116" ed:parentid="114" ed:height="22.5">
        <path id="208" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L116,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="108" lengthAdjust="spacing" x="4" y="15.8">数据库逻辑结构设计</tspan>
        </text>
    </g>
    <g id="209" transform="translate(695,1197.1)" ed:width="104" ed:parentid="114" ed:height="22.5">
        <path id="210" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L104,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="96" lengthAdjust="spacing" x="4" y="15.8">应用程序概要设计</tspan>
        </text>
    </g>
    <g id="211" transform="translate(695,1228.3)" ed:width="92" ed:parentid="114" ed:height="22.5">
        <path id="212" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">数据库概要设计</tspan>
        </text>
    </g>
    <g id="213" transform="translate(695,1259.5)" ed:width="116" ed:parentid="116" ed:height="22.5">
        <path id="214" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L116,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="108" lengthAdjust="spacing" x="4" y="15.8">数据库物理结构设计</tspan>
        </text>
    </g>
    <g id="215" transform="translate(695,1290.7)" ed:width="116" ed:parentid="116" ed:height="22.5">
        <path id="216" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L116,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="108" lengthAdjust="spacing" x="4" y="15.8">数据库事务详细设计</tspan>
        </text>
    </g>
    <g id="217" transform="translate(695,1321.9)" ed:width="104" ed:parentid="116" ed:height="22.5">
        <path id="218" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e38d76" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e38d76" fill="none" d="M0,22.5L104,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="96" lengthAdjust="spacing" x="4" y="15.8">应用程序详细设计</tspan>
        </text>
    </g>
    <g id="219" transform="translate(625,1389.4)" ed:width="92" ed:parentid="106" ed:height="22.5">
        <path id="220" stroke-linejoin="round" transform="translate(-14.5,48.08)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M-14.5,25.6L2.6,25.6L2.6,-19.6C2.6,-22.9,5.3,-25.6,8.6,-25.6L14.5,-25.6"/>
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">建立数据库结构</tspan>
        </text>
    </g>
    <g id="221" transform="translate(625,1420.6)" ed:width="56" ed:parentid="106" ed:height="22.5">
        <path id="222" stroke-linejoin="round" transform="translate(-14.5,32.48)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M-14.5,10L2.6,10L2.6,-4C2.6,-7.3,5.3,-10,8.6,-10L14.5,-10"/>
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">数据加载</tspan>
        </text>
    </g>
    <g id="223" transform="translate(625,1451.8)" ed:width="164" ed:parentid="106" ed:height="22.5">
        <path id="224" stroke-linejoin="round" transform="translate(-14.5,16.88)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M-14.5,-5.6L2.6,-5.6L2.6,-0.4C2.6,2.9,5.3,5.6,8.6,5.6L14.5,5.6"/>
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,22.5L164,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="156" lengthAdjust="spacing" x="4" y="15.8">事务和应用程序的编码及测试</tspan>
        </text>
    </g>
    <g id="225" transform="translate(625,1483)" ed:width="140" ed:parentid="106" ed:height="22.5">
        <path id="226" stroke-linejoin="round" transform="translate(-14.5,1.27)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M-14.5,-21.2L2.6,-21.2L2.6,15.2C2.6,18.5,5.3,21.2,8.6,21.2L14.5,21.2"/>
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,22.5L140,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="132" lengthAdjust="spacing" x="4" y="15.8">系统集成、测试与试运行</tspan>
        </text>
    </g>
    <g id="227" transform="translate(625,1514.2)" ed:width="56" ed:parentid="106" ed:height="22.5">
        <path id="228" stroke-linejoin="round" transform="translate(-14.5,-14.33)" stroke="#70bdf2" stroke-linecap="round" fill="none" d="M-14.5,-36.8L2.6,-36.8L2.6,30.8C2.6,34.1,5.3,36.8,8.6,36.8L14.5,36.8"/>
        <path stroke-linejoin="round" stroke="#70bdf2" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">系统部署</tspan>
        </text>
    </g>
    <g id="271" transform="translate(625,1644.1)" ed:width="56" ed:parentid="110" ed:height="22.5">
        <path id="272" stroke-linejoin="round" transform="translate(-14.5,118.27)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,95.8L2.6,95.8L2.6,-89.8C2.6,-93.1,5.3,-95.8,8.6,-95.8L14.5,-95.8"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">日常维护</tspan>
        </text>
    </g>
    <g id="273" transform="translate(710,1581.7)" ed:width="68" ed:parentid="271" ed:height="22.5">
        <path id="274" stroke-linejoin="round" transform="translate(-14.5,53.7)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,31.2L2.6,31.2L2.6,-25.2C2.6,-28.5,5.3,-31.2,8.6,-31.2L14.5,-31.2"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">备份与恢复</tspan>
        </text>
    </g>
    <g id="275" transform="translate(710,1612.9)" ed:width="68" ed:parentid="271" ed:height="22.5">
        <path id="276" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">完整性维护</tspan>
        </text>
    </g>
    <g id="277" transform="translate(710,1644.1)" ed:width="68" ed:parentid="271" ed:height="22.5">
        <path id="278" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">安全性维护</tspan>
        </text>
    </g>
    <g id="279" transform="translate(710,1675.3)" ed:width="80" ed:parentid="271" ed:height="22.5">
        <path id="280" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">存储空间管理</tspan>
        </text>
    </g>
    <g id="281" transform="translate(710,1706.5)" ed:width="56" ed:parentid="271" ed:height="22.5">
        <path id="282" stroke-linejoin="round" transform="translate(-14.5,-8.7)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-31.2L2.6,-31.2L2.6,25.2C2.6,28.5,5.3,31.2,8.6,31.2L14.5,31.2"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">并发控制</tspan>
        </text>
    </g>
    <g id="283" transform="translate(625,1768.9)" ed:width="68" ed:parentid="110" ed:height="22.5">
        <path id="284" stroke-linejoin="round" transform="translate(-14.5,55.88)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,33.4L2.6,33.4L2.6,-27.4C2.6,-30.7,5.3,-33.4,8.6,-33.4L14.5,-33.4"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">监控与分析</tspan>
        </text>
    </g>
    <g id="285" transform="translate(722,1737.7)" ed:width="92" ed:parentid="283" ed:height="22.5">
        <path id="286" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">数据采集与统计</tspan>
        </text>
    </g>
    <g id="287" transform="translate(722,1768.9)" ed:width="56" ed:parentid="283" ed:height="22.5">
        <path id="288" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">操作分析</tspan>
        </text>
    </g>
    <g id="289" transform="translate(722,1800.1)" ed:width="80" ed:parentid="283" ed:height="22.5">
        <path id="290" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">基准程序评估</tspan>
        </text>
    </g>
    <g id="291" transform="translate(625,1924.9)" ed:width="80" ed:parentid="110" ed:height="22.5">
        <path id="292" stroke-linejoin="round" transform="translate(-14.5,-22.13)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-44.6L2.6,-44.6L2.6,38.6C2.6,41.9,5.3,44.6,8.6,44.6L14.5,44.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">性能优化调整</tspan>
        </text>
    </g>
    <g id="293" transform="translate(625,2080.9)" ed:width="56" ed:parentid="110" ed:height="22.5">
        <path id="294" stroke-linejoin="round" transform="translate(-14.5,-100.13)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-122.6L2.6,-122.6L2.6,116.6C2.6,119.9,5.3,122.6,8.6,122.6L14.5,122.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">系统进化</tspan>
        </text>
    </g>
    <g id="295" transform="translate(710,2049.7)" ed:width="80" ed:parentid="293" ed:height="22.5">
        <path id="296" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">应用程序升级</tspan>
        </text>
    </g>
    <g id="297" transform="translate(710,2080.9)" ed:width="68" ed:parentid="293" ed:height="22.5">
        <path id="298" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,0,8.6,0L14.5,0"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L68,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="60" lengthAdjust="spacing" x="4" y="15.8">数据库重组</tspan>
        </text>
    </g>
    <g id="299" transform="translate(710,2112.1)" ed:width="97" ed:parentid="293" ed:height="22.5">
        <path id="300" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L97,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="89" lengthAdjust="spacing" x="4" y="15.8">DBMS和OS升级</tspan>
        </text>
    </g>
    <g id="301" transform="translate(734,1831.3)" ed:width="92" ed:parentid="291" ed:height="22.5">
        <path id="302" stroke-linejoin="round" transform="translate(-14.5,69.3)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,46.8L2.6,46.8L2.6,-40.8C2.6,-44.1,5.3,-46.8,8.6,-46.8L14.5,-46.8"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">查询调整与优化</tspan>
        </text>
    </g>
    <g id="303" transform="translate(734,1862.5)" ed:width="56" ed:parentid="291" ed:height="22.5">
        <path id="304" stroke-linejoin="round" transform="translate(-14.5,53.7)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,31.2L2.6,31.2L2.6,-25.2C2.6,-28.5,5.3,-31.2,8.6,-31.2L14.5,-31.2"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">索引调整</tspan>
        </text>
    </g>
    <g id="305" transform="translate(734,1893.7)" ed:width="56" ed:parentid="291" ed:height="22.5">
        <path id="306" stroke-linejoin="round" transform="translate(-14.5,38.1)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,15.6L2.6,15.6L2.6,-9.6C2.6,-12.9,5.3,-15.6,8.6,-15.6L14.5,-15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">事务调整</tspan>
        </text>
    </g>
    <g id="307" transform="translate(734,1924.9)" ed:width="56" ed:parentid="291" ed:height="22.5">
        <path id="308" stroke-linejoin="round" transform="translate(-14.5,22.5)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,0L2.6,0C2.6,0,5.3,-0,8.6,-0L14.5,-0"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">模式调整</tspan>
        </text>
    </g>
    <g id="309" transform="translate(734,1956.1)" ed:width="56" ed:parentid="291" ed:height="22.5">
        <path id="310" stroke-linejoin="round" transform="translate(-14.5,6.9)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-15.6L2.6,-15.6L2.6,9.6C2.6,12.9,5.3,15.6,8.6,15.6L14.5,15.6"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L56,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="48" lengthAdjust="spacing" x="4" y="15.8">参数调整</tspan>
        </text>
    </g>
    <g id="311" transform="translate(734,1987.3)" ed:width="92" ed:parentid="291" ed:height="22.5">
        <path id="312" stroke-linejoin="round" transform="translate(-14.5,-8.7)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-31.2L2.6,-31.2L2.6,25.2C2.6,28.5,5.3,31.2,8.6,31.2L14.5,31.2"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L92,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="84" lengthAdjust="spacing" x="4" y="15.8">硬件调整和升级</tspan>
        </text>
    </g>
    <g id="313" transform="translate(734,2018.5)" ed:width="80" ed:parentid="291" ed:height="22.5">
        <path id="314" stroke-linejoin="round" transform="translate(-14.5,-24.3)" stroke="#e0a7d3" stroke-linecap="round" fill="none" d="M-14.5,-46.8L2.6,-46.8L2.6,40.8C2.6,44.1,5.3,46.8,8.6,46.8L14.5,46.8"/>
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M0,22.5L80,22.5"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="72" lengthAdjust="spacing" x="4" y="15.8">应用程序优化</tspan>
        </text>
    </g>
    <g id="318" transform="translate(850,1842.65)" ed:width="196.375" ed:parentid="317" ed:layout="rightmap" ed:height="31">
        <path stroke-linejoin="round" stroke="#e0a7d3" fill="none" d="M15.5,0L180.9,0C189.4,0,196.4,6.9,196.4,15.5C196.4,24.1,189.4,31,180.9,31L15.5,31C6.9,31,0,24.1,0,15.5C0,6.9,6.9,0,15.5,0z"/>
        <text class="st4">
            <tspan style="white-space:pre" textLength="156" lengthAdjust="spacing" x="21" y="19.5">看看就好，记住前面四个就行</tspan>
        </text>
    </g>
    <g id="101" transform="translate(153,1110.3)" ed:width="262" ed:topictype="mainidea" ed:layout="rightmap" ed:height="65">
        <path stroke-width="3" stroke-linejoin="round" stroke="#50bec1" fill="none" d="M0,0L262,0L262,65L0,65L0,0z"/>
        <text class="st5">
            <tspan style="white-space:pre" textLength="209" lengthAdjust="spacing" x="27" y="39.5">数据库应用系统生命周期</tspan>
        </text>
    </g>
    <g ed:togtopicid="164" transform="translate(1059.35,698.05)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="101" transform="translate(416,1136.8)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="102" transform="translate(687,343.45)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="104" transform="translate(582,819.7)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="106" transform="translate(597,1457.05)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="108" transform="translate(582,1217.95)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="110" transform="translate(597,1852.15)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="112" transform="translate(667,1124.35)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="114" transform="translate(667,1202.35)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="116" transform="translate(667,1295.95)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="118" transform="translate(808,203.05)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="120" transform="translate(784,327.85)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="122" transform="translate(772,468.25)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="155" transform="translate(835,807.25)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="165" transform="translate(1144.35,698.05)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="179" transform="translate(847,900.85)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="181" transform="translate(691,1010.05)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="271" transform="translate(682,1649.35)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="283" transform="translate(694,1774.15)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="291" transform="translate(706,1930.15)">
        <use xlink:href="#minus"/>
    </g>
    <g ed:togtopicid="293" transform="translate(682,2086.15)">
        <use xlink:href="#minus"/>
    </g>
    <symbol id="plus">
        <path fill="url(#lg1)" d="M11,6C11,8.8,8.8,11,6,11C3.2,11,1,8.8,1,6C1,3.2,3.2,1,6,1C8.8,1,11,3.2,11,6z"/>
        <path stroke="#46a000" fill="none" d="M11,6C11,8.8,8.8,11,6,11C3.2,11,1,8.8,1,6C1,3.2,3.2,1,6,1C8.8,1,11,3.2,11,6zM3,6L9,6M6,3L6,9"/>
    </symbol>
    <symbol id="minus">
        <path fill="url(#lg1)" d="M11,6C11,8.8,8.8,11,6,11C3.2,11,1,8.8,1,6C1,3.2,3.2,1,6,1C8.8,1,11,3.2,11,6z"/>
        <path stroke="#46a000" fill="none" d="M11,6C11,8.8,8.8,11,6,11C3.2,11,1,8.8,1,6C1,3.2,3.2,1,6,1C8.8,1,11,3.2,11,6zM3,6L9,6"/>
    </symbol>
    <symbol id="note">
        <image xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAyZpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+IDx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IkFkb2JlIFhNUCBDb3JlIDUuNi1jMTM4IDc5LjE1OTgyNCwgMjAxNi8wOS8xNC0wMTowOTowMSAgICAgICAgIj4gPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4gPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIgeG1sbnM6eG1wTU09Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9tbS8iIHhtbG5zOnN0UmVmPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvc1R5cGUvUmVzb3VyY2VSZWYjIiB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iIHhtcE1NOkRvY3VtZW50SUQ9InhtcC5kaWQ6NDMwRENEQjU5Nzg1MTFFNzlBQ0FCMEY4Rjc5N0Q0MkIiIHhtcE1NOkluc3RhbmNlSUQ9InhtcC5paWQ6NDMwRENEQjQ5Nzg1MTFFNzlBQ0FCMEY4Rjc5N0Q0MkIiIHhtcDpDcmVhdG9yVG9vbD0iQWRvYmUgUGhvdG9zaG9wIENDIDIwMTcgKFdpbmRvd3MpIj4gPHhtcE1NOkRlcml2ZWRGcm9tIHN0UmVmOmluc3RhbmNlSUQ9InhtcC5paWQ6NkFDNEE4NzgyNENGMTFFN0FEOTA5MzNFOUY4NzE5OTAiIHN0UmVmOmRvY3VtZW50SUQ9InhtcC5kaWQ6NkFDNEE4NzkyNENGMTFFN0FEOTA5MzNFOUY4NzE5OTAiLz4gPC9yZGY6RGVzY3JpcHRpb24+IDwvcmRmOlJERj4gPC94OnhtcG1ldGE+IDw/eHBhY2tldCBlbmQ9InIiPz6IjguxAAADcUlEQVR42uSXS0gUcRzHv7OzD3dzW7VaNfKRpYZFpJkYRRFI0KEOBUGHDlKEEfSwJOh16QHVMehQHTrUoQdF0CWNQHpopm1pFgX5wM18uz5WZ3dmdvrqJBlFrjWrgf/Tf/87zOf3/c3v9Rc0TcN0LhOmeZnHNidOX4m4K86c3CP8vx4YZ6WhgOGWVpy9/vCns/qSo1h68XzkPaB0fYFS8wpHlqQhO6Siofjc6PkYPKIGaIqC4DsvNMGJQKsXeZIfEHHsw75T8BSWRN4AwWyGsCgJ/rf1kLxtkGUZqqyehYYTf4yBsVXpef9X4PREC+KU55DjNsOeNB/K1o3ouHwTKg1S6RVVUU/TiCAfvWC4B9zRAdi6H0BAAJb2GwgOeuFclom6rEzIfQNQZAVSINihiv77E3ogPztrcvRQD/D1LmCPYQAIEHqfwdpTjmDmJVT3+qHmrkDG05deu314rc+kNRsbA8EOoOUWjRBG4egs5T4AWOJgpSfW5rjh8fmR4avJietsbV5z9drEMRD2ChDeRuWCZST0CH9EuATY4oHZK4CeZ9jgrketYzVspc87Ew2thNJXwu/wLdYfcJXKrW7ASXjvC2jM/7KPaegfEsOrhOFmwfJUGxwDBJpsdDvbSFcZlTO4bXN15b4K1gI/JMd6VDbOMrYbxph7ILTdY2GJIjxEeKkOt8whPJvKK3guI7SgCPasQ5PrBRNmgdJOt5dzQ5gi68o1hfBYwJVD5VU0ZghYfByiK3fyzejP39xL+IjyaEKpuPuxDjfH6PC+ahrVDyws5u/csF4ZvgFSC+GsH2bCVcK7RuAqlc8mbCXQ7wFk1oLU/XTOOoMnouExuFOP8lG3Ey4yuFyrCH+jp2PyXmBuwb/NA7/LgtzYBj7INFLZ0bqejPQ6wh1AbP53ONMxuYi1eJPxM2GKO5pZ5kJIi4HW7Rllw8Toj10NDNTqcZG0C4jfYsxE9EsWDHUg9MUPbVhglc2HyeKB4MokvI7/NVH5biBhWwSnYl8DtMFW/dubHNBmMbr7qXzoM5UXAonbIzeWS4EAql7XQxT5GEsqFInGiAiZ8xjtB4D5O4wfSsevpsZG3C7/hOSdBUiYZ4XmTGGNT+C0ExW5qXj8EkURh4sPwh2fQF8JEKZiLP9pvEpPn/p7AW9IM+tuKMz42/E3AQYASdRSZfYtoZ0AAAAASUVORK5CYII=" height="16" width="16" x="0" y="0"/>
    </symbol>
</svg>
</div>
        <div id="copyright">Created With  <a href="https://www.edrawsoft.com/" target="_blank" title="edrawsoft">MindMaster</a></div>
      </div>
    </div>
    <script>eval(atob('dmFyIG11YT13aW5kb3cubmF2aWdhdG9yLnVzZXJBZ2VudDsNCnZhciB1YT0obXVhLmluZGV4T2YoJ3J2OjExJykrbXVhLmluZGV4T2YoJ01TSUUnKSk+PTA7DQpOdW1iZXIucHJvdG90eXBlLnRvc3VpdHN2Zz1mdW5jdGlvbiAoKSB7DQogICAgdmFyIG51bT10aGlzLnZhbHVlT2YoKTsNCiAgICBpZihudW0lMT09PTApew0KICAgICAgICByZXR1cm4gbnVtKzAuNQ0KICAgIH1lbHNlIHJldHVybiBudW07DQp9Ow0KTnVtYmVyLnByb3RvdHlwZS5wbHVzej1mdW5jdGlvbigpIHsNCiAgICB2YXIgbnVtPXRoaXMudmFsdWVPZigpOw0KICAgIHJldHVybiBudW08MTA/JzAnK251bTpudW07DQp9Ow0KZnVuY3Rpb24gcGFyc2VEYXRlKG51bSkgew0KICAgIHZhciBkYXRlID0gbmV3IERhdGUobnVtKTsNCiAgICB2YXIgWSA9IGRhdGUuZ2V0RnVsbFllYXIoKSArICctJzsNCiAgICB2YXIgTSA9IChkYXRlLmdldE1vbnRoKCkrMSkucGx1c3ooKSArICctJzsNCiAgICB2YXIgRCA9IGRhdGUuZ2V0RGF0ZSgpLnBsdXN6KCkgKyAnICc7DQogICAgdmFyIGggPSBkYXRlLmdldEhvdXJzKCkucGx1c3ooKSArICc6JzsNCiAgICB2YXIgbW0gPSBkYXRlLmdldE1pbnV0ZXMoKS5wbHVzeigpICsgJzonOw0KICAgIHZhciBzID0gZGF0ZS5nZXRTZWNvbmRzKCkucGx1c3ooKTsNCiAgICByZXR1cm4gWStNK0QraCttbStzOw0KfQ0KLy8tLXByZWRlZmluZWQNCi8vY29tbWVudC0tDQp2YXIgY29tbWVudHM9ZG9jdW1lbnQucXVlcnlTZWxlY3RvckFsbCgnZz5nW2VkXFw6Y29tbWVudF0nKTsNCmZ1bmN0aW9uIGdldGN3aChwb3B1cCkgew0KICAgIGRvY3VtZW50LmJvZHkuZ2V0RWxlbWVudHNCeVRhZ05hbWUoJ3N2ZycpWzBdLmFwcGVuZENoaWxkKHBvcHVwKTsNCiAgICB2YXIgdz1wb3B1cC5nZXRCb3VuZGluZ0NsaWVudFJlY3QoKS53aWR0aDsNCiAgICB2YXIgaD1wb3B1cC5nZXRCb3VuZGluZ0NsaWVudFJlY3QoKS5oZWlnaHQ7DQogICAgcmV0dXJuIFt3LGhdDQp9DQpmb3IodmFyIGk9MDtpPGNvbW1lbnRzLmxlbmd0aDtpKyspew0KICAgIHZhciBwb3B1cD1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywnZycpOw0KICAgIHZhciBob3Zlcj1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywncmVjdCcpOw0KICAgIHZhciBvbGluZT1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywncmVjdCcpOw0KICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgnZmlsbCcsJyNjZGNkZmYnKTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ3gnLCcwJyk7DQogICAgaG92ZXIuc2V0QXR0cmlidXRlKCd5JywnMCcpOw0KICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgnaGVpZ2h0JywnMTYnKTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ3dpZHRoJywnMTYnKTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ2ZpbGwtb3BhY2l0eScsJzAuNicpOw0KICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgndHJhbnNmb3JtJyxjb21tZW50c1tpXS5xdWVyeVNlbGVjdG9yKCd1c2UnKS5nZXRBdHRyaWJ1dGUoJ3RyYW5zZm9ybScpKTsNCiAgICBob3Zlci5zdHlsZS5kaXNwbGF5PSdub25lJzsNCiAgICBjb21tZW50c1tpXS5hcHBlbmRDaGlsZChob3Zlcik7DQogICAgdmFyIGE9SlNPTi5wYXJzZShjb21tZW50c1tpXS5nZXRBdHRyaWJ1dGUoJ2VkOmNvbW1lbnQnKSk7DQogICAgdmFyIGhlaWdodD0wOw0KICAgIHZhciBjYXJyPVtdOw0KICAgIGZvcih2YXIgaj0wO2o8YS5sZW5ndGg7aisrKXsNCiAgICAgICAgdmFyIHN0YW1wPU51bWJlcihhW2pdLkRhdGUpKjEwMDA7DQogICAgICAgIHZhciB0aW1lPXBhcnNlRGF0ZShzdGFtcCk7DQogICAgICAgIHZhciBuYW1lPWFbal0uTmFtZTsNCiAgICAgICAgdmFyIG1lc3NhZ2U9YVtqXS5NZXNzYWdlOw0KICAgICAgICB2YXIgbWVzc2FnZUFycj1tZXNzYWdlLnNwbGl0KC9cbi8pOw0KICAgICAgICB2YXIgbz1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywnZycpOw0KICAgICAgICB2YXIgbj1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICB2YXIgdD1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICB2YXIgbT1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICBuLnNldEF0dHJpYnV0ZSgneCcsNSk7DQogICAgICAgIG4uc2V0QXR0cmlidXRlKCd5JywxMik7DQogICAgICAgIG4uc2V0QXR0cmlidXRlKCdmaWxsJywnIzAwNmVmZicpOw0KICAgICAgICBuLnRleHRDb250ZW50PW5hbWUrJ++8mic7DQogICAgICAgIG4uc2V0QXR0cmlidXRlKCdmb250LXNpemUnLCcxMicpOw0KICAgICAgICB0LnNldEF0dHJpYnV0ZSgneCcsMjAwKTsNCiAgICAgICAgdC5zZXRBdHRyaWJ1dGUoJ3knLDEyKTsNCiAgICAgICAgdC5zZXRBdHRyaWJ1dGUoJ2ZpbGwnLCcjOTY5Njk2Jyk7DQogICAgICAgIHQudGV4dENvbnRlbnQ9dGltZTsNCiAgICAgICAgdC5zZXRBdHRyaWJ1dGUoJ2ZvbnQtc2l6ZScsJzEwJyk7DQogICAgICAgIG0uc2V0QXR0cmlidXRlKCd0cmFuc2Zvcm0nLCd0cmFuc2xhdGUoMjAsMjcpJyk7DQogICAgICAgIG0uc2V0QXR0cmlidXRlKCdmb250LXNpemUnLCcxMicpOw0KICAgICAgICBmb3IodmFyIGs9MDtrPG1lc3NhZ2VBcnIubGVuZ3RoO2srKyl7DQogICAgICAgICAgICB2YXIgdHM9ZG9jdW1lbnQuY3JlYXRlRWxlbWVudE5TKCdodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZycsJ3RzcGFuJyk7DQogICAgICAgICAgICB0cy5zZXRBdHRyaWJ1dGUoJ3gnLCcwJyk7DQogICAgICAgICAgICB0cy5zZXRBdHRyaWJ1dGUoJ3knLGsqMTYpOw0KICAgICAgICAgICAgdHMudGV4dENvbnRlbnQ9bWVzc2FnZUFycltrXTsNCiAgICAgICAgICAgIG0uYXBwZW5kQ2hpbGQodHMpOw0KICAgICAgICB9DQogICAgICAgIG8uc2V0QXR0cmlidXRlKCd0cmFuc2Zvcm0nLCd0cmFuc2xhdGUoMCwnK2hlaWdodCsnKScpOw0KICAgICAgICBvLmFwcGVuZENoaWxkKG4pOw0KICAgICAgICBvLmFwcGVuZENoaWxkKHQpOw0KICAgICAgICBvLmFwcGVuZENoaWxkKG0pOw0KICAgICAgICBjYXJyLnB1c2gobyk7DQogICAgICAgIHBvcHVwLmFwcGVuZENoaWxkKG8pOw0KICAgICAgICBoZWlnaHQ9KG1lc3NhZ2VBcnIubGVuZ3RoKzEpKjE2K2hlaWdodDsNCiAgICB9DQogICAgdmFyIHdhcnI9Z2V0Y3doKHBvcHVwKTsNCiAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ3gnLCcwJyk7DQogICAgb2xpbmUuc2V0QXR0cmlidXRlKCd5JywnMCcpOw0KICAgIHZhciBvdz13YXJyWzBdKzEwLjU7DQogICAgdmFyIG9oPXdhcnJbMV0rMzsNCiAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ3dpZHRoJyxvdyk7DQogICAgb2xpbmUuc2V0QXR0cmlidXRlKCdoZWlnaHQnLG9oKTsNCiAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ2ZpbGwnLCd3aGl0ZScpOw0KICAgIG9saW5lLnNldEF0dHJpYnV0ZSgnc3Ryb2tlJywnIzY1NjU2NScpOw0KICAgIHBvcHVwLmFwcGVuZENoaWxkKG9saW5lKTsNCiAgICB2YXIgbD1jYXJyLmxlbmd0aDsNCiAgICB3aGlsZShsLS0pew0KICAgICAgICBwb3B1cC5hcHBlbmRDaGlsZChjYXJyW2xdKTsNCiAgICB9DQogICAgcG9wdXAub25tb3VzZW92ZXI9ZnVuY3Rpb24gKCkgew0KICAgICAgICB0aGlzLnN0eWxlLmRpc3BsYXk9J2Jsb2NrJzsNCiAgICB9Ow0KICAgIHBvcHVwLm9ubW91c2VvdXQ9ZnVuY3Rpb24gKCkgew0KICAgICAgICB0aGlzLnN0eWxlLmRpc3BsYXkgPSAnbm9uZSc7DQogICAgfTsNCiAgICB2YXIgY3M9Y29tbWVudHNbaV0ucXVlcnlTZWxlY3RvcigndXNlJykuZ2V0QXR0cmlidXRlKCd0cmFuc2Zvcm0nKS5tYXRjaCgvXCgoXFMqfFxTKlxzXFMqKVwpLylbMV0uc3BsaXQoLyB8LC8pOw0KICAgIHZhciBwcz1jb21tZW50c1tpXS5wYXJlbnROb2RlLmdldEF0dHJpYnV0ZSgndHJhbnNmb3JtJykubWF0Y2goL1woKFxTKnxcUypcc1xTKilcKS8pWzFdLnNwbGl0KC8gfCwvKTsNCiAgICB2YXIgeD1wYXJzZUZsb2F0KGNzWzBdKStwYXJzZUZsb2F0KHBzWzBdKTsNCiAgICB2YXIgeT1wYXJzZUZsb2F0KHBzWzFdKTsNCiAgICB4PXgudG9zdWl0c3ZnKCk7DQogICAgeT15LnRvc3VpdHN2ZygpOw0KICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgndHJhbnNmb3JtJywndHJhbnNsYXRlKCcreCsnLCcreSsnKScpOw0KICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgnY29tbWVudCcsJycpOw0KICAgIHBvcHVwLnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgnZWQ6Y29tbWVudGlkJyxjb21tZW50c1tpXS5wYXJlbnROb2RlLmlkKTsNCiAgICBkb2N1bWVudC5xdWVyeVNlbGVjdG9yKCcjc3ZnLWNvbnRhaW5lciA+IHN2ZycpLmFwcGVuZENoaWxkKHBvcHVwKTsNCiAgICBjb21tZW50c1tpXS5vbm1vdXNlb3Zlcj1mdW5jdGlvbiAoKSB7DQogICAgICAgIHZhciBjb21tZW50aWQ9dGhpcy5wYXJlbnROb2RlLmlkOw0KICAgICAgICB0aGlzLnF1ZXJ5U2VsZWN0b3IoJ3JlY3QnKS5zdHlsZS5kaXNwbGF5PSdibG9jayc7DQogICAgICAgIGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3IoImdbZWRcXDpjb21tZW50aWQ9JyIrY29tbWVudGlkKyInXVtjb21tZW50XSIpLnN0eWxlLmRpc3BsYXk9J2Jsb2NrJzsNCiAgICB9Ow0KICAgIGNvbW1lbnRzW2ldLm9ubW91c2VvdXQ9ZnVuY3Rpb24gKCkgew0KICAgICAgICB2YXIgY29tbWVudGlkPXRoaXMucGFyZW50Tm9kZS5pZDsNCi8vICAgICAgICB3aW5kb3cuZ2V0U2VsZWN0aW9uKCkucmVtb3ZlQWxsUmFuZ2VzKCk7DQogICAgICAgIHRoaXMucXVlcnlTZWxlY3RvcigncmVjdCcpLnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgICAgICBkb2N1bWVudC5xdWVyeVNlbGVjdG9yKCJnW2VkXFw6Y29tbWVudGlkPSciK2NvbW1lbnRpZCsiJ11bY29tbWVudF0iKS5zdHlsZS5kaXNwbGF5PSdub25lJzsNCiAgICB9DQp9DQovLy0tY29tbWVudA0KLy9ub3RlLS0NCmlmKCF1YSl7DQogICAgdmFyIG5vdGVzPWRvY3VtZW50LnF1ZXJ5U2VsZWN0b3JBbGwoJ2c+Z1tlZFxcOm5vdGVdJyk7DQogICAgZnVuY3Rpb24gZ2V0d2gocyxwKSB7DQogICAgICAgIHZhciBtYWlucD1kb2N1bWVudC5jcmVhdGVFbGVtZW50KCdkaXYnKTsNCiAgICAgICAgbWFpbnAuc3R5bGUuY3NzVGV4dD1zOw0KICAgICAgICBtYWlucC5zdHlsZS5kaXNwbGF5PSdpbmxpbmUtYmxvY2snOw0KICAgICAgICBtYWlucC5pbm5lckhUTUw9cDsNCiAgICAgICAgZG9jdW1lbnQuYm9keS5hcHBlbmRDaGlsZChtYWlucCk7DQogICAgICAgIHZhciB3PW1haW5wLmNsaWVudFdpZHRoOw0KICAgICAgICB2YXIgaD1tYWlucC5jbGllbnRIZWlnaHQ7DQogICAgICAgIGRvY3VtZW50LmJvZHkucmVtb3ZlQ2hpbGQobWFpbnApOw0KICAgICAgICByZXR1cm4gW3csaF0NCiAgICB9DQogICAgZm9yKHZhciBpPTA7aTxub3Rlcy5sZW5ndGg7aSsrKXsNCiAgICAgICAgdmFyIGE9bm90ZXNbaV0uZ2V0QXR0cmlidXRlKCdlZDpub3RlJyk7DQogICAgICAgIHZhciBtYWlucD1hLm1hdGNoKC88cChbXFNcc10qKTxcL3A+L2cpWzBdOw0KICAgICAgICB2YXIgbWFpbnM9YS5tYXRjaCgvc3R5bGU9IiguKj8pIi8pWzFdOw0KICAgICAgICB2YXIgb3V0PWRvY3VtZW50LmNyZWF0ZUVsZW1lbnROUygnaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnLCdnJyk7DQogICAgICAgIHZhciBvbGluZT1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywncmVjdCcpOw0KICAgICAgICB2YXIgcG9wdXA9ZG9jdW1lbnQuY3JlYXRlRWxlbWVudE5TKCdodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZycsJ2ZvcmVpZ25PYmplY3QnKTsNCiAgICAgICAgdmFyIGhvdmVyPWRvY3VtZW50LmNyZWF0ZUVsZW1lbnROUygnaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnLCdyZWN0Jyk7DQogICAgICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgnZmlsbCcsJyNjZGNkZmYnKTsNCiAgICAgICAgaG92ZXIuc2V0QXR0cmlidXRlKCd4JywnMCcpOw0KICAgICAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ3knLCcwJyk7DQogICAgICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgnaGVpZ2h0JywnMTYnKTsNCiAgICAgICAgaG92ZXIuc2V0QXR0cmlidXRlKCd3aWR0aCcsJzE2Jyk7DQogICAgICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgnZmlsbC1vcGFjaXR5JywnMC42Jyk7DQogICAgICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgndHJhbnNmb3JtJyxub3Rlc1tpXS5xdWVyeVNlbGVjdG9yKCd1c2UnKS5nZXRBdHRyaWJ1dGUoJ3RyYW5zZm9ybScpKTsNCiAgICAgICAgaG92ZXIuc3R5bGUuZGlzcGxheT0nbm9uZSc7DQogICAgICAgIG5vdGVzW2ldLmFwcGVuZENoaWxkKGhvdmVyKTsNCiAgICAgICAgcG9wdXAuc3R5bGUuY3NzVGV4dD1tYWluczsNCiAgICAgICAgcG9wdXAuaW5uZXJIVE1MPW1haW5wOw0KICAgICAgICB2YXIgd2g9Z2V0d2gobWFpbnMsbWFpbnApOw0KICAgICAgICBwb3B1cC5zZXRBdHRyaWJ1dGUoJ3dpZHRoJyx3aFswXSsxNik7DQogICAgICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgnaGVpZ2h0Jyx3aFsxXSs4KTsNCiAgICAgICAgcG9wdXAuc2V0QXR0cmlidXRlKCd0cmFuc2Zvcm0nLCd0cmFuc2xhdGUoOCw0KScpOw0KICAgICAgICBwb3B1cC5zdHlsZS50ZXh0QWxpZ249J2xlZnQnOw0KICAgICAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ3gnLCcwJyk7DQogICAgICAgIG9saW5lLnNldEF0dHJpYnV0ZSgneScsJzAnKTsNCiAgICAgICAgb2xpbmUuc2V0QXR0cmlidXRlKCd3aWR0aCcsd2hbMF0rMTYpOw0KICAgICAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ2hlaWdodCcsd2hbMV0rOCk7DQogICAgICAgIG9saW5lLnNldEF0dHJpYnV0ZSgnc3Ryb2tlJywnI2EyN2EwMCcpOw0KICAgICAgICBvbGluZS5zZXRBdHRyaWJ1dGUoJ2ZpbGwnLCcjZmZlNzlkJyk7DQogICAgICAgIG91dC5hcHBlbmRDaGlsZChvbGluZSk7DQogICAgICAgIG91dC5hcHBlbmRDaGlsZChwb3B1cCk7DQogICAgICAgIG91dC5zZXRBdHRyaWJ1dGUoJ25vdGUnLCcnKTsNCiAgICAgICAgb3V0LnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgICAgICBvdXQuc2V0QXR0cmlidXRlKCdlZDpub3RlaWQnLG5vdGVzW2ldLnBhcmVudE5vZGUuaWQpOw0KICAgICAgICBvdXQub25tb3VzZW92ZXI9ZnVuY3Rpb24gKCkgew0KICAgICAgICAgICAgdGhpcy5zdHlsZS5kaXNwbGF5PSdibG9jayc7DQogICAgICAgIH07DQogICAgICAgIG91dC5vbm1vdXNlb3V0PWZ1bmN0aW9uICgpIHsNCi8vICAgICAgICB3aW5kb3cuZ2V0U2VsZWN0aW9uID8gd2luZG93LmdldFNlbGVjdGlvbigpLnJlbW92ZVJhbmdlKHdpbmRvdy5nZXRTZWxlY3Rpb24oKS5yZSk6ZG9jdW1lbnQuc2VsZWN0aW9uLmVtcHR5KCk7DQoNCiAgICAgICAgICAgIHRoaXMuc3R5bGUuZGlzcGxheT0nbm9uZSc7DQogICAgICAgIH07DQogICAgICAgIHZhciBjcz1ub3Rlc1tpXS5xdWVyeVNlbGVjdG9yKCd1c2UnKS5nZXRBdHRyaWJ1dGUoJ3RyYW5zZm9ybScpLm1hdGNoKC9cKChcUyp8XFMqXHNcUyopXCkvKVsxXS5zcGxpdCgvIHwsLyk7DQogICAgICAgIHZhciBwcz1ub3Rlc1tpXS5wYXJlbnROb2RlLmdldEF0dHJpYnV0ZSgndHJhbnNmb3JtJykubWF0Y2goL1woKFxTKnxcUypcc1xTKilcKS8pWzFdLnNwbGl0KC8gfCwvKTsNCiAgICAgICAgdmFyIHg9cGFyc2VGbG9hdChjc1swXSkrcGFyc2VGbG9hdChwc1swXSk7DQogICAgICAgIHZhciB5PXBhcnNlRmxvYXQocHNbMV0pOw0KICAgICAgICB4PXgudG9zdWl0c3ZnKCk7DQogICAgICAgIHk9eS50b3N1aXRzdmcoKTsNCiAgICAgICAgb3V0LnNldEF0dHJpYnV0ZSgndHJhbnNmb3JtJywndHJhbnNsYXRlKCcreCsnLCcreSsnKScpOw0KICAgICAgICBkb2N1bWVudC5xdWVyeVNlbGVjdG9yKCcjc3ZnLWNvbnRhaW5lciA+IHN2ZycpLmFwcGVuZENoaWxkKG91dCk7DQogICAgICAgIG5vdGVzW2ldLm9ubW91c2VvdmVyPWZ1bmN0aW9uICgpIHsNCiAgICAgICAgICAgIHZhciBub3RlaWQ9dGhpcy5wYXJlbnROb2RlLmlkOw0KICAgICAgICAgICAgdGhpcy5xdWVyeVNlbGVjdG9yKCdyZWN0Jykuc3R5bGUuZGlzcGxheT0nYmxvY2snOw0KICAgICAgICAgICAgZG9jdW1lbnQucXVlcnlTZWxlY3RvcigiZ1tlZFxcOm5vdGVpZD0nIitub3RlaWQrIiddW25vdGVdIikuc3R5bGUuZGlzcGxheT0nYmxvY2snOw0KICAgICAgICB9Ow0KICAgICAgICBub3Rlc1tpXS5vbm1vdXNlb3V0PWZ1bmN0aW9uICgpIHsNCiAgICAgICAgICAgIHZhciBub3RlaWQ9dGhpcy5wYXJlbnROb2RlLmlkOw0KLy8gICAgICAgIHdpbmRvdy5nZXRTZWxlY3Rpb24oKS5yZW1vdmVBbGxSYW5nZXMoKTsNCiAgICAgICAgICAgIHRoaXMucXVlcnlTZWxlY3RvcigncmVjdCcpLnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgICAgICAgICAgZG9jdW1lbnQucXVlcnlTZWxlY3RvcigiZ1tlZFxcOm5vdGVpZD0nIitub3RlaWQrIiddW25vdGVdIikuc3R5bGUuZGlzcGxheT0nbm9uZSc7DQogICAgICAgIH0NCiAgICB9DQp9ZWxzZXsNCiAgICBjb25zb2xlLmxvZygn5oqx5q2J77yMSUXmtY/op4jlmajkuI3mlK/mjIFub3Rl6Kej5p6Q77yM6K+35L2/55So5YW25LuW5YaF5qC45rWP6KeI5Zmo44CC6LCi6LCi77yBJykNCn0NCi8vLS1ub3RlDQovL2h5cGVybGluay0tDQp2YXIgbGlua3M9ZG9jdW1lbnQucXVlcnlTZWxlY3RvckFsbCgnZz5nW2VkXFw6aHlwZXJsaW5rXScpOw0KZnVuY3Rpb24gZ2V0bWF4bGVuKGFycixicnIpIHsNCiAgICB2YXIgbD0wOw0KICAgIHZhciBsbD0wOw0KICAgIGZvcih2YXIgaj0wO2o8YXJyLmxlbmd0aDtqKyspew0KICAgICAgICB2YXIgZT1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICBpZighaXNOYU4obGlua2FycltqXSkpew0KICAgICAgICAgICAgZS50ZXh0Q29udGVudD0nUGFnZS0nK2FycltqXTsNCiAgICAgICAgfWVsc2V7DQogICAgICAgICAgICBlLnRleHRDb250ZW50PWFycltqXTsNCiAgICAgICAgfQ0KICAgICAgICBlLnN0eWxlLmZvbnRTaXplPScxMnB4JzsNCiAgICAgICAgZG9jdW1lbnQuYm9keS5nZXRFbGVtZW50c0J5VGFnTmFtZSgnc3ZnJylbMF0uYXBwZW5kQ2hpbGQoZSk7DQogICAgICAgIHZhciBldz1lLmdldEJCb3goKS53aWR0aDsNCiAgICAgICAgZG9jdW1lbnQuYm9keS5nZXRFbGVtZW50c0J5VGFnTmFtZSgnc3ZnJylbMF0ucmVtb3ZlQ2hpbGQoZSk7DQogICAgICAgIHZhciBoPWRvY3VtZW50LmNyZWF0ZUVsZW1lbnROUygnaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmcnLCd0ZXh0Jyk7DQogICAgICAgIGgudGV4dENvbnRlbnQ9YnJyW2pdOw0KICAgICAgICBoLnN0eWxlLmZvbnRTaXplPScxMnB4JzsNCiAgICAgICAgaC5zdHlsZS5mb250V2VpZ2h0PSdib2xkJzsNCiAgICAgICAgZG9jdW1lbnQuYm9keS5nZXRFbGVtZW50c0J5VGFnTmFtZSgnc3ZnJylbMF0uYXBwZW5kQ2hpbGQoaCk7DQogICAgICAgIHZhciBodz1oLmdldEJCb3goKS53aWR0aDsNCiAgICAgICAgZG9jdW1lbnQuYm9keS5nZXRFbGVtZW50c0J5VGFnTmFtZSgnc3ZnJylbMF0ucmVtb3ZlQ2hpbGQoaCk7DQogICAgICAgIGw9ZXc+aHc/ZXc6aHc7DQogICAgICAgIGxsPWw+bGw/bDpsbDsNCiAgICB9DQogICAgcmV0dXJuIGxsOw0KfQ0KZm9yKHZhciBpPTA7aTxsaW5rcy5sZW5ndGg7aSsrKXsNCiAgICB2YXIgcG9wdXA9ZG9jdW1lbnQuY3JlYXRlRWxlbWVudE5TKCdodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZycsJ2cnKTsNCiAgICB2YXIgaG92ZXI9ZG9jdW1lbnQuY3JlYXRlRWxlbWVudE5TKCdodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZycsJ3JlY3QnKTsNCiAgICB2YXIgZGVzY2Fycj1bXTsNCiAgICB2YXIgbGlua2Fycj1bXTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ2ZpbGwnLCcjY2RjZGZmJyk7DQogICAgaG92ZXIuc2V0QXR0cmlidXRlKCd4JywnMCcpOw0KICAgIGhvdmVyLnNldEF0dHJpYnV0ZSgneScsJzAnKTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ2hlaWdodCcsJzE2Jyk7DQogICAgaG92ZXIuc2V0QXR0cmlidXRlKCd3aWR0aCcsJzE2Jyk7DQogICAgaG92ZXIuc2V0QXR0cmlidXRlKCdmaWxsLW9wYWNpdHknLCcwLjYnKTsNCiAgICBob3Zlci5zZXRBdHRyaWJ1dGUoJ3RyYW5zZm9ybScsbGlua3NbaV0ucXVlcnlTZWxlY3RvcigndXNlJykuZ2V0QXR0cmlidXRlKCd0cmFuc2Zvcm0nKSk7DQogICAgaG92ZXIuc3R5bGUuZGlzcGxheT0nbm9uZSc7DQogICAgbGlua3NbaV0uYXBwZW5kQ2hpbGQoaG92ZXIpOw0KICAgIC8vIGNvbnNvbGUubG9nKGxpbmtzW2ldLmdldEF0dHJpYnV0ZSgnZWQ6aHlwZXJsaW5rJykpOw0KICAgIHZhciBhPUpTT04ucGFyc2UobGlua3NbaV0uZ2V0QXR0cmlidXRlKCdlZDpoeXBlcmxpbmsnKSk7DQogICAgdmFyIGNzPWxpbmtzW2ldLnF1ZXJ5U2VsZWN0b3IoJ3VzZScpLmdldEF0dHJpYnV0ZSgndHJhbnNmb3JtJykubWF0Y2goL1woKFxTKnxcUypcc1xTKilcKS8pWzFdLnNwbGl0KC8gfCwvKTsNCiAgICB2YXIgcHM9bGlua3NbaV0ucGFyZW50Tm9kZS5nZXRBdHRyaWJ1dGUoJ3RyYW5zZm9ybScpLm1hdGNoKC9cKChcUyp8XFMqXHNcUyopXCkvKVsxXS5zcGxpdCgvIHwsLyk7DQogICAgdmFyIHg9cGFyc2VGbG9hdChjc1swXSkrcGFyc2VGbG9hdChwc1swXSk7DQogICAgdmFyIHk9cGFyc2VGbG9hdChwc1sxXSk7DQogICAgeD14LnRvc3VpdHN2ZygpOw0KICAgIHk9eS50b3N1aXRzdmcoKTsNCiAgICB2YXIgYWw9YS5sZW5ndGg7DQogICAgZm9yKHZhciBqPTA7ajxhbDtqKyspew0KICAgICAgICBsaW5rYXJyLnB1c2goYVtqXS5saW5rKTsNCiAgICAgICAgZGVzY2Fyci5wdXNoKGFbal0uZGVzYyk7DQogICAgfQ0KICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgndHJhbnNmb3JtJywndHJhbnNsYXRlKCcreCsnLCcreSsnKScpOw0KICAgIHZhciBtYXg9Z2V0bWF4bGVuKGxpbmthcnIsZGVzY2Fycik7DQogICAgZm9yKHZhciBrPTA7azxhbDtrKyspew0KICAgICAgICB2YXIgYz1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywnYScpOw0KICAgICAgICB2YXIgZD1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywncmVjdCcpOw0KICAgICAgICB2YXIgZT1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICB2YXIgZj1kb2N1bWVudC5jcmVhdGVFbGVtZW50TlMoJ2h0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnJywndGV4dCcpOw0KICAgICAgICBpZihpc05hTihsaW5rYXJyW2tdKSl7DQogICAgICAgICAgICBjLnNldEF0dHJpYnV0ZSgnaHJlZicsbGlua2FycltrXSk7DQogICAgICAgICAgICBjLnNldEF0dHJpYnV0ZSgndGFyZ2V0JywnX2JsYW5rJyk7DQogICAgICAgICAgICBlLnRleHRDb250ZW50PWxpbmthcnJba107DQogICAgICAgIH1lbHNlew0KICAgICAgICAgICAgZS50ZXh0Q29udGVudD0nUGFnZS0nK2xpbmthcnJba107DQogICAgICAgICAgICBjLnNldEF0dHJpYnV0ZSgnaHJlZicsJyMnK2xpbmthcnJba10pOw0KICAgICAgICB9DQogICAgICAgIGQuc2V0QXR0cmlidXRlKCd3aWR0aCcsbWF4KzEwKTsNCiAgICAgICAgZC5zZXRBdHRyaWJ1dGUoJ2hlaWdodCcsJzMzJyk7DQogICAgICAgIGQuc2V0QXR0cmlidXRlKCdzdHJva2UnLCcjOTk5OTk5Jyk7DQogICAgICAgIGQuc2V0QXR0cmlidXRlKCdmaWxsJywnd2hpdGUnKTsNCiAgICAgICAgZC5zZXRBdHRyaWJ1dGUoJ3knLDMzKmspOw0KICAgICAgICBmLnRleHRDb250ZW50PWRlc2NhcnJba107DQogICAgICAgIGYuc3R5bGUuZm9udFNpemU9JzEycHgnOw0KICAgICAgICBmLnN0eWxlLmZvbnRXZWlnaHQ9J2JvbGQnOw0KICAgICAgICBmLnNldEF0dHJpYnV0ZSgneCcsNSk7DQogICAgICAgIGYuc2V0QXR0cmlidXRlKCd5JywzMyprKzEyKTsNCiAgICAgICAgZS5zdHlsZS5mb250U2l6ZT0nMTJweCc7DQogICAgICAgIGUuc2V0QXR0cmlidXRlKCd5JywzMyprKzI4KTsNCiAgICAgICAgZS5zZXRBdHRyaWJ1dGUoJ3gnLDUpOw0KICAgICAgICBjLmFwcGVuZENoaWxkKGQpOw0KICAgICAgICBjLmFwcGVuZENoaWxkKGYpOw0KICAgICAgICBjLmFwcGVuZENoaWxkKGUpOw0KICAgICAgICBjLm9ubW91c2VvdmVyPWZ1bmN0aW9uICgpIHsNCiAgICAgICAgICAgIHRoaXMucXVlcnlTZWxlY3RvcigncmVjdCcpLnN0eWxlLmZpbGw9JyNlMWUxZmYnDQogICAgICAgIH07DQogICAgICAgIGMub25tb3VzZW91dD1mdW5jdGlvbiAoKSB7DQogICAgICAgICAgICB0aGlzLnF1ZXJ5U2VsZWN0b3IoJ3JlY3QnKS5zdHlsZS5maWxsPSd3aGl0ZScNCiAgICAgICAgfTsNCiAgICAgICAgcG9wdXAuYXBwZW5kQ2hpbGQoYyk7DQogICAgfQ0KICAgIHBvcHVwLnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgIHBvcHVwLnNldEF0dHJpYnV0ZSgnaHlwZXJsaW5rJywnJyk7DQogICAgcG9wdXAuc2V0QXR0cmlidXRlKCdlZDpsaW5raWQnLGxpbmtzW2ldLnBhcmVudE5vZGUuaWQpOw0KICAgIHBvcHVwLm9ubW91c2VvdmVyPWZ1bmN0aW9uICgpIHsNCiAgICAgICAgdGhpcy5zdHlsZS5kaXNwbGF5PSdibG9jayc7DQogICAgfTsNCiAgICBwb3B1cC5vbmNsaWNrPWZ1bmN0aW9uICgpIHsNCiAgICAgICAgdGhpcy5zdHlsZS5kaXNwbGF5PSdub25lJzsNCiAgICB9Ow0KICAgIHBvcHVwLm9ubW91c2VvdXQ9ZnVuY3Rpb24gKCkgew0KICAgICAgICB0aGlzLnN0eWxlLmRpc3BsYXk9J25vbmUnOw0KICAgIH07DQogICAgZG9jdW1lbnQucXVlcnlTZWxlY3RvcignI3N2Zy1jb250YWluZXIgPiBzdmcnKS5hcHBlbmRDaGlsZChwb3B1cCk7DQogICAgbGlua3NbaV0ub25tb3VzZW92ZXI9ZnVuY3Rpb24gKCkgew0KICAgICAgICB2YXIgbGlua2lkPXRoaXMucGFyZW50Tm9kZS5pZDsNCiAgICAgICAgdGhpcy5xdWVyeVNlbGVjdG9yKCdyZWN0Jykuc3R5bGUuZGlzcGxheT0nYmxvY2snOw0KICAgICAgICBkb2N1bWVudC5xdWVyeVNlbGVjdG9yKCJnW2VkXFw6bGlua2lkPSciK2xpbmtpZCsiJ11baHlwZXJsaW5rXSIpLnN0eWxlLmRpc3BsYXk9J2Jsb2NrJzsNCiAgICB9DQogICAgbGlua3NbaV0ub25tb3VzZW91dD1mdW5jdGlvbiAoKSB7DQogICAgICAgIHZhciBsaW5raWQ9dGhpcy5wYXJlbnROb2RlLmlkOw0KICAgICAgICB0aGlzLnF1ZXJ5U2VsZWN0b3IoJ3JlY3QnKS5zdHlsZS5kaXNwbGF5PSdub25lJzsNCiAgICAgICAgZG9jdW1lbnQucXVlcnlTZWxlY3RvcigiZ1tlZFxcOmxpbmtpZD0nIitsaW5raWQrIiddW2h5cGVybGlua10iKS5zdHlsZS5kaXNwbGF5PSdub25lJzsNCiAgICB9DQp9DQovLy0taHlwZXJsaW5rDQovL2luaXRpYWxpemUtLQ0KdmFyIHNoYXBlPWRvY3VtZW50LnF1ZXJ5U2VsZWN0b3JBbGwoJ2dbZWRcXDp0b2d0b3BpY2lkXScpOw0KdmFyIG1JZD1kb2N1bWVudC5xdWVyeVNlbGVjdG9yQWxsKCdnW2VkXFw6dG9waWN0eXBlXScpOw0KdmFyIGRhdGFUcmVlPXt9Ow0KdmFyIGV4dHJhUmVsYT17fTsNCnZhciBjaGVja0lEPScnOw0KZm9yKHZhciBpPTA7aTxtSWQubGVuZ3RoO2krKyl7DQogICAgdmFyIHR5cGU9bUlkW2ldLmdldEF0dHJpYnV0ZSgnZWQ6dG9waWN0eXBlJyk7DQogICAgdmFyIHNpZD1tSWRbaV0uaWQ7DQogICAgaWYodHlwZSE9PSdjYWxsb3V0Jyl7DQogICAgICAgIGluaXQoc2lkLGRhdGFUcmVlKQ0KICAgIH0NCn0NCmZ1bmN0aW9uIGluaXQoaWQsIG9iaikgew0KICAgIHZhciBjaGlsZHMgPSBkb2N1bWVudC5xdWVyeVNlbGVjdG9yQWxsKCJnW2VkXFw6cGFyZW50aWQ9JyIgKyBpZCArICInXTpub3QoW2VkXFw6dG9waWN0eXBlXSkiKTsNCiAgICB2YXIgY2FsbHMgPSBkb2N1bWVudC5xdWVyeVNlbGVjdG9yQWxsKCJnW2VkXFw6cGFyZW50aWQ9JyIgKyBpZCArICInXVtlZFxcOnRvcGljdHlwZV0iKTsNCiAgICB2YXIgc3VtbWFyeSA9IGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3JBbGwoInBhdGhbZWRcXDpwYXJlbnRpZCo9JyIgKyBpZCArICInXVtlZFxcOnR5cGU9J3N1bW1hcnknXSIpOw0KICAgIHZhciBib3VuZGFyeT0gZG9jdW1lbnQucXVlcnlTZWxlY3RvckFsbCgicGF0aFtlZFxcOnBhcmVudGlkKj0nIiArIGlkICsgIiddW2VkXFw6dHlwZT0nYm91bmRhcnknXSIpOw0KICAgIHZhciByZWxhZnJvbT1kb2N1bWVudC5xdWVyeVNlbGVjdG9yQWxsKCJnW2VkXFw6ZnJvbWlkKj0nIiArIGlkICsgIiddW2VkXFw6dHlwZT0ncmVsYXRpb24nXSIpOw0KICAgIHZhciByZWxhdG89ZG9jdW1lbnQucXVlcnlTZWxlY3RvckFsbCgiZ1tlZFxcOnRvaWQqPSciICsgaWQgKyAiJ11bZWRcXDp0eXBlPSdyZWxhdGlvbiddIik7DQogICAgb2JqWyJtIiArIGlkXSA9IHt9Ow0KICAgIHZhciB0eXBlID0gZG9jdW1lbnQuZ2V0RWxlbWVudEJ5SWQoaWQpLmdldEF0dHJpYnV0ZSgnZWQ6dG9waWN0eXBlJyk7DQogICAgdmFyIGl3PWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGlkKS5nZXRBdHRyaWJ1dGUoJ2VkOndpZHRoJyk7DQogICAgdmFyIGloPWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGlkKS5nZXRBdHRyaWJ1dGUoJ2VkOmhlaWdodCcpOw0KICAgIGlmICh0eXBlKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0udHlwZSA9IHR5cGU7DQogICAgfQ0KICAgIGlmKGl3JiZpaCl7DQogICAgICAgIG9ialsibSIgKyBpZF0ud2lkdGggPWl3Ow0KICAgICAgICBvYmpbIm0iICsgaWRdLmhlaWdodCA9aWg7DQogICAgfQ0KICAgIGlmIChyZWxhZnJvbS5sZW5ndGggIT09IDApIHsNCiAgICAgICAgb2JqWyJtIiArIGlkXS5yZWxhZnJvbSA9IHt9Ow0KICAgICAgICBmb3IgKHZhciBpID0gMDsgaSA8IHJlbGFmcm9tLmxlbmd0aDsgaSsrKSB7DQogICAgICAgICAgICB2YXIgaW5kZXhpZCA9IHJlbGFmcm9tW2ldLmlkOw0KICAgICAgICAgICAgdmFyIHRvaWQgPSBkb2N1bWVudC5nZXRFbGVtZW50QnlJZChpbmRleGlkKS5nZXRBdHRyaWJ1dGUoJ2VkOnRvaWQnKTsNCiAgICAgICAgICAgIGlmIChleHRyYVJlbGFbaW5kZXhpZF0gPT09IHVuZGVmaW5lZCkgew0KICAgICAgICAgICAgICAgIGV4dHJhUmVsYVtpbmRleGlkXSA9IHsNCiAgICAgICAgICAgICAgICAgICAgaWQ6IGluZGV4aWQsDQogICAgICAgICAgICAgICAgICAgIGZyb21pZDogaWQsDQogICAgICAgICAgICAgICAgICAgIHRvaWQ6IHRvaWQsDQogICAgICAgICAgICAgICAgICAgIGlzQzogZmFsc2UNCiAgICAgICAgICAgICAgICB9Ow0KICAgICAgICAgICAgfQ0KICAgICAgICAgICAgb2JqWyJtIiArIGlkXS5yZWxhZnJvbVtpbmRleGlkXT17fTsNCiAgICAgICAgICAgIG9ialsibSIgKyBpZF0ucmVsYWZyb20uZGlzcGxheT1kb2N1bWVudC5nZXRFbGVtZW50QnlJZChpZCkuc3R5bGUuZGlzcGxheSAhPT0gJ25vbmUnPydibG9jayc6J25vbmUnOw0KICAgICAgICB9DQogICAgfQ0KICAgIGlmIChyZWxhdG8ubGVuZ3RoICE9PSAwKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0ucmVsYXRvID0ge307DQogICAgICAgIGZvciAodmFyIGkgPSAwOyBpIDwgcmVsYXRvLmxlbmd0aDsgaSsrKSB7DQogICAgICAgICAgICB2YXIgaW5kZXhpZD1yZWxhdG9baV0uaWQ7DQogICAgICAgICAgICB2YXIgZnJvbWlkPWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGluZGV4aWQpLmdldEF0dHJpYnV0ZSgnZWQ6ZnJvbWlkJyk7DQogICAgICAgICAgICBpZihleHRyYVJlbGFbaW5kZXhpZF0gPT09IHVuZGVmaW5lZCl7DQogICAgICAgICAgICAgICAgZXh0cmFSZWxhW2luZGV4aWRdPXsNCiAgICAgICAgICAgICAgICAgICAgaWQ6aW5kZXhpZCwNCiAgICAgICAgICAgICAgICAgICAgZnJvbWlkOmZyb21pZCwNCiAgICAgICAgICAgICAgICAgICAgdG9pZDppZCwNCiAgICAgICAgICAgICAgICAgICAgaXNDOmZhbHNlDQogICAgICAgICAgICAgICAgfTsNCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIG9ialsibSIgKyBpZF0ucmVsYXRvW2luZGV4aWRdPXt9Ow0KICAgICAgICAgICAgb2JqWyJtIiArIGlkXS5yZWxhdG8uZGlzcGxheT1kb2N1bWVudC5nZXRFbGVtZW50QnlJZChpZCkuc3R5bGUuZGlzcGxheSAhPT0gJ25vbmUnPydibG9jayc6J25vbmUnOw0KICAgICAgICB9DQogICAgfQ0KICAgIGlmIChjaGlsZHMubGVuZ3RoICE9PSAwKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0uY2hpbGQgPSB7fTsNCiAgICAgICAgaWYgKGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3IoImdbZWRcXDp0b2d0b3BpY2lkPSciICsgaWQgKyAiJ10iKSkgew0KICAgICAgICAgICAgLy8gY29uc29sZS5sb2coZG9jdW1lbnQucXVlcnlTZWxlY3RvcigiZ1tlZFxcOnRvZ3RvcGljaWQ9JyIgKyBpZCArICInXSIpLmNoaWxkTm9kZXNbMF0uZ2V0QXR0cmlidXRlKCd4bGluazpocmVmJykpOw0KICAgICAgICAgICAgdmFyIHRvZyA9IGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3IoImdbZWRcXDp0b2d0b3BpY2lkPSciICsgaWQgKyAiJ10iKS5jaGlsZHJlblswXS5nZXRBdHRyaWJ1dGUoJ3hsaW5rOmhyZWYnKS5zbGljZSgxKTsNCiAgICAgICAgICAgIG9ialsibSIgKyBpZF0udG9ndHlwZSA9IHRvZzsNCiAgICAgICAgfQ0KICAgICAgICBmb3IgKHZhciBpID0gMDsgaSA8IGNoaWxkcy5sZW5ndGg7IGkrKykgew0KICAgICAgICAgICAgdmFyIGNpZCA9IGNoaWxkc1tpXS5pZDsNCiAgICAgICAgICAgIGluaXQoY2lkLCBvYmpbIm0iICsgaWRdLmNoaWxkKTsNCiAgICAgICAgfQ0KICAgIH0NCiAgICBpZiAoY2FsbHMubGVuZ3RoICE9PSAwKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0uY2FsbCA9IHt9Ow0KICAgICAgICBmb3IgKHZhciBpID0gMDsgaSA8IGNhbGxzLmxlbmd0aDsgaSsrKSB7DQogICAgICAgICAgICB2YXIgY2lkID0gY2FsbHNbaV0uaWQ7DQogICAgICAgICAgICBpbml0KGNpZCwgb2JqWyJtIiArIGlkXS5jYWxsKTsNCiAgICAgICAgfQ0KICAgIH0NCiAgICBpZiAoYm91bmRhcnkubGVuZ3RoICE9PSAwKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0uYm91bmRhcnkgPSB7fTsNCiAgICAgICAgZm9yICh2YXIgaSA9IDA7IGkgPCBib3VuZGFyeS5sZW5ndGg7IGkrKykgew0KICAgICAgICAgICAgdmFyIGNpZCA9Ym91bmRhcnlbaV0uaWQ7DQogICAgICAgICAgICBpbml0KGNpZCwgb2JqWyJtIiArIGlkXS5ib3VuZGFyeSk7DQogICAgICAgIH0NCiAgICB9DQogICAgaWYgKHN1bW1hcnkubGVuZ3RoICE9PSAwKSB7DQogICAgICAgIG9ialsibSIgKyBpZF0uc3VtbWFyeSA9IHt9Ow0KICAgICAgICBmb3IgKHZhciBpID0gMDsgaSA8IHN1bW1hcnkubGVuZ3RoOyBpKyspIHsNCiAgICAgICAgICAgIHZhciBjaWQgPSBzdW1tYXJ5W2ldLmlkOw0KICAgICAgICAgICAgaW5pdChjaWQsIG9ialsibSIgKyBpZF0uc3VtbWFyeSk7DQogICAgICAgIH0NCiAgICB9DQp9DQovLy0taW5pdGlhbGl6ZQ0KLy90b2dnbGVkaXNwbGF5LS0NCnZhciBjaGFpbkFycj1bXTsNCmZ1bmN0aW9uIGdldGNoYWluKGlkKXsNCiAgICBjaGFpbkFyci51bnNoaWZ0KCdtJytpZCk7DQogICAgdmFyIHBhcmVudD1kb2N1bWVudC5nZXRFbGVtZW50QnlJZChpZCkuZ2V0QXR0cmlidXRlKCdlZDpwYXJlbnRpZCcpOw0KICAgIGlmKCFwYXJlbnQpew0KICAgICAgICByZXR1cm47DQogICAgfQ0KICAgIGdldGNoYWluKHBhcmVudCk7DQp9DQpmdW5jdGlvbiBnZXRvYmooaWQpIHsNCiAgICBjaGFpbkFycj1bXTsNCiAgICBnZXRjaGFpbihpZCk7DQogICAgdmFyIG1haW49Y2hhaW5BcnJbMF07DQogICAgaWYoY2hhaW5BcnIubGVuZ3RoPjEpew0KICAgICAgICB2YXIgb2JqPWRhdGFUcmVlW21haW5dOw0KICAgICAgICAvLyBjb25zb2xlLmxvZyhjaGFpbkFycik7DQogICAgICAgIGZvcih2YXIgaT0xO2k8Y2hhaW5BcnIubGVuZ3RoO2krKykgew0KICAgICAgICAgICAgdmFyIGEgPSBjaGFpbkFycltpXTsNCiAgICAgICAgICAgIGZvcih2YXIgaj0wO2o8T2JqZWN0LmtleXMob2JqKS5sZW5ndGg7aisrKXsNCiAgICAgICAgICAgICAgICB2YXIgY29iaj0gb2JqW09iamVjdC5rZXlzKG9iailbal1dW2FdOw0KICAgICAgICAgICAgICAgIGlmKGNvYmopew0KICAgICAgICAgICAgICAgICAgICBvYmo9Y29iajsNCiAgICAgICAgICAgICAgICAgICAgY29udGludWUNCiAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICB9DQogICAgICAgIH0NCiAgICAgICAgcmV0dXJuIG9iag0KICAgIH1lbHNlew0KICAgICAgICB2YXIgb2JqPWRhdGFUcmVlW21haW5dOw0KICAgICAgICByZXR1cm4gb2JqDQogICAgfQ0KDQp9DQpmb3IodmFyIGk9MDtpPHNoYXBlLmxlbmd0aDtpKyspew0KICAgIHNoYXBlW2ldLm9uY2xpY2s9ZnVuY3Rpb24gKCkgew0KICAgICAgICB2YXIgaWQ9TnVtYmVyKHRoaXMuZ2V0QXR0cmlidXRlKCdlZDp0b2d0b3BpY2lkJykpOw0KICAgICAgICB2YXIgb2JqPWdldG9iaihpZCk7DQoNCiAgICAgICAgdmFyIHR5cGU9b2JqLnRvZ3R5cGU9PT0nbWludXMnPydwbHVzJzonbWludXMnOw0KICAgICAgICB2YXIgZGlzcGxheT1vYmoudG9ndHlwZT09PSdtaW51cyc/J25vbmUnOidibG9jayc7DQogICAgICAgIHRoaXMuY2hpbGRyZW5bMF0uc2V0QXR0cmlidXRlKCd4bGluazpocmVmJywnIycrdHlwZSk7DQogICAgICAgIG9iai50b2d0eXBlPXR5cGU7DQogICAgICAgIGNoZWNrSUQ9b2JqOw0KDQogICAgICAgIHV0ZChvYmosaWQsZGlzcGxheSk7DQogICAgICAgIGV4dHJhUmVsYUZpbigpOw0KICAgIH0NCn0NCmZ1bmN0aW9uIHV0ZChvYmosaWQsc2hvdyxvYykgew0KDQogICAgdmFyIHBzaG93PWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGlkKS5zdHlsZS5kaXNwbGF5IT09ICdub25lJz8nYmxvY2snOidub25lJzsNCiAgICBpZiAob2JqLnJlbGFmcm9tKXsNCiAgICAgICAgaWYob2JqLnJlbGFmcm9tLmRpc3BsYXkhPT0gcHNob3cpew0KICAgICAgICAgICAgdmFyIHJlbGFmcm9tcz1PYmplY3Qua2V5cyhvYmoucmVsYWZyb20pOw0KICAgICAgICAgICAgcmVsYWZyb21zLnNwbGljZShyZWxhZnJvbXMuaW5kZXhPZignZGlzcGxheScpLDEpOw0KICAgICAgICAgICAgZm9yKHZhciBrPTA7azxyZWxhZnJvbXMubGVuZ3RoO2srKyl7DQogICAgICAgICAgICAgICAgdmFyIGQ9cmVsYWZyb21zW2tdOw0KICAgICAgICAgICAgICAgIGV4dHJhUmVsYVtkXS5pc0M9dHJ1ZTsNCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIG9iai5yZWxhZnJvbS5kaXNwbGF5ID0gcHNob3c7DQogICAgICAgIH0NCiAgICB9DQogICAgaWYgKG9iai5yZWxhdG8pew0KICAgICAgICBpZihvYmoucmVsYXRvLmRpc3BsYXkhPT0gcHNob3cpew0KICAgICAgICAgICAgdmFyIHJlbGF0b3M9T2JqZWN0LmtleXMob2JqLnJlbGF0byk7DQogICAgICAgICAgICByZWxhdG9zLnNwbGljZShyZWxhdG9zLmluZGV4T2YoJ2Rpc3BsYXknKSwxKTsNCiAgICAgICAgICAgIGZvcih2YXIgaz0wO2s8cmVsYXRvcy5sZW5ndGg7aysrKXsNCiAgICAgICAgICAgICAgICB2YXIgZD1yZWxhdG9zW2tdOw0KICAgICAgICAgICAgICAgIGV4dHJhUmVsYVtkXS5pc0M9dHJ1ZTsNCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIG9iai5yZWxhdG8uZGlzcGxheSA9IHBzaG93Ow0KICAgICAgICB9DQogICAgfQ0KICAgIGlmKG9iai5jYWxsKXsNCiAgICAgICAgdmFyIGNhbGxzPU9iamVjdC5rZXlzKG9iai5jYWxsKTsNCiAgICAgICAgaWYoY2hlY2tJRCE9PW9iail7DQogICAgICAgICAgICBmb3IodmFyIGk9MDtpIDwgY2FsbHMubGVuZ3RoO2krKyl7DQogICAgICAgICAgICAgICAgdmFyIGE9Y2FsbHNbaV0uc2xpY2UoMSk7DQogICAgICAgICAgICAgICAgdmFyIGI9b2JqLmNhbGxbY2FsbHNbaV1dOw0KICAgICAgICAgICAgICAgIHZhciBjPWIudG9ndHlwZTsNCiAgICAgICAgICAgICAgICBkb2N1bWVudC5nZXRFbGVtZW50QnlJZChhKS5zdHlsZS5kaXNwbGF5PXNob3c7DQogICAgICAgICAgICAgICAgaWYgKGIucmVsYWZyb20mJiFjKXsNCiAgICAgICAgICAgICAgICAgICAgaWYoYi5yZWxhZnJvbS5kaXNwbGF5IT09IHNob3cpew0KICAgICAgICAgICAgICAgICAgICAgICAgdmFyIHJlbGFmcm9tcz1PYmplY3Qua2V5cyhiLnJlbGFmcm9tKTsNCiAgICAgICAgICAgICAgICAgICAgICAgIHJlbGFmcm9tcy5zcGxpY2UocmVsYWZyb21zLmluZGV4T2YoJ2Rpc3BsYXknKSwxKTsNCiAgICAgICAgICAgICAgICAgICAgICAgIGZvcih2YXIgaz0wO2s8cmVsYWZyb21zLmxlbmd0aDtrKyspew0KICAgICAgICAgICAgICAgICAgICAgICAgICAgIHZhciBkPXJlbGFmcm9tc1trXTsNCiAgICAgICAgICAgICAgICAgICAgICAgICAgICBleHRyYVJlbGFbZF0uaXNDPXRydWU7DQogICAgICAgICAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICAgICAgICAgICAgICBiLnJlbGFmcm9tLmRpc3BsYXkgPSBzaG93Ow0KICAgICAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgICAgIGlmIChiLnJlbGF0byYmIWMpew0KICAgICAgICAgICAgICAgICAgICBpZihiLnJlbGF0by5kaXNwbGF5IT09IHNob3cpew0KICAgICAgICAgICAgICAgICAgICAgICAgdmFyIHJlbGF0b3M9T2JqZWN0LmtleXMoYi5yZWxhdG8pOw0KICAgICAgICAgICAgICAgICAgICAgICAgcmVsYXRvcy5zcGxpY2UocmVsYXRvcy5pbmRleE9mKCdkaXNwbGF5JyksMSk7DQogICAgICAgICAgICAgICAgICAgICAgICBmb3IodmFyIGs9MDtrPHJlbGF0b3MubGVuZ3RoO2srKyl7DQogICAgICAgICAgICAgICAgICAgICAgICAgICAgdmFyIGQ9cmVsYXRvc1trXTsNCiAgICAgICAgICAgICAgICAgICAgICAgICAgICBleHRyYVJlbGFbZF0uaXNDPXRydWU7DQogICAgICAgICAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICAgICAgICAgICAgICBiLnJlbGF0by5kaXNwbGF5ID0gc2hvdzsNCiAgICAgICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICBpZihjKXsNCiAgICAgICAgICAgICAgICAgICAgZG9jdW1lbnQucXVlcnlTZWxlY3RvcigiZ1tlZFxcOnRvZ3RvcGljaWQ9JyIrYSsiJ10iKS5zdHlsZS5kaXNwbGF5PXNob3c7DQogICAgICAgICAgICAgICAgICAgIGlmKGM9PT0nbWludXMnKXsNCiAgICAgICAgICAgICAgICAgICAgICAgIHV0ZChiLGEsc2hvdykNCiAgICAgICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgICAgICAgICBpZiAoKGIuY2FsbHx8Yi5ib3VuZGFyeXx8Yi5zdW1tYXJ5KSYmYz09PSdwbHVzJykgew0KICAgICAgICAgICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93LHRydWUpDQogICAgICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICAgICAgaWYoYi5jYWxsJiYhYykgew0KICAgICAgICAgICAgICAgICAgICB1dGQoYixhLHNob3csdHJ1ZSkNCiAgICAgICAgICAgICAgICB9DQogICAgICAgICAgICAgICAgaWYgKGIuc3VtbWFyeSYmIWMpIHsNCiAgICAgICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93KQ0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICBpZiAoYi5ib3VuZGFyeSYmIWMpIHsNCiAgICAgICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93KQ0KICAgICAgICAgICAgICAgIH0NCg0KICAgICAgICAgICAgfQ0KICAgICAgICB9DQogICAgfQ0KICAgIGlmKG9iai5zdW1tYXJ5KXsNCiAgICAgICAgdmFyIHN1bW1hcnlzPU9iamVjdC5rZXlzKG9iai5zdW1tYXJ5KTsNCiAgICAgICAgaWYoKGNoZWNrSUQhPT1vYmomJihvYmoudG9ndHlwZT09PSdtaW51cyd8fCFvYmoudG9ndHlwZSkpfHxjaGVja0lEPT09b2JqKXsNCiAgICAgICAgICAgIGZvcih2YXIgaT0wO2k8c3VtbWFyeXMubGVuZ3RoO2krKyl7DQogICAgICAgICAgICAgICAgdmFyIGE9c3VtbWFyeXNbaV0uc2xpY2UoMSk7DQogICAgICAgICAgICAgICAgdmFyIGI9b2JqLnN1bW1hcnlbc3VtbWFyeXNbaV1dOw0KICAgICAgICAgICAgICAgIC8vIGNvbnNvbGUubG9nKGEpOw0KICAgICAgICAgICAgICAgIGRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGEpLnN0eWxlLmRpc3BsYXk9c2hvdzsNCi8vICAgICAgICAgICAgICAgIGlmKGMpew0KLy8gICAgICAgICAgICAgICAgICAgIGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3IoImdbZWRcXDp0b2d0b3BpY2lkPSciK2ErIiddIikuc3R5bGUuZGlzcGxheT1zaG93Ow0KLy8gICAgICAgICAgICAgICAgICAgIGlmKGM9PT0nbWludXMnKXsNCi8vICAgICAgICAgICAgICAgICAgICAgICAgdXRkKGIsc2hvdykNCi8vICAgICAgICAgICAgICAgICAgICB9DQovLyAgICAgICAgICAgICAgICAgICAgaWYgKGIuY2FsbCYmYz09PSdwbHVzJykgew0KLy8gICAgICAgICAgICAgICAgICAgICAgICB1dGQoYixzaG93LHRydWUpDQovLyAgICAgICAgICAgICAgICAgICAgfQ0KLy8gICAgICAgICAgICAgICAgfQ0KLy8gICAgICAgICAgICAgICAgaWYoYi5jYWxsJiYhYykgew0KLy8gICAgICAgICAgICAgICAgICAgIHV0ZChiLHNob3csdHJ1ZSkNCi8vICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICBpZihPYmplY3Qua2V5cyhiKS5sZW5ndGghPT0wKXsNCiAgICAgICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93KQ0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgIH0NCiAgICAgICAgfQ0KICAgIH0NCiAgICBpZihvYmouYm91bmRhcnkpew0KICAgICAgICB2YXIgYm91bmRhcnlzPU9iamVjdC5rZXlzKG9iai5ib3VuZGFyeSk7DQogICAgICAgIGlmKGNoZWNrSUQhPT1vYmopew0KICAgICAgICAgICAgZm9yKHZhciBpPTA7aTxib3VuZGFyeXMubGVuZ3RoO2krKyl7DQogICAgICAgICAgICAgICAgdmFyIGE9Ym91bmRhcnlzW2ldLnNsaWNlKDEpOw0KICAgICAgICAgICAgICAgIHZhciBiPW9iai5ib3VuZGFyeVtib3VuZGFyeXNbaV1dOw0KICAgICAgICAgICAgICAgIC8vIGNvbnNvbGUubG9nKGEpOw0KICAgICAgICAgICAgICAgIGRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGEpLnN0eWxlLmRpc3BsYXk9c2hvdzsNCi8vICAgICAgICAgICAgICAgIGlmKGMpew0KLy8gICAgICAgICAgICAgICAgICAgIGRvY3VtZW50LnF1ZXJ5U2VsZWN0b3IoImdbZWRcXDp0b2d0b3BpY2lkPSciK2ErIiddIikuc3R5bGUuZGlzcGxheT1zaG93Ow0KLy8gICAgICAgICAgICAgICAgICAgIGlmKGM9PT0nbWludXMnKXsNCi8vICAgICAgICAgICAgICAgICAgICAgICAgdXRkKGIsc2hvdykNCi8vICAgICAgICAgICAgICAgICAgICB9DQovLyAgICAgICAgICAgICAgICAgICAgaWYgKGIuY2FsbCYmYz09PSdwbHVzJykgew0KLy8gICAgICAgICAgICAgICAgICAgICAgICB1dGQoYixzaG93LHRydWUpDQovLyAgICAgICAgICAgICAgICAgICAgfQ0KLy8gICAgICAgICAgICAgICAgfQ0KLy8gICAgICAgICAgICAgICAgaWYoYi5jYWxsJiYhYykgew0KLy8gICAgICAgICAgICAgICAgICAgIHV0ZChiLHNob3csdHJ1ZSkNCi8vICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICBpZihPYmplY3Qua2V5cyhiKS5sZW5ndGghPT0wKXsNCiAgICAgICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93KQ0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgIH0NCiAgICAgICAgfQ0KICAgIH0NCiAgICBpZighb2MmJm9iai5jaGlsZCkgew0KICAgICAgICB2YXIgY2hpbGRzID0gT2JqZWN0LmtleXMob2JqLmNoaWxkKTsNCiAgICAgICAgZm9yICh2YXIgaSA9IDA7IGkgPCBjaGlsZHMubGVuZ3RoOyBpKyspIHsNCiAgICAgICAgICAgIHZhciBhID0gY2hpbGRzW2ldLnNsaWNlKDEpOw0KICAgICAgICAgICAgdmFyIGIgPSBvYmouY2hpbGRbY2hpbGRzW2ldXTsNCiAgICAgICAgICAgIHZhciBjID0gYi50b2d0eXBlOw0KICAgICAgICAgICAgZG9jdW1lbnQuZ2V0RWxlbWVudEJ5SWQoYSkuc3R5bGUuZGlzcGxheSA9IHNob3c7DQogICAgICAgICAgICBpZiAoYi5yZWxhZnJvbSYmIWMpew0KICAgICAgICAgICAgICAgIGlmKGIucmVsYWZyb20uZGlzcGxheSE9PSBzaG93KXsNCiAgICAgICAgICAgICAgICAgICAgdmFyIHJlbGFmcm9tcz1PYmplY3Qua2V5cyhiLnJlbGFmcm9tKTsNCiAgICAgICAgICAgICAgICAgICAgcmVsYWZyb21zLnNwbGljZShyZWxhZnJvbXMuaW5kZXhPZignZGlzcGxheScpLDEpOw0KICAgICAgICAgICAgICAgICAgICBmb3IodmFyIGs9MDtrPHJlbGFmcm9tcy5sZW5ndGg7aysrKXsNCiAgICAgICAgICAgICAgICAgICAgICAgIHZhciBkPXJlbGFmcm9tc1trXTsNCiAgICAgICAgICAgICAgICAgICAgICAgIGV4dHJhUmVsYVtkXS5pc0M9dHJ1ZTsNCiAgICAgICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgICAgICAgICBiLnJlbGFmcm9tLmRpc3BsYXkgPSBzaG93Ow0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIGlmIChiLnJlbGF0byYmIWMpew0KICAgICAgICAgICAgICAgIGlmKGIucmVsYXRvLmRpc3BsYXkhPT0gc2hvdyl7DQogICAgICAgICAgICAgICAgICAgIHZhciByZWxhdG9zPU9iamVjdC5rZXlzKGIucmVsYXRvKTsNCiAgICAgICAgICAgICAgICAgICAgcmVsYXRvcy5zcGxpY2UocmVsYXRvcy5pbmRleE9mKCdkaXNwbGF5JyksMSk7DQogICAgICAgICAgICAgICAgICAgIGZvcih2YXIgaz0wO2s8cmVsYXRvcy5sZW5ndGg7aysrKXsNCiAgICAgICAgICAgICAgICAgICAgICAgIHZhciBkPXJlbGF0b3Nba107DQogICAgICAgICAgICAgICAgICAgICAgICBleHRyYVJlbGFbZF0uaXNDPXRydWU7DQogICAgICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgICAgICAgICAgYi5yZWxhdG8uZGlzcGxheSA9IHNob3c7DQogICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgfQ0KICAgICAgICAgICAgaWYgKGMpIHsNCiAgICAgICAgICAgICAgICBkb2N1bWVudC5xdWVyeVNlbGVjdG9yKCJnW2VkXFw6dG9ndG9waWNpZD0nIiArIGEgKyAiJ10iKS5zdHlsZS5kaXNwbGF5ID0gc2hvdzsNCiAgICAgICAgICAgICAgICBpZiAoYyA9PT0gJ21pbnVzJykgew0KICAgICAgICAgICAgICAgICAgICB1dGQoYixhLHNob3cpDQogICAgICAgICAgICAgICAgfQ0KICAgICAgICAgICAgICAgIGlmICgoYi5jYWxsfHxiLmJvdW5kYXJ5fHxiLnN1bW1hcnkpJiZjPT09J3BsdXMnKSB7DQogICAgICAgICAgICAgICAgICAgIHV0ZChiLGEsc2hvdyx0cnVlKQ0KICAgICAgICAgICAgICAgIH0NCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIGlmIChiLmNhbGwmJiFjKSB7DQogICAgICAgICAgICAgICAgdXRkKGIsYSxzaG93LHRydWUpDQogICAgICAgICAgICB9DQogICAgICAgICAgICBpZiAoYi5zdW1tYXJ5JiYhYykgew0KICAgICAgICAgICAgICAgIHV0ZChiLGEsc2hvdykNCiAgICAgICAgICAgIH0NCiAgICAgICAgICAgIGlmIChiLmJvdW5kYXJ5JiYhYykgew0KICAgICAgICAgICAgICAgIHV0ZChiLGEsc2hvdykNCiAgICAgICAgICAgIH0NCiAgICAgICAgfQ0KICAgIH0NCn0NCg0KZnVuY3Rpb24gZXh0cmFSZWxhRmluKCkgew0KICAgIHZhciBleHRyYWtleXM9T2JqZWN0LmtleXMoZXh0cmFSZWxhKTsNCiAgICBmb3IodmFyIGk9MDtpPGV4dHJha2V5cy5sZW5ndGg7aSsrKXsNCiAgICAgICAgdmFyIGV4dHJhT2JqPWV4dHJhUmVsYVtleHRyYWtleXNbaV1dOw0KICAgICAgICBpZihleHRyYU9iai5pc0MgPT09IHRydWUpew0KICAgICAgICAgICAgdmFyIGZzaG93PWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGV4dHJhT2JqLmZyb21pZCkuc3R5bGUuZGlzcGxheSAhPT0nbm9uZSc/IHRydWU6IGZhbHNlOw0KICAgICAgICAgICAgdmFyIHRzaG93PWRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGV4dHJhT2JqLnRvaWQpLnN0eWxlLmRpc3BsYXkgIT09J25vbmUnPyB0cnVlOiBmYWxzZTsNCiAgICAgICAgICAgIGRvY3VtZW50LmdldEVsZW1lbnRCeUlkKGV4dHJhT2JqLmlkKS5zdHlsZS5kaXNwbGF5PWZzaG93ICYmIHRzaG93PyAnYmxvY2snOiAnbm9uZSc7DQogICAgICAgICAgICBleHRyYVJlbGFbZXh0cmFrZXlzW2ldXS5pc0MgPSBmYWxzZTsNCiAgICAgICAgfQ0KICAgIH0NCn0='))</script>
  </body>
</html>



