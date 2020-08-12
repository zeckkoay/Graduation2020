<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Graduation 2020</title>
    <style>
        body{
            overflow:hidden;
        }
        @font-face {
            font-family: "MaShanZheng";
            src: url('./resources/fonts/MaShanZheng-Regular.ttf'); /* IE9 Compat Modes */
            src: url('./resources/fonts/MaShanZheng-Regular.ttf?#iefix') format('embedded-opentype'), /* IE6-IE8 */
            url('./resources/fonts/MaShanZheng-Regular.ttf')  format('truetype') /* Safari, Android, iOS */
        }
        .hide{
            opacity:0;
            pointer-events: none;
        }
        #playScr{
            position:absolute;
            width:100%;
            height:100%;
            background-color:rgba(0,0,0,0);
            z-index:20;
        }
        #chinese-quotes{
            font-family: "MaShanZheng";
            color:#FFF;
            font-size: 96px;
        }
        #english-quotes{
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
            color:#FFF;
            font-size: 96px;
        }
        #chinese-quotes,#english-quotes, #chinese-quotes *,#english-quotes *{z-index:20;}
        section{display:block;width:100%;margin-bottom:8px;}
        #video-frame{
            min-width:1080px;width:1080px;max-width:1080px;
            min-height:1920px;height:1920px;max-height:1920px;
            margin:0 auto;position:relative;
            background-color:#000;
            overflow: hidden;
        }
        .bgcover{
            background-color:#000;
            position:absolute;
            width:100%;
            height:600px;
            z-index: 10;
        }
        #topbgcover{
            top:0;
        }
        #bottombgcover{
            bottom:0;
        }
        .text-center{text-align: center;}
        .tmp-border{border:1px solid #000;}
        .center-frames{
            position:absolute;
            top:50%;left:50%;
            transform: translate(-50%,-50%);
        }

        #DTLLS_0{
            height:0px;width:0px;
            filter: blur(10px);
            -webkit-filter: blur(10px);
            transition:height 3s linear, width 3s linear, filter 3s linear, -webkit-filter 3s linear;
        }
        #DTLLS_0.start{
            height:247px;width:330px;
            filter: blur(0px);
            -webkit-filter: blur(0px);
        }
        #DTLLS_1{
            width:330px;
            filter: blur(10px);
            -webkit-filter: blur(10px);
            opacity:0;
            transition:width 3s linear, filter 3s linear, -webkit-filter 3s linear,opacity 3s linear;
        }
        #DTLLS_1.start{
            width:1080px;
            filter: blur(0px);
            -webkit-filter: blur(0px);
            opacity:1;
        }
        .word-fade-in {
            animation: word-fade-in ease .3s;
            -webkit-animation: word-fade-in ease .3s;
            -moz-animation: word-fade-in ease .3s;
            -o-animation: word-fade-in ease .3s;
            -ms-animation: word-fade-in ease .3s;
        }
        @keyframes word-fade-in {
            0% {
                opacity:0;
            }
            100% {
                opacity:1;
            }
        }
        @-moz-keyframes word-fade-in {
            0% {
                opacity:0;
            }
            100% {
                opacity:1;
            }
        }
        @-webkit-keyframes word-fade-in {
            0% {
                opacity:0;
            }
            100% {
                opacity:1;
            }
        }
        @-o-keyframes word-fade-in {
            0% {
                opacity:0;
            }
            100% {
                opacity:1;
            }
        }
        @-ms-keyframes word-fade-in {
            0% {
                opacity: 0;
            }
            100% {
                opacity: 1;
            }
        }
        div[id^="cq-"]{
            position:absolute;
            width: 90%;
            top:300px;
            left:50%;
            overflow: visible;
            word-wrap: unset;
            transform: translate(-50%,-50%);
            height:210px;
        }
        div[id^="cq-"] section.even,div[id^="eq-"] section.even{text-align:right;}
        div[id^="eq-"]{
            position:absolute;
            width: 90%;
            bottom:300px;
            left:50%;
            overflow: visible;
            word-wrap: unset;
            transform: translate(-50%,-50%);
            height:210px;
        }
        #eq-0 section:nth-child(2){text-align:right;}
        #chinese-quotes chara{
            opacity: 0;
            transition: opacity ease .5s,font-size ease .3s;
            font-size: 0px;
        }
        #chinese-quotes chara.word-fade-in{
            opacity: 1;
            font-size: 96px;
        }
        #english-quotes chara{
            opacity: 0;
            transition: opacity ease .5s,font-size ease .3s;
            font-size: 0px;
        }
        #english-quotes chara.word-fade-in{
            opacity: 1;
            font-size: 72px;
        }
        #GraduanThrowHats{
            opacity: 0;
            transition: opacity .5s ease;
        }
        #GraduanThrowHats.start{
            opacity: 1;
        }
        #GraduanThrowHats svg{
            position:absolute;
            bottom:0;
        }
        #GraduanThrowHats svg #Hats{
            transform:translate(0,800px);
            transition:transform 1s ease-out;
        }
        #GraduanThrowHats svg #Hands,#GraduanThrowHats svg #Peoples{
            transform:translate(0,800px);
            transition:transform 1s ease-out;
        }
        #GraduanThrowHats svg #Hats.start{
            transform:translate(-20px,0);
        }
        #GraduanThrowHats svg #Hands.start,#GraduanThrowHats svg #Peoples.start{
            transform:translate(0,0);
        }
        svg[id^="firework-"] rect{
            fill:rgba(0,0,0,0);
        }
        #firework-0,#firework-1,#firework-2,#firework-3{
            position:absolute;
        }
        #FirstScene-0{
            z-index:5;
            width:100%;height:715.43px;
            opacity: 0;
            transition:opacity 1s ease-in-out;
        }
        #FirstScene-0.start{
            opacity: .5;
        }
        #firework-0{
            transform: translate(-25%,-25%) rotate(60deg);
        }
        #firework-1{
            transform: translate(25%,-25%) rotate(180deg);
        }
        #firework-2{
            transform: translate(-25%,25%) rotate(300deg);
        }
        #firework-3{
            transform: translate(25%,25%) rotate(300deg);
        }
        #FirstScene-1{
            position: absolute;
            top: 675px;
            left: 170px;
            z-index:6;
            opacity:0;
            transition:opacity 1s ease-in-out 1s;
        }
        #FirstScene-1.start{
            opacity:1;
        }
        .bounce-7 {
            animation-name: bounce-7;
            animation-timing-function: cubic-bezier(0.280, 0.840, 0.420, 1);
            animation-duration: 2s;
            animation-iteration-count: infinite;
        }
        @keyframes bounce-7 {
            0%   { transform: scale(1,1)      translateY(0); }
            10%  { transform: scale(1.1,.9)   translateY(0); }
            30%  { transform: scale(.9,1.1)   translateY(-100px); }
            50%  { transform: scale(1.05,.95) translateY(0); }
            57%  { transform: scale(1,1)      translateY(-7px); }
            64%  { transform: scale(1,1)      translateY(0); }
            100% { transform: scale(1,1)      translateY(0); }
        }
        #playBtn{
            position:absolute;
            top: 1120px;
            left: 1040px;
            transform: scale(5);
        }
        #playClickable{
            position:absolute;
            top:0;
            width:100%;height:100%;
            background-color:rgba(0,0,0,0);
            cursor: pointer;
        }
        #img-monitor{
            position:absolute;
            top: -1000px;
            left: 400px;
            transform:scale(2);
            transition:top 1.75s ease-out;
        }
        #img-monitor.start{
            position:absolute;
            top: 760px;
            left: 400px;
            transform:scale(2);
        }
        #YT-logo{
            transform: translate(-80px,-230px) skew(10deg, 0deg);
            opacity:0;
            transition: opacity .5s ease-in-out;
        }
        #YT-logo.start{
            opacity:1;
        }
        #LastScene{
            width:0%;
            transition:width 1.8s ease-in-out;
        }
        #LastScene.start{
            width:100%;
        }
    </style>
</head>
<body>
    <div id="video-frame" class="tmp-border">
        <div id="playScr">
            <div style="width:100%;height:100%;background-color:#000;opacity:.9;"></div>
            <div id="playBtn">
                <svg id="svg1307">
                    <defs id="defs1309">
                        <linearGradient
                            id="linearGradient2306"
                            y2="95"
                            gradientUnits="userSpaceOnUse"
                            x2="70.827"
                            gradientTransform="translate(-45 -71.094)"
                            y1="124.12"
                            x1="71.289"
                        >
                            <stop
                                id="stop5077"
                                style="stop-color:#adb0a8"
                                offset="0"
                            />
                            <stop
                                id="stop5079"
                                style="stop-color:#464744"
                                offset="1"
                            />
                        </linearGradient>
                        <radialGradient
                            id="radialGradient2314"
                            gradientUnits="userSpaceOnUse"
                            cy="83.991"
                            cx="107.59"
                            gradientTransform="matrix(.053243 -.83624 2.0195 .12857 -151.92 108.08)"
                            r="12.552"
                        >
                            <stop
                                id="stop2693"
                                style="stop-color:#ffffff"
                                offset="0"
                            />
                            <stop
                                id="stop2695"
                                style="stop-color:#d3d7cf"
                                offset="1"
                            />
                        </radialGradient>
                        <linearGradient
                            id="linearGradient2690"
                            y2="88.924"
                            gradientUnits="userSpaceOnUse"
                            x2="70.952"
                            gradientTransform="matrix(1.1282 0 0 1.1282 -53.993 -83.36)"
                            y1="101.74"
                            x1="70.914"
                        >
                            <stop
                                id="stop2686"
                                style="stop-color:#ffffff"
                                offset="0"
                            />
                            <stop
                                id="stop2688"
                                style="stop-color:#000000"
                                offset="1"
                            />
                        </linearGradient>
                    </defs>
                    <sodipodi:namedview
                        id="base"
                        inkscape:showpageshadow="false"
                        inkscape:zoom="1"
                        borderopacity="0.19607843"
                        inkscape:current-layer="layer1"
                        stroke="#555753"
                        guidetolerance="1px"
                        fill="#555753"
                        inkscape:grid-points="true"
                        inkscape:grid-bbox="true"
                        showgrid="false"
                        showguides="false"
                        bordercolor="#666666"
                        inkscape:window-x="326"
                        inkscape:guide-bbox="true"
                        inkscape:window-y="160"
                        inkscape:window-width="872"
                        inkscape:pageopacity="0.0000000"
                        inkscape:pageshadow="2"
                        pagecolor="#ffffff"
                        inkscape:cx="-117.42449"
                        inkscape:cy="12.980288"
                        inkscape:document-units="px"
                        inkscape:window-height="688"
                        showborder="true"
                    >
                        <sodipodi:guide
                            id="guide2194"
                            position="38.996647"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide2196"
                            position="9.0140845"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide2198"
                            position="9.0140845"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide2200"
                            position="38.975184"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide2202"
                            position="22.988281"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide2204"
                            position="23.908786"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide4332"
                            position="157.99417"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide4334"
                            position="-36.062446"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide4336"
                            position="-58.02695"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide4338"
                            position="180.00287"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide4417"
                            position="107.92217"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide4419"
                            position="129.93087"
                            orientation="vertical"
                        />
                        <sodipodi:guide
                            id="guide5106"
                            position="19.996875"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide5119"
                            position="63.039674"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide5121"
                            position="49.066305"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide5307"
                            position="-86.007168"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide5309"
                            position="-108.09009"
                            orientation="horizontal"
                        />
                        <sodipodi:guide
                            id="guide3111"
                            position="-100.15429"
                            orientation="horizontal"
                        />
                        <inkscape:grid
                            id="GridFromPre046Settings"
                            opacity=".2"
                            color="#0000ff"
                            originy="0px"
                            originx="0px"
                            empspacing="2"
                            spacingy="0.5px"
                            spacingx="0.5px"
                            empopacity="0.4"
                            type="xygrid"
                            empcolor="#0000ff"
                        />
                    </sodipodi:namedview>
                    <g
                        id="layer1"
                        inkscape:label="Layer 1"
                        inkscape:groupmode="layer"
                    >
                        <path
                            id="path2682"
                            style="stroke-linejoin:round;opacity:.15;color:#000000;stroke:url(#linearGradient2690);stroke-linecap:square;stroke-width:2;fill:none"
                            inkscape:r_cy="true"
                            inkscape:r_cx="true"
                            sodipodi:nodetypes="cccc"
                            d="m12 39.5v-30.5l26.07 14.817-26.07 15.683z"
                        />
                        <path
                            id="path3375"
                            style="fill-rule:evenodd;color:#000000;fill:url(#radialGradient2314)"
                            inkscape:r_cy="true"
                            inkscape:r_cx="true"
                            sodipodi:nodetypes="cccc"
                            d="m12.499 37.811v-27.811l24.104 13.906-24.104 13.905z"
                        />
                        <path
                            id="path2479"
                            style="stroke-linejoin:round;color:#000000;stroke:url(#linearGradient2306);stroke-linecap:square;fill:none"
                            inkscape:r_cy="true"
                            inkscape:r_cx="true"
                            sodipodi:nodetypes="cccc"
                            d="m12.499 37.811v-27.811l24.104 13.906-24.104 13.905z"
                        />
                        <path
                            id="path2481"
                            style="fill-rule:evenodd;color:#000000;fill:#ffffff"
                            inkscape:r_cy="true"
                            inkscape:r_cx="true"
                            sodipodi:nodetypes="cccccccc"
                            d="m12.999 10.874v26.063l22.594-13.031-22.594-13.032zm1 1.75l19.563 11.282-19.563 11.281v-22.563z"
                        />
                        <path
                            id="path2339"
                            style="opacity:.5;color:#000000;display:block;fill:#ffffff"
                            inkscape:r_cy="true"
                            inkscape:r_cx="true"
                            sodipodi:nodetypes="cccc"
                            d="m13.938 12.562v11.688c4.269-0.045 9.164-0.346 17.062-1.875l-17.062-9.813z"
                        />
                    </g>
                </svg>
            </div>
            <div id="playClickable"></div>
        </div>
        <div id="FirstScene-0" class="center-frames">
            <svg id="firework-0" width="100%" height="100%" viewBox="0 0 600 600"
                 xmlns="http://www.w3.org/2000/svg"
                 xmlns:xlink="http://www.w3.org/1999/xlink">
                <defs>
                    <clipPath id="firework-0-cp1">
                        <circle cx="225" cy="225" r="225">
                            <animate id="firework-0-a1" attributeName="r" values="1;225;" begin="0.1s;firework-0-a3.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-0-cp2">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-0-a2" attributeName="r" values="1;225;" begin="firework-0-a1.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-0-cp3">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-0-a3" attributeName="r" values="1;225;" begin="firework-0-a2.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <image id="firework-0-red" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-pink.svg"/>
                    <image id="firework-0-green" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-green.svg"/>
                    <image id="firework-0-blue" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-blue.svg"/>
                </defs>

                <rect x="-250%" y="-250%" width="500%" height="500%"/>
                <g transform="translate(0,40)">
                    <use xlink:href="#firework-0-red" style="clip-path:url(#firework-0-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-0-a3.end+0.1s;" dur=".5s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,150)">
                    <use xlink:href="#firework-0-blue" style="clip-path:url(#firework-0-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-0-a3.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,0)">
                    <use xlink:href="#firework-0-blue" style="clip-path:url(#firework-0-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a1.end+0.1s;" dur="1.5s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,0)">
                    <use xlink:href="#firework-0-red" style="clip-path:url(#firework-0-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a1.end+0.1s;" dur="1.3s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(55,150)">
                    <use xlink:href="#firework-0-green" style="clip-path:url(#firework-0-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a1.end+0.1s;" dur="1.1s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,150)">
                    <use xlink:href="#firework-0-blue" style="clip-path:url(#firework-0-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a2.end+0.1s;" dur="1.8s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(80,0)">
                    <use xlink:href="#firework-0-green" style="clip-path:url(#firework-0-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a2.end+0.1s;" dur="1.4s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(130,150)">
                    <use xlink:href="#firework-0-red" style="clip-path:url(#firework-0-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-0-a2.end+0.1s;" dur=".9s"
                                 fill="freeze"/>
                    </use>
                </g>
            </svg>
            <svg id="firework-1" width="100%" height="100%" viewBox="0 0 600 600"
                 xmlns="http://www.w3.org/2000/svg"
                 xmlns:xlink="http://www.w3.org/1999/xlink">
                <defs>
                    <clipPath id="firework-1-cp1">
                        <circle cx="225" cy="225" r="225">
                            <animate id="firework-1-a1" attributeName="r" values="1;225;" begin="0.1s;firework-1-a3.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-1-cp2">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-1-a2" attributeName="r" values="1;225;" begin="firework-1-a1.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-1-cp3">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-1-a3" attributeName="r" values="1;225;" begin="firework-1-a2.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <image id="firework-1-red" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-pink.svg"/>
                    <image id="firework-1-green" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-green.svg"/>
                    <image id="firework-1-blue" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-blue.svg"/>
                </defs>

                <rect x="-250%" y="-250%" width="500%" height="500%"/>
                <g transform="translate(0,40)">
                    <use xlink:href="#firework-1-red" style="clip-path:url(#firework-1-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-1-a3.end+0.1s;" dur=".5s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,150)">
                    <use xlink:href="#firework-1-blue" style="clip-path:url(#firework-1-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-1-a3.end+0.1s;" dur="1.5s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,0)">
                    <use xlink:href="#firework-1-blue" style="clip-path:url(#firework-1-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a1.end+0.1s;" dur="1.2s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,0)">
                    <use xlink:href="#firework-1-red" style="clip-path:url(#firework-1-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a1.end+0.1s;" dur=".8s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(55,150)">
                    <use xlink:href="#firework-1-green" style="clip-path:url(#firework-1-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a1.end+0.1s;" dur="1.8s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,150)">
                    <use xlink:href="#firework-1-blue" style="clip-path:url(#firework-1-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a2.end+0.1s;" dur="1.6s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(80,0)">
                    <use xlink:href="#firework-1-green" style="clip-path:url(#firework-1-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a2.end+0.1s;" dur="1.35s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(130,150)">
                    <use xlink:href="#firework-1-red" style="clip-path:url(#firework-1-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-1-a2.end+0.1s;" dur="1.2s"
                                 fill="freeze"/>
                    </use>
                </g>
            </svg>
            <svg id="firework-2" width="100%" height="100%" viewBox="0 0 600 600"
                 xmlns="http://www.w3.org/2000/svg"
                 xmlns:xlink="http://www.w3.org/1999/xlink">
                <defs>
                    <clipPath id="firework-2-cp1">
                        <circle cx="225" cy="225" r="225">
                            <animate id="firework-2-a1" attributeName="r" values="1;225;" begin="0.1s;firework-2-a3.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-2-cp2">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-2-a2" attributeName="r" values="1;225;" begin="firework-2-a1.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-2-cp3">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-2-a3" attributeName="r" values="1;225;" begin="firework-2-a2.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <image id="firework-2-red" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-pink.svg"/>
                    <image id="firework-2-green" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-green.svg"/>
                    <image id="firework-2-blue" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-blue.svg"/>
                </defs>

                <rect x="-250%" y="-250%" width="500%" height="500%"/>
                <g transform="translate(0,40)">
                    <use xlink:href="#firework-2-red" style="clip-path:url(#firework-2-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-2-a3.end+0.1s;" dur="1.3s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,150)">
                    <use xlink:href="#firework-2-blue" style="clip-path:url(#firework-2-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-2-a3.end+0.1s;" dur="1.6s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,0)">
                    <use xlink:href="#firework-2-blue" style="clip-path:url(#firework-2-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a1.end+0.1s;" dur="1.9s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,0)">
                    <use xlink:href="#firework-2-red" style="clip-path:url(#firework-2-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a1.end+0.1s;" dur="2.9s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(55,150)">
                    <use xlink:href="#firework-2-green" style="clip-path:url(#firework-2-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a1.end+0.1s;" dur="2.6s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,150)">
                    <use xlink:href="#firework-2-blue" style="clip-path:url(#firework-2-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a2.end+0.1s;" dur="1.8s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(80,0)">
                    <use xlink:href="#firework-2-green" style="clip-path:url(#firework-2-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a2.end+0.1s;" dur=".6s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(130,150)">
                    <use xlink:href="#firework-2-red" style="clip-path:url(#firework-2-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-2-a2.end+0.1s;" dur=".3s"
                                 fill="freeze"/>
                    </use>
                </g>
            </svg>
            <svg id="firework-3" width="100%" height="100%" viewBox="0 0 600 600"
                 xmlns="http://www.w3.org/2000/svg"
                 xmlns:xlink="http://www.w3.org/1999/xlink">
                <defs>
                    <clipPath id="firework-3-cp1">
                        <circle cx="225" cy="225" r="225">
                            <animate id="firework-3-a1" attributeName="r" values="1;225;" begin="0.1s;firework-3-a3.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-3-cp2">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-3-a2" attributeName="r" values="1;225;" begin="firework-3-a1.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <clipPath id="firework-3-cp3">
                        <circle cx="225" cy="225" r="1">
                            <animate id="firework-3-a3" attributeName="r" values="1;225;" begin="firework-3-a2.end+0.1s" dur="0.4s"
                                     fill="freeze"/>
                        </circle>
                    </clipPath>
                    <image id="firework-3-red" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-pink.svg"/>
                    <image id="firework-3-green" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-green.svg"/>
                    <image id="firework-3-blue" width="450" height="462"
                           xlink:href="https://freesvg.org/storage/zip/blog/fireworks-blue.svg"/>
                </defs>

                <rect x="-250%" y="-250%" width="500%" height="500%"/>
                <g transform="translate(0,40)">
                    <use xlink:href="#firework-3-red" style="clip-path:url(#firework-3-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-3-a3.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,150)">
                    <use xlink:href="#firework-3-blue" style="clip-path:url(#firework-3-cp1);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="0s;firework-3-a3.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,0)">
                    <use xlink:href="#firework-3-blue" style="clip-path:url(#firework-3-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a1.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(110,0)">
                    <use xlink:href="#firework-3-red" style="clip-path:url(#firework-3-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a1.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(55,150)">
                    <use xlink:href="#firework-3-green" style="clip-path:url(#firework-3-cp2);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a1.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>

                <g transform="translate(0,150)">
                    <use xlink:href="#firework-3-blue" style="clip-path:url(#firework-3-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a2.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(80,0)">
                    <use xlink:href="#firework-3-green" style="clip-path:url(#firework-3-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a2.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
                <g transform="translate(130,150)">
                    <use xlink:href="#firework-3-red" style="clip-path:url(#firework-3-cp3);">
                        <animate attributeName="opacity" values="1;1;0.5;0.1;" begin="firework-3-a2.end+0.1s;" dur="1s"
                                 fill="freeze"/>
                    </use>
                </g>
            </svg>
        </div>
        <div id="FirstScene-1" class="bounce-7">
            <svg id="GraduationIcon0" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg"
                 xmlns:xlink="http://www.w3.org/1999/xlink" width="795.39431" height="574.03802"
                 viewBox="0 0 795.39431 574.03802">
                <defs>
                    <linearGradient id="b2a81085-935f-40be-bb27-75940df8c338" x1="-450.78971" y1="2803.04671"
                                    x2="-450.78971" y2="2729.34772"
                                    gradientTransform="translate(3217.53309 1009.65784) rotate(90)"
                                    gradientUnits="userSpaceOnUse">
                        <stop offset="0" stop-color="gray" stop-opacity="0.25"/>
                        <stop offset="0.53514" stop-color="gray" stop-opacity="0.12"/>
                        <stop offset="1" stop-color="gray" stop-opacity="0.1"/>
                    </linearGradient>
                </defs>
                <title>Graduation</title>
                <ellipse cx="232.05775" cy="450.06897" rx="35.09476" ry="5.26421"
                         transform="translate(-476.55674 294.92367) rotate(-63.61079)" fill="#e0e0e0"/>
                <ellipse cx="670.57742" cy="667.85592" rx="35.09476" ry="3.57677"
                         transform="translate(-428.03695 808.73554) rotate(-63.61079)" fill="#e0e0e0"/>
                <rect x="397.95325" y="566.93514" width="21.05685" height="70.18951"
                      transform="translate(274.52069 -285.26226) rotate(39.54732)" fill="#f55f44"/>
                <rect x="409.32507" y="573.56618" width="23.69234" height="70.18951"
                      transform="translate(489.54965 1134.58125) rotate(-166.7689)" opacity="0.05"/>
                <rect x="411.92558" y="573.86778" width="21.05685" height="70.18951"
                      transform="translate(492.0121 1135.47005) rotate(-166.7689)" fill="#f55f44"/>
                <rect x="414.48638" y="314.08219" width="73.69899" height="489.57186"
                      transform="translate(-452.20218 551.7936) rotate(-63.61079)"
                      fill="url(#b2a81085-935f-40be-bb27-75940df8c338)"/>
                <path d="M655.01556,699.105c-8.584-4.11751-444.8438-220.718-438.55625-217.5983,24.21371-36.95739,31.19689-62.87545,31.19689-62.87545l438.55625,217.5983S670.81132,663.25857,655.01556,699.105Z"
                      transform="translate(-202.30284 -162.98099)" fill="#f5f5f5"/>
                <rect x="421.72508" y="519.09383" width="40.35897" height="70.18951"
                      transform="translate(90.06389 -301.64381) rotate(26.38921)" opacity="0.05"/>
                <rect x="423.47981" y="519.09383" width="36.8495" height="70.18951"
                      transform="translate(90.06389 -301.64381) rotate(26.38921)" fill="#f55f44"/>
                <rect x="428.83545" y="518.70387" width="24.56633" height="70.18951"
                      transform="translate(89.80867 -301.33512) rotate(26.38921)" opacity="0.05"/>
                <rect x="430.59019" y="518.70387" width="21.05685" height="70.18951"
                      transform="translate(89.80867 -301.33512) rotate(26.38921)" fill="#f55f44"/>
                <circle cx="261.30557" cy="563.92499" r="2.92569" fill="#dbdbdb"/>
                <g opacity="0.5">
                    <rect x="29.39431" y="482" width="3" height="17" fill="#47e6b1"/>
                    <rect x="231.69716" y="644.98099" width="3" height="17"
                          transform="translate(684.3753 257.30284) rotate(90)" fill="#47e6b1"/>
                </g>
                <g opacity="0.5">
                    <rect x="785.39431" y="270" width="3" height="17" fill="#47e6b1"/>
                    <rect x="987.69716" y="432.98099" width="3" height="17"
                          transform="translate(1228.3753 -710.69716) rotate(90)" fill="#47e6b1"/>
                </g>
                <g opacity="0.5">
                    <rect x="47.39431" y="59" width="3" height="17" fill="#47e6b1"/>
                    <rect x="249.69716" y="221.98099" width="3" height="17"
                          transform="translate(279.3753 -183.69716) rotate(90)" fill="#47e6b1"/>
                </g>
                <g opacity="0.5">
                    <rect x="695.39431" y="33" width="3" height="17" fill="#47e6b1"/>
                    <rect x="897.69716" y="195.98099" width="3" height="17"
                          transform="translate(901.3753 -857.69716) rotate(90)" fill="#47e6b1"/>
                </g>
                <path d="M214.59252,416.4373a3.67458,3.67458,0,0,1-2.04749-4.441,1.76592,1.76592,0,0,0,.0799-.40754h0a1.84257,1.84257,0,0,0-3.31045-1.22119h0a1.76637,1.76637,0,0,0-.2039.3618,3.67459,3.67459,0,0,1-4.441,2.04749,1.766,1.766,0,0,0-.40754-.07991h0a1.84258,1.84258,0,0,0-1.22119,3.31045h0a1.76606,1.76606,0,0,0,.3618.20389,3.67462,3.67462,0,0,1,2.04749,4.441,1.76594,1.76594,0,0,0-.07991.40754h0a1.84257,1.84257,0,0,0,3.31045,1.22119h0a1.7659,1.7659,0,0,0,.2039-.3618,3.67459,3.67459,0,0,1,4.441-2.04749,1.76665,1.76665,0,0,0,.40755.07991h0a1.84257,1.84257,0,0,0,1.22119-3.31045h0A1.76684,1.76684,0,0,0,214.59252,416.4373Z"
                      transform="translate(-202.30284 -162.98099)" fill="#4d8af0" opacity="0.5"/>
                <path d="M386.59252,219.4373a3.67458,3.67458,0,0,1-2.04749-4.441,1.76592,1.76592,0,0,0,.0799-.40754h0a1.84257,1.84257,0,0,0-3.31045-1.22119h0a1.76637,1.76637,0,0,0-.2039.3618,3.67459,3.67459,0,0,1-4.441,2.04749,1.766,1.766,0,0,0-.40754-.07991h0a1.84258,1.84258,0,0,0-1.22119,3.31045h0a1.76606,1.76606,0,0,0,.3618.20389,3.67462,3.67462,0,0,1,2.04749,4.441,1.76594,1.76594,0,0,0-.07991.40754h0a1.84257,1.84257,0,0,0,3.31045,1.22119h0a1.7659,1.7659,0,0,0,.2039-.3618,3.67459,3.67459,0,0,1,4.441-2.04749,1.76665,1.76665,0,0,0,.40755.07991h0a1.84257,1.84257,0,0,0,1.22119-3.31045h0A1.76684,1.76684,0,0,0,386.59252,219.4373Z"
                      transform="translate(-202.30284 -162.98099)" fill="#4d8af0" opacity="0.5"/>
                <path d="M596.59252,730.4373a3.67458,3.67458,0,0,1-2.04749-4.441,1.76592,1.76592,0,0,0,.0799-.40754h0a1.84257,1.84257,0,0,0-3.31045-1.22119h0a1.76637,1.76637,0,0,0-.2039.3618,3.67459,3.67459,0,0,1-4.441,2.04749,1.766,1.766,0,0,0-.40754-.07991h0a1.84258,1.84258,0,0,0-1.22119,3.31045h0a1.76606,1.76606,0,0,0,.3618.20389,3.67462,3.67462,0,0,1,2.04749,4.441,1.76594,1.76594,0,0,0-.07991.40754h0a1.84257,1.84257,0,0,0,3.31045,1.22119h0a1.7659,1.7659,0,0,0,.2039-.3618,3.67459,3.67459,0,0,1,4.441-2.04749,1.76665,1.76665,0,0,0,.40755.07991h0a1.84257,1.84257,0,0,0,1.22119-3.31045h0A1.76684,1.76684,0,0,0,596.59252,730.4373Z"
                      transform="translate(-202.30284 -162.98099)" fill="#4d8af0" opacity="0.5"/>
                <circle cx="759.39431" cy="444" r="6" fill="#f55f44" opacity="0.5"/>
                <circle cx="627.39431" cy="482" r="6" fill="#4d8af0" opacity="0.5"/>
                <circle cx="103.39431" cy="541" r="6" fill="#47e6b1" opacity="0.5"/>
                <circle cx="411.39431" cy="6" r="6" fill="#f55f44" opacity="0.5"/>
                <path d="M407.19716,520.481l-24,36s8,37,185,36,191-36,191-36l-33-48-101-69Z"
                      transform="translate(-202.30284 -162.98099)" fill="#6c63ff"/>
                <path d="M407.19716,520.481l-24,36s8,37,185,36,191-36,191-36l-33-48-101-69Z"
                      transform="translate(-202.30284 -162.98099)" opacity="0.15"/>
                <polygon
                        points="715.394 224 400.394 363 16.394 224 368.394 64 541.184 143.67 547.374 146.53 715.394 224"
                        fill="#6c63ff"/>
                <polygon
                        points="715.394 224 400.394 363 16.394 224 368.394 64 541.184 143.67 547.374 146.53 715.394 224"
                        opacity="0.15"/>
                <polygon points="553.894 257.32 547.894 257.68 541.184 143.67 547.374 146.53 553.894 257.32"
                         fill="#f5f5f5"/>
                <path d="M411.19716,386.481l-28,170s201-65,376,0l-26-180S498.19716,347.481,411.19716,386.481Z"
                      transform="translate(-202.30284 -162.98099)" fill="#6c63ff"/>
                <ellipse cx="553.39431" cy="272" rx="29" ry="20" fill="#f5f5f5"/>
            </svg>
        </div>
        <img id="DTLLS_0" class="center-frames" src="resources/images/DTLLS_0.jpg"/>
        <img id="DTLLS_1" class="center-frames" src="resources/images/DTLLS_1.jpg"/>
        <div id="GraduanThrowHats" class="center-frames" style="width:100%;height:715.46px;background:linear-gradient(217deg, rgba(178,243,255,0.8), rgba(255,255,255,0) 70.71%),linear-gradient(127deg, rgba(171,194,255,0.8), rgba(0,255,217,0) 70.71%),linear-gradient(336deg, rgba(0,0,255,.8), rgba(0,0,255,0) 70.71%);">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1805.6 845.04">
                <defs>
                    <style>.cls-1 {
                        fill: #010101;
                        fill-rule: evenodd;
                    }</style>
                </defs>
                <g id="Peoples">
                    <path id="ppls0"
                          d="M95,1382.05c-.07-.25,1.09-.77,1.3-.87,2.51-1.15,21.33-12.81,24.57-31.39a31.35,31.35,0,0,0,.34-8.51c-1.15-11.28-7.77-12.7-9.53-20.43-3-13.39,14.33-20.18,15-46,0-.3,0,0,0-2.89,0-30,1.14-38.56-3.24-40.85-1.82-1-3.74-.38-5-.09-16.68,3.81-37.78-14.92-41.1-17.87-5.6-5-12.14-12.6-28.34-63.57-4.4-13.84-16.86-29.75-12.68-35.43a4.85,4.85,0,0,1,1.7-1.34c16-9.3,45.68-22,45.68-22l2.15-.66c.07.48.19,1.19.34,2a225.45,225.45,0,0,0,9,35.06c5.56,16.32,8.34,24.49,12.42,28.59,0,0,1.73,1.74,17.88,13.28,10.79,2.61,14.7,1.16,16.17-.85,1.2-1.64,1.08-4.1,3.4-5.45,1.39-.8,3.49-1.11,4.6-.17s.37,2.17,1.19,3.24c1.43,1.86,6,1.59,9-.34,3.24-2,5.43-6.37,4.26-9.28-.25-.62-.61-1.06-3.41-3.32-2.44-2-3.66-3-5.53-4.25-4.44-3.11-8.34-19.2-.94-30.13,8.81-13,31.55-15.67,42.81-3.75,9.55,10.11,8.7,28.42,2,33.45-2.46,1.84-5.91,2.06-8,5.53-1.87,3.12-1.42,6.8-.85,9.19,0,0,.45.82,5.27,5.79l15.15.51.68-3.74,12.26.17c0,.64.1,1.61.13,2.8,0,.7,0,.71,0,.77.84,2.16,12.43-.08,12.43-.08s-9.7-34.24-14.05-51.07c-4.48-17.34-18.88-103.88-14.55-78.64,8.08-1.89,14.78-3.58,19.66-4.85,10.95-2.83,23.74-6.38,23.74-6.38A173.67,173.67,0,0,1,262.13,1070c1.69,12.48,1.49,22.07,8.42,32.17,2.78,4,10.86,14.22,10.73,14l8.68-.51c.05-1.4.13-3.41.25-6.3v-.08c.12-3.61-6.87-6.25-9.95-9.19-6.19-5.9-3.69-19.66.51-27.83a28.66,28.66,0,0,1,13-13.28c1.24-.6,12.55-5.83,23.74,0a26.9,26.9,0,0,1,11.24,11.74c4.54,8.46,5.88,20.5.76,28.6-2.16,3.43-10.22,12.59-7.66,9.45-.61,2.61-.12,4,.51,4.85,2.39,3.12,10.22,2.12,10.22,2.12,1.14-3.63,3.24-8,7.31-9.7a10.17,10.17,0,0,1,5.45-.51c14.6,2,58.26-76.49,59.24-78.47l38.46,19.24a305.74,305.74,0,0,1-15.49,37.79s-8.37,17.06-40.34,65.7c-.57,12.34-1.12,30.88-.51,53.44.57,21.14,1.78,31.9,3.07,50h0c0,42.93,3.06,128.76,3.06,128.77l-283.66,0h0C387.17,1381,98,1382,98,1382,96.68,1382.1,95.06,1382.34,95,1382.05Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl8"
                          d="M406.13,1252.26c-1,.18-9,3.27-13,6.38-5,3.85-22.5,22.21-44.43,49,0,0-19.06,33.31-22.2,74.21v.18H527.66l25.53-178.82a182.55,182.55,0,0,0,33.19-38.8s10.38-16.4,32.34-77.11l-29.44-21.45-6.13,2.39s-46,66.7-49.36,71.14l-2,2.73-10.21-1.51s.81-3.65-.42-5.51c-1.54-2.33-6.73-2.6-8.26-.6-.77,1-.05,1.85-.76,3-1.63,2.54-8.11,2.6-9.58,0a3.92,3.92,0,0,1,0-3.06c.72-2.42,3.59-12.13,9.45-12.77,0,0,2.45-.27,13.53,9.19a8.45,8.45,0,0,0,2-2.42c1-2.33-1.46-6.37-4.47-8.08-.61-.35-1-.49-1-.61.17-.67,14.43,2.3,14.43,2.3l-12.38-7.66s-12.62-4.09-18-5.36a2.58,2.58,0,0,1-1.54-.89c-.94-1.26-.6-4,.64-4.73,3.89-2.34,18.62,13.33,19.34,14.49,0,0,0,.07.07.07.27-.07.28-8-3.2-12.51-2.4-3.16-4.81-2.52-12.89-5.75-5.84-2.33-15.74-7.13-15.19-9.19.35-1.31,5.09-2.2,8.42-.25,5.91,3.43,6.55,15.21,6.64,15.57,0-.27,2.33-9.53.64-14.94-2.85-9.13-18.51-11.81-25.53-13-8.81-1.51-20-3.42-31.15,3.19a37.3,37.3,0,0,0-15.57,18.9,35.37,35.37,0,0,0-1.54,20.42s1.66,6.87,17.11,25.79l.32,10.28-3.32-.07c-5.84-9-6.7-9.64-6.7-9.64-8.45-6.4-27.62,2.94-27.64,2.94a7.31,7.31,0,0,0-3,3.38,5.62,5.62,0,0,0-.2,3v0c-.1,1.59-53.17-.32-53.17-.32l-1.53,31.15c22.38,7.58,25.27,10.47,25.27,10.47,8.12,8.12,1.3,14.52,10.47,28.85,0,0,4.09,6.4,15.77,18.07l-1.09,7.72Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl7"
                          d="M490.89,1382.05c.19.22.65.11.71.1,1.43-.27,76.75-.28,197.93-.1,1.26-3.5,23.18-66.63-.51-103.75-4.91-7.71-8-8.42-29.53-32.68,0,0-9.37-10.58-21.62-15.41-1.94-.76-3.56-1.4-4.59-1.19a2,2,0,0,1-1.51-.13c-.26-.17-.5-.48-.55-.44s0,.26.1.25.23,0-.34-15.68a38.32,38.32,0,0,0,13.79-16.42c4.32-10.13,5.81-26.65-5.11-37.79-10.56-10.78-25.34-9-26.38-8.85a32.19,32.19,0,0,0-22.64,15c-4.73,7.59-4.75,15-4.77,22.8,0,9.27,2.21,18.13,4.6,23.32.32.71,3.4,7.32,3.4,7.32l.68,10.39c2.9,3-5.81-5.94-8.68-8.94-13.82-14.44-22.21-63.06-22.21-63.06l-53.36,17.1s5.14,32.31,19.66,61c11.8,23.35,30.12,44.94,30.13,44.94s-25,10.42-39.58,24.51c0,0-11.13,10.79-27.91,74C492.6,1378.38,490.33,1381.39,490.89,1382.05Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl6"
                          d="M625.19,1092.17c-.33-3.23-.5-4.85-.5-4.85a.24.24,0,0,1,0-.13c.13-.31,1.73.09,1.92.13,3.47.79,45.06-3.06,45.06-3.06a183.13,183.13,0,0,0,3.83,27.06c3.86,17.66,7,19.54,11.49,37,0,0,1.57,6.13,7.15,45.19,2.33-.66,5.52-1.13,7.91.51,3,2.06,1.65,5.32,5.11,8.68,0,0,.92.9,8.68,4.47,0-10,0-16.38,0-16.38-5.55-2.37-6.34-3-6.34-3-3.81-2.92-5.33-9.93-2.89-12.68s8.85-2,8.85-2c-.61,11.58.11-14.56,1.62-18.9,4-11.45,16.86-16.24,17.49-16.47,14.44-5.13,27.18,3.43,31,6,4.17,2.81,7.38,5,9.32,9.2,3.43,7.49-6.42,41.91-3.07,28.34a8.09,8.09,0,0,1,3.7-1.66,3.75,3.75,0,0,1,3.32,1.4c1.31,2.15-1.3,6.81-4.59,8.3-1.12.5-3.7,1.28-3.7,1.28a64.81,64.81,0,0,1-4,9.31c-4.13,7.27-11.07,12-12.64,12.39a1.81,1.81,0,0,0-1.15.64,3.12,3.12,0,0,0-.38,1.53,66.45,66.45,0,0,1,6.76,1c8.42,2.18,13.15,15.7,13.15,15.7l44.3-.21,15,16.68L782,1266.38s5.94,17.51,8.51,26.22c0,0,11.57,39.19,5.57,89.11,0,0,0,.12,0,.27v.07c-.1.81-145,0-145,0h-1c-.62-.09,8.63-54.31,9.19-93.28a242.09,242.09,0,0,0-4.64-53.89c-8.39-41.13-19.34-37-23.7-70.62C628.35,1145.32,625.51,1095.26,625.19,1092.17Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl5"
                          d="M791.66,1158.13c0-4.56,0-8.29,0-10.73-23.63-17.78-36.49-35.31-43.92-48.34-4.19-7.36-4.63-9.74-10-18.12-14.79-23.33-34.47-41.36-34.47-41.37l48-34.21c13.1,15.57,22.8,28.85,29.36,38.3,8.67,12.49,20.17,23.36,26.3,37.28,1.55,3.53,4.92,12,12.25,15.57,1.89.93,8.68,3.83,8.68,3.83-.21,5,1.11,7.27,2.56,8.43,3.47,2.77,10.9,1.53,11,1.53a59,59,0,0,1-12.51-20,67.18,67.18,0,0,1-3.07-12.64c-3.66-21.3-5.49-31.94-.25-40.6,4.72-7.81,12.49-11,15.83-12.38,3.09-1.27,15.58-6.48,27.57-.26a30.07,30.07,0,0,1,12.26,12.39,34.69,34.69,0,0,1,3.83,12.76c1.33,9.7-.57,19.32-.64,20.17a5.93,5.93,0,0,1,2.68-1.66c1.45-.4,3.75-.4,4.47.64,0,0,1.16,1.7-10.22,15.83l-2.93-1.15c1,3.3.53,5.35-.13,6.64a22,22,0,0,1-3.06,4l1.15,9.32,3.44-.9h0a42.84,42.84,0,0,1-.75,6.91.21.21,0,0,0,0,.11c.2,1.08,10,.11,12.28-.11h.1c16.33-1.63,100.82-90.87,100.85-90.9h0l32.17,28.34h0s-15.33,30-37.28,54.13c-22.54,24.79-52.08,43.41-52.08,43.41h0v52.85c0,82.23-2.81,184.92-2.81,184.94h0s-141.21-2-150.38,0a.46.46,0,0,1-.26,0c-3.24-1.29,27.9-50.78,21-102.39-3.54-26.61-13.12-23.27-14.63-49.36C787,1211.51,791.29,1198.06,791.66,1158.13Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl4"
                          d="M979.27,1115.52a.29.29,0,0,0,0,.23,3,3,0,0,1,0,.67c0,.57,0,1.13,0,1.7,0,1.28,0,28.88-.07,31.88-.12,12.18-4.56,105-13.91,232h170.55q8.18-68.47,16.34-136.94a220.45,220.45,0,0,0,4.6-24c1.79-13.5,2.74-30.36-3.16-104.29l0-.27q-3.16.2-6.37.35c-14,.67-27.54.63-40.5,0a52.25,52.25,0,0,1,5.11,20.17c.67,26.62-22.47,52.84-22.47,52.85l-9.7.76c-.06-3.12-.11-6.24-.17-9.36a40.58,40.58,0,0,0,9-12.68c6.67-14.86,5-36.41-6.81-43.91-4.32-2.74-8.88-2.89-14.3-3.07-4.71-.15-14.35-.47-22.46,6.13a29,29,0,0,0-8.68,12.6c-.94,2.35-6.16,15.52,0,24,3.17,4.36,5.81,2.6,9,7.31,4.9,7.23,3.57,18.56,3.57,18.56a17.18,17.18,0,0,1-10.21.68c-3.79-1-18.57-16.2-15.32-12.77,2-41,3-62.3,3-62.39s0-.08,0-.18v-.07c0-1-14.68-.68-14.68-.68-10,.23-9.65.51-16.64.56-3.82,0-10.27,0-12.1,0a10.26,10.26,0,0,1-3.08,0C979.79,1115.49,979.38,1115.36,979.27,1115.52Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl3"
                          d="M1146.94,1061.91c.07-.2.53-.21.59-.21.88,0,20.12-2.62,47.92-6.42,3.09,11.1,5.23,19.61,6.64,25.53.52,2.23,3,12.64,6.12,25,3.5,13.77,4.25,15.81,6.26,18.51,0,0,2,2.71,15.06,13l6.77.26a26.7,26.7,0,0,1,.64-15.58c5.92-15.91,26.91-18.72,30.12-19.15,5.12-.68,21.55-2.87,31.92,8.17,11.3,12,8.8,31.9,1,43.92-4.56,7-15.48,18.44-25.53,17.11-2.11-.29-5.3-1.27-7.92.51s-3.06,5.29-3.57,9.44c-.49,4-1.34,10.94,2.55,14,1.35,1.07,2.18.82,4.34,1.53,7.91,2.59,14.15,11.7,13,18.12-.14.8-.56,3.2-2.29,4.09s-3.06-.47-4.86.26c-2.07.84-3,3.76-3.06,5.61-.21,6.09,7.33,9.19,7.92,9.19h.63s1,18.55,2.78,53.58c0,0,0,.66,4.84,93.58H1171.14S1182.3,1190,1182.3,1190s-9.38-17.53-11.58-21.79c-20.54-39.83-23.17-101.74-23-103.49a2.61,2.61,0,0,0-.25-1.91C1147.24,1062.39,1146.85,1062.13,1146.94,1061.91Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl2"
                          d="M1346.16,1046.53a.18.18,0,0,0-.16,0c-.68.18-41.68,18.81-47.28,19-.3,0-1.68,0-2.21.85s.19,2.43.34,2.73c1.8,3.63,1.11,18.9,12.26,52.59l21.61,53.11a20.91,20.91,0,0,1-1.68,10.81c-1.87,4-4.47,5.77-8.1,8.93-4.57,4-12.62,11-16.09,19.15-2.75,6.49-2.07,12.4-1.79,15.58,3.1,35-6.12,152.76-6.12,152.77h108q5.36-62.47,10.72-124.94a18.68,18.68,0,0,1,.34-4.94s1.7-8.32,11.74-15.4c0,0,30-29.78,126.56-37.37h0c1.5-.57-15.25-43.66-15.25-43.66l-95,10.22,1.36-5.45s13-5.49,17.7-12.94c5.68-8.94,3-26.31-8.17-34.72-12.22-9.18-29-3.46-36.77,1.7-6.16,4.08-15,13.28-15,13.28s-4.11-3.13-6.63-2.38c-3.06.9-3.93,7.54-3.92,11.06a50.94,50.94,0,0,0,1,8.51l-6.47,8.34s-5.24.3-6.46.17c-6.32-.65-7.92-23.22-13.62-44.76-1.94-7.31-1.18-2.54-11.75-34-3.74-11.12-9.25-27.83-9.25-27.83S1346.27,1046.62,1346.16,1046.53Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl1"
                          d="M1438.13,1049.53c.81.37,60.37-9.91,62.81-11.23a2,2,0,0,1,1.08-.26.86.86,0,0,1,.89,1.28c-.68,2.46.33,54.8.58,58,0,0,.17,2.12.17,2.12,9.85,6.65,13.59,12.31,15.15,16.34.52,1.36,3.23,8.86,3.23,8.86a53.75,53.75,0,0,1,15.83,3.4c8.62,3.28,17.07,9.09,19.07,12.41.09.15.44.76.68.7.9-.26-1-10.39-1-10.39a50.34,50.34,0,0,1-9.88-21.27c-1.13-5.74-4.54-23.07,6.47-34.22,11.26-11.39,30.13-8.76,40.85-3.4,3.47,1.73,12.73,6.36,15.15,15.15,0,0,.6,2.17.51,16.17l2.9-.85s1.25,1.06,1.53,1.36c1.45,1.58-.19,8.07-4.94,10.72-1.62.91-7.27,1.56-5.45,1.19l-.51,15.15,17.2,1.19a69.85,69.85,0,0,0,20.25-10s5.64-4.07,22.47-22.47a244,244,0,0,0,6.3-36.42c1.1-12.68,2-22.47.53-26.49a.61.61,0,0,1,0-.4s.8-2.57,62.13,10.72c-7.51,19.86-14,36.64-19.07,49.53-8,20.35-9.55,23.92-12.93,29.28,0,0-5.28,8.34-30,34.55-1.89,57.84-4.59,104-6.81,136.51-2.47,38.07-6.14,85.37-6.13,85.37,35,2.71-164.42,0-164.42,0s4.68-72.3-1.79-117.28c-.86-6-2.49-15.45.51-27.07,2.85-11,10.06-24.75,10-24.51,0,0-19.83-27.9-32.17-58.47-4.24-10.48-.53-3.78-14.81-52.59-11.08-37.87-15.68-50-16-50.56a13.35,13.35,0,0,1-.51-1.48c-.06-.18-.16-.5,0-.58S1438.12,1049.53,1438.13,1049.53Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl0"
                          d="M1641.36,1265c1.55-7.71,12.77-20.39,12.77-20.39,3.16-3.57,7.25-8,12.25-12.8,0,0,3.18-2.74,25.53-18.89a162.5,162.5,0,0,1-7.14-16.34c-6.46-17.31-10-26.75-7.66-37.79,2.08-9.93,9.54-24.26,23.49-27.58,10.7-2.54,19.57,2.74,20.93,3.58,19.19,11.83,16.9,43.63,9.7,50-.71.64-6.63,5.62-6.63,5.62l1.1,6.3c3.5,1.31,5.26.82,6.21.17s1.17-1.64,2.39-3.75a22.41,22.41,0,0,1,3.74-4.93c3-2.64,7.37-.68,11.41-.69,10.69,0,18.79-13.87,20.42-16.68,3.93-6.72,2.64-9.16,5.79-25,0,0,.7-3.54,10.89-39.49l54.47,12.94h0s-5.33,36.5-15.66,70.47c-11.8,38.84-30.29,74.89-30.3,74.89h0l2.81,117.37H1638.3l2.55-114.48h0Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Static" class="cls-1"
                          d="M1503.31,1382.05c-15.78,0-32-.11-49.74,0-15.45.09-36,0-50.55,0-1.19,0,2.52-9,2.92-10.12l1.81-3.23-7.27,1.13-2.59-1.91c-2.52,1.18-5.07,2.89-8,3.62l-6.78.73-3.22,0a20.05,20.05,0,0,1-5.47,0l-6.2-.3-5-3.61-4.06-2.68-1.56-6.25c-.18-.78-.36-1.56-.53-2.35q1.21-3.65,2.44-7.31c.48-1.78,1-3.55,1.46-5.33,0-.74.07-1.49.1-2.24v-3.22c0-1.09,0-2.18-.05-3.27a30.12,30.12,0,0,1-1-6.15c0-1.37,0-2.74,0-4.1l1.75-2.25c2.22-3,5.35-5.25,8.3-7.51l2.88-2.25q2.73-5.64,5.47-11.27c.66-.61,1.33-1.21,2-1.81l.78,0,8.54-14.93c.07-.94.13-1.89.19-2.83.36-2.2.07-4.75.44-7.08,0-1,0-1.92.05-2.88.25-1.41,2.79-6.77,3.66-7.52l7.18-2.63,2,.15c1.53-.55,4.31-3,5.85-.93l-.68,1,9.91-2.44,37.87-7.08,4.64-.14,4-.15c4-.63,7.86.13,11.62.25a5.73,5.73,0,0,1-.49-2.39l2.39-.1-.19-.64h.53l2.35.05,2.92,0c1.52-.37,3.06-1.48,4.69-1.76l2.39.44,1.81.3,1.17,1.17a18.08,18.08,0,0,1,4,5l1.08,1.61c.86,3.39,1.72,6.8,2.58,10.2l3.18,4.78,3.61,7,8.44,10.69,2.49,2.1.88,1.9c1,1.94,1.89,4.05,3,5.86,2.15,3.4,4.42,6.57,6.5,10.15.57,1,1.14,2.08,1.7,3.12l.15,3.56q2.46,5.87,4.93,11.72l2.34,10.2c.15,2.73.3,5.47.44,8.2.33,3.12.65,6.25,1,9.37l-3.47,1.37c-2.52,1-5.09,1.89-7.42,3.07l-3.66,1.91-6.19-.93c-2.19-.44-4.51-.25-6.89-.64l-2.63-.19-6.35,3.17c-.1.88-.19,1.76-.29,2.64l.39,5.9C1503.75,1373.55,1503.41,1380.57,1503.31,1382.05Zm-24.59-126.92-14.74,2.25c.41,3.77,1.11,7.35,1.85,10.93.12.6-.24.94-.15,1.46l1.32,4c1.37,4.34,2.9,8.18,4.54,12.16,2.26,5.48,4.52,11.18,7.76,15.71q2.34,3.25,4.69,6.49c.93,1.31,1.44,2.69,3.46,2.93,1-2.45,2-4.91,3.08-7.37l3.75-3.66c2.85-3.57,5.89-6.88,9-10.15-.94-2.25-1.8-4.52-2.73-6.64-.37-.84-.75-1.69-1.12-2.54-2.14-3-4.65-5.74-6.93-8.59l-4.1-4.48-1.76-4.11-.83-.73a37,37,0,0,0-4.59-3.76c-1.17-.77-2.24-1-3.07-2.14C1478.33,1256.52,1478.89,1255.37,1478.72,1255.13Zm-62.48,51-.54-.05-.24-1.31-.44,0v0c.16.49.33,1,.49,1.46h-.59c-.31-1.92-.82-3.91-1.17-6,0-1,0-2,0-2.93a46.13,46.13,0,0,1,1.76-12.25c.16-1.43.32-2.87.49-4.3l.63-.19q.42-8.76.83-17.52l-9,2.29c0,2-.42,2-.93,3.12l-2.34,6.84c0,.79.07,1.59.1,2.39-.41.84-.82,1.69-1.22,2.54-.1.65-.2,1.3-.29,2a30.05,30.05,0,0,1-2.84,5c-2.86,4.77-5.79,9-8.1,14.34-.5,1.18-1,2.35-1.51,3.52l2.78.93,7.23,16.25,10.15.34a24.57,24.57,0,0,1,4-4.39L1418,1316l2.49-5,3-15.22,2.34-11.43,2.58-9.46h0l-.49.09-3-13.56-6.69,1.61q-.56,8.88-1.12,17.76h0l.73-.14a41,41,0,0,0,.15,7.12c0,1.42.06,2.83.1,4.25.82,3.85,3.58,8.4,2.49,13l-.93-.83-.1,0-.63,1.51h-.05v-.09c-.12-.33-.23-.66-.34-1h0c-.08.36-.17.72-.25,1.07l-.19-.19-.78-.59-.1,0-.39.93h0a1.9,1.9,0,0,0-.39-1.42C1416.27,1305.06,1416.26,1305.6,1416.24,1306.13Zm-12.35-38.31c-.85,2.67-3.31,4-3.22,7.42h0l1.42-.2,2.19-7Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Static-2" data-name="Static" class="cls-1"
                          d="M1108.3,1372.26l.39-5.9c-.1-.88-.19-1.76-.29-2.64l-6.35-3.17-2.63.2c-2.37.38-4.7.2-6.88.63l-6.2.93-3.66-1.9c-2.33-1.19-4.89-2.07-7.42-3.08l-3.47-1.37c.33-3.12.65-6.24,1-9.37.15-2.73.29-5.46.44-8.2l2.34-10.2,4.93-11.71.15-3.57,1.71-3.12c2.07-3.57,4.34-6.74,6.49-10.15,1.13-1.81,2-3.92,3-5.86.3-.63.59-1.27.88-1.9l2.49-2.1,8.45-10.69,3.61-7,3.17-4.78q1.29-5.1,2.59-10.2c.35-.54.71-1.08,1.07-1.61a18.26,18.26,0,0,1,4-5l1.18-1.17,1.8-.29,2.39-.44c1.63.27,3.17,1.39,4.69,1.75l2.92-.05,2.35,0h.54c-.07.21-.13.42-.2.63l2.39.1a5.73,5.73,0,0,1-.49,2.39c3.76-.12,7.66-.87,11.62-.24l4,.14,4.64.15,37.87,7.07,9.91,2.45-.68-1c1.54-2,4.32.39,5.85.93l2.05-.15,7.18,2.64c.87.74,3.41,6.1,3.66,7.51,0,1,0,1.92,0,2.88.38,2.33.08,4.88.44,7.08.06.94.13,1.89.19,2.83l8.54,14.93.78.05,2,1.81,5.46,11.28,2.88,2.24c3,2.26,6.08,4.51,8.3,7.51l1.76,2.25c0,1.37,0,2.73-.05,4.1a29.46,29.46,0,0,1-1,6.15c0,1.09,0,2.18,0,3.27v3.22c0,.75.07,1.5.1,2.25l1.47,5.32q1.22,3.66,2.44,7.32l-.54,2.34-1.56,6.25-4.05,2.68-5,3.61-6.2.3a19.67,19.67,0,0,1-5.47,0l-3.22,0-6.78-.73c-2.89-.72-5.44-2.44-8-3.61l-2.59,1.9-7.27-1.12c.6,1.07,1.21,2.14,1.81,3.22.41,1.12,2.09,2.55,1.22,3.37-10.75,10.12-33.56,7.88-49,7.79a208,208,0,0,1-49.82-6.57C1108.5,1375.23,1108.4,1373.75,1108.3,1372.26ZM1134,1257.08c-.83,1.1-1.9,1.37-3.07,2.15a36,36,0,0,0-4.59,3.76l-.83.73c-.59,1.36-1.17,2.73-1.76,4.1l-4.1,4.49c-2.28,2.84-4.79,5.61-6.93,8.59-.37.84-.74,1.69-1.12,2.53-.93,2.13-1.79,4.39-2.73,6.64,3.14,3.28,6.18,6.58,9,10.16l3.76,3.66q1.53,3.67,3.07,7.37c2-.25,2.53-1.63,3.47-2.93l4.68-6.5c3.24-4.53,5.5-10.23,7.76-15.71,1.64-4,3.17-7.82,4.54-12.15l1.32-4c.09-.51-.27-.86-.15-1.46.74-3.58,1.44-7.16,1.86-10.93l-14.74-2.25C1133.27,1255.57,1133.82,1256.71,1134,1257.08Zm61.89,47.64a1.91,1.91,0,0,0-.39,1.41h0l-.39-.93-.1,0-.78.59-.19.2-.24-1.08h-.06c-.11.33-.22.65-.34,1v.1h0l-.63-1.52-.1-.05-.92.83c-1.09-4.58,1.66-9.13,2.48-13,0-1.41.07-2.83.1-4.25a41,41,0,0,0,.15-7.12l.73.14h.05q-.56-8.88-1.12-17.76l-6.69-1.61-3,13.57-.48-.1h0l2.58,9.47q1.19,5.7,2.35,11.42,1.51,7.61,3,15.23l2.49,5,2.44,2.15a25.36,25.36,0,0,1,4,4.39l10.15-.34,7.22-16.25,2.78-.93-1.51-3.51c-2.3-5.37-5.24-9.58-8.1-14.35a28.94,28.94,0,0,1-2.83-5l-.3-1.95c-.4-.85-.81-1.69-1.22-2.54,0-.8.07-1.59.1-2.39l-2.34-6.83c-.51-1.18-1-1.12-.93-3.13l-9-2.29q.42,8.76.83,17.52l.64.2.48,4.29a46.13,46.13,0,0,1,1.76,12.25c0,1,0,2,.05,2.93-.35,2.1-.86,4.08-1.17,6h-.59c.16-.48.33-1,.49-1.46v0l-.44,0-.24,1.32-.54,0C1195.89,1305.79,1195.88,1305.25,1195.86,1304.72Zm12-36.51q1.1,3.51,2.2,7l1.41.19h0c.09-3.39-2.36-4.75-3.22-7.42Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Static-3" data-name="Static" class="cls-1"
                          d="M1002.55,1382.05c-16,.93-36.42.39-53.95,0-15.46.09-33.2,0-48-.4-1.19,0,2.93-43.6,3.33-44.72l1.81-3.23-7.27,1.13-2.59-1.91c-2.52,1.18-5.07,2.89-8,3.62l-6.78.73-3.22,0a20.05,20.05,0,0,1-5.47,0l-6.2-.3-5-3.61-4.06-2.68-1.56-6.25c-.18-.78-.36-1.56-.53-2.35q1.21-3.65,2.44-7.31c.48-1.78,1-3.55,1.46-5.33,0-.74.07-1.49.1-2.24v-3.22c0-1.09,0-2.18,0-3.27a30.12,30.12,0,0,1-1-6.15c0-1.37,0-2.74,0-4.1l1.75-2.25c2.22-3,5.35-5.25,8.3-7.51l2.88-2.25q2.73-5.64,5.47-11.27c.66-.61,1.33-1.21,2-1.81l.78,0,8.54-14.93c.07-.94.13-1.89.19-2.83.36-2.2.07-4.75.44-7.08,0-1,0-1.92,0-2.88.25-1.41,2.79-6.77,3.66-7.52l7.18-2.63,2,.15c1.53-.55,4.31-3,5.85-.93l-.68,1,9.91-2.44,37.87-7.08,4.64-.14,4-.15c4-.63,7.86.13,11.62.25a5.73,5.73,0,0,1-.49-2.39l2.39-.1-.19-.64h.53l2.35.05,2.92,0c1.52-.37,3.06-1.48,4.69-1.76l2.39.44,1.81.3,1.17,1.17a18.08,18.08,0,0,1,3.95,5l1.08,1.61c.86,3.39,1.72,6.8,2.58,10.2l3.18,4.78,3.61,7,8.44,10.69,2.49,2.1.88,1.9c1,1.94,1.89,4.05,3,5.86,2.15,3.4,4.42,6.57,6.5,10.15.57,1,1.14,2.08,1.7,3.12l.15,3.56q2.46,5.87,4.93,11.72l2.34,10.2c.15,2.73.3,5.47.44,8.2.33,3.12.65,6.25,1,9.37l-3.47,1.37c-2.52,1-5.09,1.89-7.42,3.07l-3.66,1.91-6.19-.93c-2.19-.44-4.51-.25-6.89-.64l-2.63-.19-6.35,3.17c-.1.88-.19,1.76-.29,2.64l.39,5.9C1001.73,1338.55,1002.65,1380.57,1002.55,1382.05ZM976.7,1220.13,962,1222.38c.41,3.77,1.11,7.35,1.85,10.93.12.6-.24.94-.15,1.46l1.32,4c1.37,4.34,2.9,8.18,4.54,12.16,2.26,5.48,4.52,11.18,7.76,15.71q2.34,3.25,4.69,6.49c.93,1.31,1.44,2.69,3.46,2.93,1-2.45,2.05-4.91,3.08-7.37l3.75-3.66c2.85-3.57,5.89-6.88,9-10.15-.94-2.25-1.8-4.52-2.73-6.64-.37-.84-.75-1.69-1.12-2.54-2.14-3-4.65-5.74-6.93-8.59l-4.1-4.48-1.76-4.11-.83-.73a37,37,0,0,0-4.59-3.76c-1.17-.77-2.24-1-3.07-2.14C976.31,1221.52,976.87,1220.37,976.7,1220.13Zm-62.48,51-.54-.05-.24-1.31-.44,0v0c.16.49.33,1,.49,1.46h-.59c-.31-1.92-.82-3.91-1.17-6,0-1,0-2,0-2.93a46.13,46.13,0,0,1,1.76-12.25c.16-1.43.32-2.87.49-4.3l.63-.19q.42-8.76.83-17.52l-9,2.29c0,2-.42,2-.93,3.12l-2.34,6.84c0,.79.07,1.59.1,2.39-.41.84-.82,1.69-1.22,2.54-.1.65-.2,1.3-.29,2a30.05,30.05,0,0,1-2.84,5c-2.86,4.77-5.79,9-8.1,14.34-.5,1.18-1,2.35-1.51,3.52l2.78.93,7.23,16.25,10.15.34a24.57,24.57,0,0,1,4-4.39l2.44-2.15,2.49-5,3-15.22,2.34-11.43,2.58-9.46h0l-.49.09-3-13.56-6.69,1.61q-.55,8.88-1.12,17.76h0l.73-.14a41,41,0,0,0,.15,7.12c0,1.42.06,2.83.1,4.25.82,3.85,3.58,8.4,2.49,13l-.93-.83-.1,0-.63,1.51h-.05v-.09c-.12-.33-.23-.66-.34-1h-.05c-.08.36-.17.72-.25,1.07l-.19-.19-.78-.59-.1,0-.39.93h-.05a1.9,1.9,0,0,0-.39-1.42C914.25,1270.06,914.24,1270.6,914.22,1271.13Zm-12.35-38.31c-.85,2.67-3.31,4-3.22,7.42h.05l1.42-.2,2.19-7Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Static-4" data-name="Static" class="cls-1"
                          d="M1373.79,1382.05c-15.78,0-38.11-.11-55.82,0-15.46.09-38.4,0-53,0-1.19,0,9.73-69.14,10.14-70.26l1.81-3.22-7.27,1.12-2.59-1.9c-2.52,1.17-5.07,2.89-8,3.61l-6.78.73-3.22,0a19.29,19.29,0,0,1-5.47,0l-6.2-.29-5-3.62-4-2.68-1.56-6.25-.54-2.34q1.23-3.66,2.44-7.32l1.47-5.32c0-.75.06-1.5.1-2.25v-3.22c0-1.09,0-2.18,0-3.27a29.47,29.47,0,0,1-1-6.14c0-1.37,0-2.74,0-4.11.59-.74,1.18-1.49,1.76-2.24,2.22-3,5.35-5.25,8.3-7.52l2.88-2.24,5.46-11.28,2-1.8.78,0q4.26-7.47,8.54-14.94c.06-.94.13-1.88.19-2.83.36-2.2.06-4.74.44-7.07,0-1,0-1.92.05-2.89.25-1.41,2.79-6.77,3.66-7.51l7.18-2.64,2,.15c1.53-.54,4.31-3,5.85-.93l-.68,1,9.91-2.44,37.87-7.08,4.64-.15,4-.14c4-.63,7.86.12,11.62.24a5.66,5.66,0,0,1-.49-2.39l2.39-.1c-.06-.21-.13-.42-.19-.63h.53l2.35,0,2.92,0c1.52-.37,3.06-1.49,4.69-1.76l2.39.44,1.8.29,1.18,1.17a18.42,18.42,0,0,1,4,5c.36.54.72,1.07,1.07,1.61q1.31,5.1,2.59,10.2c1.06,1.6,2.12,3.19,3.17,4.79,1.21,2.32,2.41,4.65,3.61,7l8.45,10.69,2.49,2.1c.29.64.58,1.27.88,1.9,1,2,1.89,4.06,3,5.86,2.15,3.41,4.42,6.58,6.5,10.15.56,1,1.13,2.09,1.7,3.13l.15,3.56,4.93,11.71,2.34,10.2c.15,2.74.29,5.47.44,8.21.33,3.12.65,6.24,1,9.37l-3.47,1.36c-2.53,1-5.09,1.89-7.42,3.08L1395,1302l-6.2-.93c-2.18-.43-4.51-.24-6.88-.63l-2.63-.2-6.35,3.18c-.1.87-.19,1.75-.29,2.63l.39,5.91C1373,1313.42,1373.88,1380.57,1373.79,1382.05Zm-25.86-187-14.74,2.24c.42,3.77,1.12,7.36,1.86,10.93.12.61-.24.95-.15,1.47l1.32,4c1.37,4.33,2.9,8.18,4.54,12.15,2.26,5.49,4.52,11.18,7.76,15.72l4.68,6.49c.94,1.31,1.45,2.68,3.47,2.93q1.55-3.69,3.07-7.37l3.76-3.66c2.85-3.57,5.89-6.88,9-10.15-.94-2.25-1.8-4.52-2.73-6.64-.38-.85-.75-1.69-1.12-2.54-2.14-3-4.65-5.75-6.93-8.59-1.37-1.5-2.74-3-4.1-4.49-.59-1.37-1.17-2.74-1.76-4.1l-.83-.73a37.79,37.79,0,0,0-4.59-3.76c-1.17-.78-2.24-1-3.07-2.15C1347.55,1196.38,1348.1,1195.24,1347.93,1195Zm-62.47,51-.54,0-.24-1.32-.44-.05v.05l.49,1.47h-.59c-.31-1.93-.82-3.91-1.17-6,0-1,0-1.95,0-2.93a46.13,46.13,0,0,1,1.76-12.25l.48-4.29.64-.2q.42-8.76.83-17.52l-9,2.3c0,2-.42,1.94-.93,3.12l-2.34,6.83c0,.8.07,1.6.1,2.39l-1.22,2.54-.3,2a28.58,28.58,0,0,1-2.83,5c-2.86,4.78-5.8,9-8.1,14.35l-1.51,3.51,2.78.93,7.22,16.25,10.15.35a24.65,24.65,0,0,1,4-4.39c.81-.72,1.62-1.44,2.44-2.15l2.49-5q1.52-7.62,3-15.23,1.17-5.7,2.35-11.42l2.58-9.47h0l-.48.1-3-13.57-6.69,1.61q-.55,8.88-1.12,17.77h0l.73-.15a41.13,41.13,0,0,0,.15,7.13c0,1.41.06,2.83.1,4.24.82,3.85,3.57,8.41,2.48,13l-.92-.82-.1,0-.63,1.51h0v-.1c-.12-.32-.23-.65-.34-1h0c-.09.36-.17.72-.25,1.08l-.19-.2-.78-.58-.1,0c-.13.32-.26.62-.39.93h0a1.92,1.92,0,0,0-.39-1.41C1285.49,1244.92,1285.48,1245.46,1285.46,1246Zm-12.35-38.31c-.86,2.66-3.31,4-3.22,7.41h0l1.41-.19q1.11-3.53,2.2-7Z"
                          transform="translate(-35.42 -538.51)"/>
                </g>
                <g id="Hands">
                    <path id="ppl8-righthand" class="cls-1"
                          d="M585.4,1109c19.31-45.18,29.63-69.35,29.63-69.35h0c6.47-5.15,7.35-6.57,7.35-6.57a13.83,13.83,0,0,0,1.53-9.95,11.48,11.48,0,0,0-4.72-7.15c-3.91-2.5-8.29-1.34-10.08-.86-4.21,1.12-9.43,4.41-11,9.54-1.34,4.4,1.22,6.25.78,14.64a19.62,19.62,0,0,1-1,7.1c-4.69,14.85-26.86,52.94-26.87,53Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl3-lefthand" class="cls-1"
                          d="M1200.51,1093.68c-11.07-47.86-17-73.47-17-73.47h0c2.18-8,2.06-9.64,2.06-9.64a13.91,13.91,0,0,0-4.64-8.94,11.52,11.52,0,0,0-8-3c-4.64.3-7.48,3.82-8.65,5.26-2.73,3.39-5,9.13-3.24,14.18,1.53,4.34,4.68,4.33,9.28,11.36a19.87,19.87,0,0,1,3.37,6.33c5,14.76,9.55,58.6,9.55,58.61Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppls0-lefthand" class="cls-1"
                          d="M81.11,1152.43c-9.32-48.24-14.3-74-14.3-74h0a27.06,27.06,0,0,1-4.34-8.17c-.7-2.56-.38-4.6.25-8.68.94-6,1.42-9,3.58-10.21,3.35-1.8,8.55,2.12,11.49,4.34,2.24,1.69,12,9.06,10.47,16.08-.81,3.69-4,4.2-5.62,9.71a18.5,18.5,0,0,0-.51,7.15c1.44,15.51,15.06,57.43,15.06,57.44h0Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl5-lefthand" class="cls-1"
                          d="M755.63,1039.94l-41-63.3h0a27.26,27.26,0,0,1-7.09-5.95c-1.6-2.11-2.07-4.12-3-8.14-1.38-5.93-2.08-8.93-.51-10.81,2.44-2.93,8.72-1.24,12.28-.28,2.72.73,14.51,3.91,15.73,11,.64,3.71-2.17,5.4-1.58,11.1a18.68,18.68,0,0,0,2.21,6.82c7.15,13.84,35.47,47.61,35.48,47.62h0Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl2-lefthand" class="cls-1"
                          d="M1335.88,1089.11l-16.73-73.53h0c-.29.15-3.2-3.91-4.6-8a21.18,21.18,0,0,1-.85-9.94c.51-3.28,1.08-6.91,4-9.07,3.22-2.35,7.94-2,11.1-.29,7.09,3.83,7.29,15,7.32,17,.06,3.39-.6,4.31-1.09,12.84a24.62,24.62,0,0,0-.28,7.16c2,15.46,16.94,56.91,16.94,56.92Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl5-righthand" class="cls-1"
                          d="M977.84,1061.36l45.52-60.13h0a27.11,27.11,0,0,0,7.5-5.41c1.76-2,2.38-4,3.61-7.9,1.81-5.81,2.72-8.75,1.3-10.75-2.22-3.09-8.61-1.87-12.23-1.17-2.76.53-14.76,2.83-16.49,9.81-.91,3.66,1.76,5.55.75,11.18a18.51,18.51,0,0,1-2.69,6.64c-8.15,13.28-38.87,44.89-38.88,44.9h0Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl2-righthand" class="cls-1"
                          d="M1692.82,1067.7c-3.34-49-5.13-75.23-5.13-75.23h0a27.43,27.43,0,0,0,2.1-9c0-2.66-.81-4.55-2.47-8.33-2.45-5.57-3.68-8.39-6.07-9-3.7-.88-7.72,4.24-10,7.14-1.73,2.22-9.27,11.83-6,18.23,1.72,3.36,5,3,7.92,7.94a18.54,18.54,0,0,1,2.32,6.78c2.57,15.37.15,59.37.15,59.39h0Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl6-lefthand" class="cls-1"
                          d="M667.84,1024.22c.13.35-.74,1.22-5.52,3.65a5.58,5.58,0,0,1,3.37,2.86A3.76,3.76,0,0,1,666,1032c.2,4.5,7.92,87.6,7.92,87.61l-16.88.59q-2.57-34.71-5.14-69.42a8.72,8.72,0,0,1-3.15-1.39,10.57,10.57,0,0,1-3.74-5.72c-2.49-7.78-3.2-11.26-3.2-11.26-.76-5-1.56-10.91-2.24-17.7a1.22,1.22,0,0,1,.26-.58,1.48,1.48,0,0,1,1.83-.27c.57.38.56,1.29.57,1.73a30.32,30.32,0,0,0,1.45,9.09c.47,1.36.89,2.53,1.83,2.77,1.63.41,3.51-2.3,3.6-2.43,1.62-2.39,1.61-5.38,1.61-8,0-2.39-.32-4.59,1-5.56a1,1,0,0,1,.59-.25c1.31,0,2.61,3.58,3,6.36.76,5.49-1.88,9-.65,9.82.76.53,1.88-.71,5.06-1.93C663.44,1024,667.6,1023.56,667.84,1024.22Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl4-lefthand" class="cls-1"
                          d="M1032.12,1058.42c.07.36-.92,1.1-6,2.8a5.59,5.59,0,0,1,2.92,3.33,3.79,3.79,0,0,1,.07,1.28c-.46,4.48-5,87.82-5,87.82l-16.78-1.88q2.53-34.71,5.08-69.42a8.94,8.94,0,0,1-2.92-1.85,10.62,10.62,0,0,1-2.86-6.2c-1.32-8.07-1.51-11.61-1.51-11.61,0-5,0-11,.37-17.83a1.21,1.21,0,0,1,.34-.54,1.5,1.5,0,0,1,1.86,0c.51.46.36,1.36.3,1.8a30.42,30.42,0,0,0,.11,9.2c.27,1.41.51,2.63,1.4,3,1.55.66,3.82-1.76,3.92-1.87,2-2.13,2.38-5.08,2.76-7.67.35-2.36.36-4.59,1.77-5.36a1,1,0,0,1,.61-.16c1.3.17,2.07,3.92,2,6.73-.05,5.54-3.17,8.6-2.08,9.62.68.64,2-.43,5.29-1.17C1027.79,1057.55,1032,1057.73,1032.12,1058.42Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl1-lefthand" class="cls-1"
                          d="M1479.84,995.58c.14.35-.71,1.25-5.42,3.81a5.54,5.54,0,0,1,3.45,2.76,3.74,3.74,0,0,1,.29,1.25c.32,4.5,10.29,87.36,10.29,87.36l-16.86,1q-3.51-34.62-7-69.25a8.93,8.93,0,0,1-3.2-1.31,10.57,10.57,0,0,1-3.89-5.61c-2.7-7.72-3.5-11.17-3.5-11.17-.9-4.94-1.86-10.86-2.72-17.63a1.19,1.19,0,0,1,.24-.59,1.5,1.5,0,0,1,1.83-.33c.58.37.59,1.28.61,1.73a30.45,30.45,0,0,0,1.7,9c.5,1.34,1,2.5,1.9,2.72,1.64.37,3.45-2.4,3.53-2.53,1.56-2.43,1.47-5.42,1.4-8-.07-2.39-.44-4.58.81-5.58a1,1,0,0,1,.58-.27c1.31,0,2.71,3.51,3.17,6.28.91,5.46-1.64,9-.39,9.83.78.51,1.87-.76,5-2.07C1475.43,995.48,1479.58,994.93,1479.84,995.58Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl4-righthand" class="cls-1"
                          d="M1121,1064c-.1.36.83,1.17,5.77,3.26a5.54,5.54,0,0,0-3.17,3.09,4,4,0,0,0-.17,1.27c.12,4.5-1.75,87.94-1.75,87.95l16.88-.6q.13-34.8.25-69.6a8.9,8.9,0,0,0,3.06-1.61,10.67,10.67,0,0,0,3.33-6c1.93-7.94,2.39-11.46,2.39-11.46.42-5,.8-11,1-17.81a1.19,1.19,0,0,0-.3-.56,1.5,1.5,0,0,0-1.85-.15c-.54.42-.47,1.33-.44,1.78a30.25,30.25,0,0,1-.82,9.17c-.37,1.38-.71,2.57-1.62,2.88-1.6.53-3.67-2.05-3.76-2.17-1.79-2.27-2-5.25-2.17-7.86-.17-2.38,0-4.6-1.35-5.47a1,1,0,0,0-.6-.21c-1.31.07-2.36,3.75-2.55,6.55-.38,5.53,2.51,8.82,1.34,9.75-.73.58-1.93-.58-5.19-1.57C1125.35,1063.49,1121.17,1063.35,1121,1064Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppls0-middlehand" class="cls-1"
                          d="M227,965.15c-.09.36.87,1.14,5.87,3.06a5.57,5.57,0,0,0-3.06,3.19,3.87,3.87,0,0,0-.13,1.28c.27,4.5,1.15,88,1.15,88l16.85-1.15-2-69.58a8.64,8.64,0,0,0,3-1.71,10.58,10.58,0,0,0,3.13-6.07c1.67-8,2-11.53,2-11.53.25-5,.44-11,.41-17.83a1.22,1.22,0,0,0-.31-.56,1.51,1.51,0,0,0-1.86-.08c-.52.43-.42,1.34-.38,1.78a30.4,30.4,0,0,1-.51,9.2c-.33,1.39-.63,2.6-1.53,2.93-1.58.59-3.74-1.92-3.83-2-1.86-2.21-2.16-5.19-2.43-7.79-.24-2.37-.16-4.59-1.53-5.42a1,1,0,0,0-.61-.19c-1.3.11-2.23,3.82-2.33,6.63-.19,5.54,2.8,8.74,1.66,9.71-.7.6-2-.52-5.23-1.41C231.38,964.47,227.19,964.47,227,965.15Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppl0-righthand" class="cls-1"
                          d="M1809.89,1039.39c-.15.33.64,1.28,5.21,4.09a5.54,5.54,0,0,0-3.6,2.57,3.8,3.8,0,0,0-.36,1.23c-.56,4.47-15,86.68-15,86.68l16.77,2q5.38-34.38,10.76-68.77a8.88,8.88,0,0,0,3.26-1.13,10.57,10.57,0,0,0,4.19-5.4c3.11-7.56,4.1-11,4.1-11,1.16-4.89,2.44-10.75,3.67-17.46a1.25,1.25,0,0,0-.2-.6,1.49,1.49,0,0,0-1.81-.42c-.6.33-.66,1.24-.71,1.68a30,30,0,0,1-2.19,8.94c-.57,1.31-1.09,2.45-2,2.61-1.66.28-3.32-2.58-3.39-2.71-1.42-2.51-1.17-5.49-1-8.1.2-2.38.69-4.55-.51-5.61a.93.93,0,0,0-.56-.3c-1.3-.13-2.89,3.35-3.51,6.09-1.2,5.41,1.15,9.1-.14,9.85-.81.46-1.83-.87-4.89-2.35C1814.3,1039.52,1810.18,1038.75,1809.89,1039.39Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="ppls0-righthand" class="cls-1"
                          d="M377.91,1074.68l48.3-80.13a19.11,19.11,0,0,1-.59-5.87c.11-2,.57-10.17,6.47-12.77,3.47-1.52,7.55-.55,10.29,1.37a11.75,11.75,0,0,1,4.6,12.25c-1.38,4.86-7.66,8.94-7.66,8.94s-44.57,78.57-46.47,82h0C392.12,1081.67,380.86,1078.51,377.91,1074.68Z"
                          transform="translate(-35.42 -538.51)"/>
                </g>
                <g id="Hats">
                    <path id="Hat1" class="cls-1"
                          d="M733.77,678.21l.24.39-3.22,3.1,0,.06.11-.07,3.88-.39-.11.07c-.24,1.07-2.45,1.44-3.53,1.85l.59.33,2.1-.67.75,1c-.69,1.12-1.38,2.25-2.08,3.37l.05,0L736,686l.72.93-1.44.88.23.39,1.42-.18-.09,1.36c-2,.52-7.55,4-8.73,5.71a53.4,53.4,0,0,0,5.15-2.69c.69-.48,1.78-1.35,2.33-1.19l-2.75,3.36c-.87.71-5,.87-6.13,1.22l-5.19,3-12,6.3-5.34,3.64-8.51,2.83.07.11,5.67,14.79c.73,2,1.66,5.34-.21,6.4l-16.82-12c-11.89-8.42-23.57-16.65-35.4-25l-15-10.36-42.84-94.8c.35-.36,1.53-2.18,1.87-2.06l46.28,21.76,4.69-8.44,4.45-4.47A157.28,157.28,0,0,1,662,584.9l16.43,5.77L691,598l8.18,4.61,3.2,4,4.32,14.69q2.31,7.68,4.63,15.35c.35,3.27.7,6.55,1,9.82l.78,6.4q-1.27,4.68-2.54,9.34l-.63,2.6c-.8,1.66-1.59,3.32-2.39,5-.32.73-.64,1.46-.95,2.19L700,674.69l-8.19,3.47-8.69,3q2.72,6.09,5.45,12.18c.37,1,1.48,4.1,2.2,4.61l8,.36,4.25-1.25,7-5c2.35-2,5-3.16,7-5.24,5-5.27,8.08-12.22,12.68-17.65l1.28.89c-1.74,3.22-3.49,6.45-5.22,9.67l6.46-6.17,1.46-2.49c-.54,2-1.08,4-1.6,5.95l1.71,1.17Zm-42.92,21.62,7.46,0-7.61-1.08Zm27.39-11.68,5.31-6.3C721.72,683.31,718,686.23,718.24,688.15Zm7.63,5.88,6.84-4.18C730.39,691.15,726.37,691.68,725.87,694Zm3.19-6.15a16,16,0,0,0,3-3.3l-2.37,1Zm-.75-7.49,2.85-3.72,0,0C729.21,678,728.34,678.53,728.31,680.39Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Hat2" class="cls-1"
                          d="M1394.67,825.23l-.36-.28c.55-1.2,1.09-2.4,1.63-3.6l0,0-.07.09-3.24,1.36.07-.09c-.2-1,1.59-1.91,2.37-2.56l-.63-.14-1.58,1.15-1-.65c.18-1.17.36-2.35.53-3.53l0,0-2.46,2.05-1-.64.92-1.16-.35-.28-1.17.53-.44-1.23c1.56-1,5-5.53,5.44-7.34a40.65,40.65,0,0,0-3.47,3.73c-.41.6-1,1.66-1.57,1.66.37-1.23.75-2.46,1.12-3.7.48-.85,4-2,4.88-2.68l3.37-4q4-4.35,8-8.71l3.27-4.61,6.34-4.73-.1-.08-10.55-11.62c-1.41-1.62-3.47-4.31-2.24-5.73l19.22,6.28c13.55,4.35,26.85,8.61,40.32,12.89l17,5.27,73.31,72.85c-.16.42-.51,2.33-.85,2.31l-48.58-7.22c-.3,2.9-.59,5.81-.89,8.71-.72,1.7-1.45,3.41-2.17,5.12a125.14,125.14,0,0,1-7,14.66l-16.51-.83-13.71-3.2-8.88-1.95-4.31-2.73-9.34-11.9L1430,856.21l-4.64-8.44c-1-1.83-2.07-3.65-3.1-5.47q-.68-4.47-1.33-8.94c-.15-.83-.29-1.65-.44-2.47.06-1.68.13-3.35.19-5v-2.18l4.71-4.13,5.82-5.21,6.43-5q-4.7-4.68-9.37-9.37c-.7-.77-2.85-3.25-3.67-3.51l-7.08,1.76-3.22,2.21-4.24,6.25c-1.3,2.38-3.15,4.1-4.08,6.46-2.33,6-2.39,12.93-4.34,18.94l-1.46-.45c.3-3.31.59-6.62.89-9.93l-3.3,7.15c-.11.86-.21,1.72-.32,2.59q-.42-2.85-.87-5.7l-1.93-.58Zm29.19-30.35-6.48,2,7-1Zm-19.43,17.49c-.75,2.32-1.49,4.64-2.24,7C1403.23,817.56,1405.35,814,1404.43,812.37Zm-8.88-3.22-4.38,5.49C1392.7,812.88,1396,811.36,1395.55,809.15Zm-.45,6.28a12.51,12.51,0,0,0-1.38,3.72l1.69-1.5C1395.31,816.91,1395.2,816.17,1395.1,815.43Zm3.5,6.44-1.07,4,0,0C1398.73,824.24,1399.28,823.53,1398.6,821.87Z"
                          transform="translate(-35.42 -538.51)"/>
                    <path id="Hat0" class="cls-1"
                          d="M468.11,661.79l.2.27-2.43,2.69,0,0,.09-.06,3-.7-.08.06c-.16.83-1.89,1.34-2.72,1.77l.47.19,1.64-.73.64.6-1.54,2.82,0,0,2.63-1.34.6.63-1.11.82.2.27,1.11-.28,0,1c-1.56.61-5.8,3.84-6.67,5.24a46.3,46.3,0,0,0,4-2.57c.53-.44,1.36-1.21,1.8-1.15l-2.06,2.84c-.65.62-3.86,1.17-4.78,1.56l-4,2.83q-4.61,3-9.19,6L445.89,688l-6.6,3,.06.07q2.49,5.31,5,10.63c.63,1.47,1.48,3.88,0,4.87l-13.63-7.38c-9.65-5.14-19.11-10.16-28.7-15.24l-12.18-6.3-36.93-67.42c.26-.32,1.13-1.81,1.4-1.76l37.15,11.69c1.13-2.3,2.27-4.6,3.4-6.89l3.35-3.85a140.81,140.81,0,0,1,10.24-10.94l13.12,2.67,10.13,4.23,5.81,2.34,3.43,3,3.9,10.7L449,632.61l1.14,7.35c.28,1.59.56,3.18.83,4.77l-1.68,7.34c-.13.68-.27,1.36-.4,2l-1.71,4-.68,1.75-5.09,2.75-6.32,3.49-6.74,3.19,4.7,8.67c.33.7,1.31,3,1.89,3.26l5-.43,4.62-1.51q2.67-2.26,5.36-4.51c1.79-1.75,3.82-2.92,5.3-4.7,3.74-4.52,5.94-10.13,9.4-14.74l.7,1.22-3.48,7.24,4.88-5.35c.36-.68.71-1.36,1.06-2l-.57,2.52c-.18,1.37-.35,2.73-.53,4.1Zm-33,20.86,5.86-.81-6,0C435,682.09,435,682.37,435.08,682.65Zm21.15-11.71,4-5.33C458.8,666.91,456,669.51,456.23,670.94Zm6.2,3.67,5.24-3.88C465.89,672,462.74,672.78,462.43,674.61Zm2.3-5a13.71,13.71,0,0,0,2.27-2.82l-1.83,1C465,668.4,464.88,669,464.73,669.61Zm-.84-5.6L466,660.9l0,0C464.51,662.09,463.85,662.59,463.89,664Z"
                          transform="translate(-35.42 -538.51)"/>
                    <g id="Hat3">
                        <polygon class="cls-1"
                                 points="1641.18 153.91 1703.82 140.64 1765.09 232.55 1708.24 238.68 1641.18 153.91"/>
                        <polygon class="cls-1"
                                 points="1658.2 179.1 1642.88 186.25 1642.88 198.51 1655.48 225.74 1671.48 244.13 1684.41 255.02 1703.13 242.76 1707.56 231.87 1679.31 179.1 1658.2 179.1"/>
                        <path class="cls-1"
                              d="M1756.6,712.85a1.33,1.33,0,0,1,.42-.44c1.58-1,12.65-10.93,18.3-20.5,4.45-7.52,6.25-16,8.33-26,.21-1,.33-1.65.35-1.72l-2.89-1-2.73-41,16.51-1.53-3.06,43.74h-4.94c-.69,9.66-1.69,17.78-3.91,24.34-2,6-5,9.79-9.28,15.32-6.8,8.74-13.63,13.5-14.15,14.25a.17.17,0,0,1-.06,0C1758.84,718.59,1755.62,714.53,1756.6,712.85Z"
                              transform="translate(-35.42 -538.51)"/>
                    </g>
                    <g id="Hat4">
                        <polygon class="cls-1"
                                 points="983.6 96.38 1017.6 150.64 952.34 239.77 927.05 188.49 983.6 96.38"/>
                        <polygon class="cls-1"
                                 points="965.79 121.02 953.82 109.09 942.31 113.31 921.06 134.49 909.3 155.84 903.51 171.73 921.46 185.1 933.21 185.51 973.05 140.84 965.79 121.02"/>
                        <path class="cls-1"
                              d="M1027.33,717a1.2,1.2,0,0,1,.56.25c1.48,1.14,14.61,8.12,25.54,10.14,8.59,1.59,17.14.38,27.3-1.12l1.74-.27,0-3.07L1120,706.32l7.11,15L1085,733.45l-1.7-4.63h0c-9.31,2.67-17.28,4.52-24.2,4.69-6.35.15-10.91-1.31-17.58-3.45-10.55-3.38-17.36-8.16-18.24-8.39a.17.17,0,0,1-.07,0C1022.71,721.12,1025.42,716.7,1027.33,717Z"
                              transform="translate(-35.42 -538.51)"/>
                    </g>
                    <polygon id="Hat5" class="cls-1"
                             points="238.2 364.21 260.92 337.15 260.92 333.57 243.31 319.79 241.52 313.91 241.26 301.4 248.41 288.64 251.48 261.57 253.52 261.57 250.71 283.27 253.84 261.22 254.89 261.22 251.22 283.31 255.31 261 255.82 261 251.73 283.5 256.17 261 258.05 261.29 252.5 283.69 258.08 262.05 258.66 261.32 258.78 262.12 253.26 283.91 259.36 261.76 260.16 261.89 253.87 284.07 261.59 259.94 261.72 260.49 254.16 284.14 262.52 260.2 263.7 261.06 254.67 284.33 262.71 265.72 262.71 267.86 255.11 284.49 250.77 289.31 249.41 289.47 242.9 301.21 242.6 301.68 242.52 302.21 242.37 313.76 243.99 319.1 263.05 332.13 266.03 332.47 308.92 282.25 402.11 273.83 367.9 300.89 367.9 306.51 381.69 326.68 346.96 351.19 298.96 374.42 282.37 349.66 238.2 364.21"/>
                    <path id="Hat7" class="cls-1"
                          d="M797,788.85l-71.74,49.79,78.38,78.13,69.19-76.34-53.11-36-.51-17.37,3.24-1.27,1.44-2.22,1.45-3.23.34-18.81-1.27-1.87-1-.85-.76-1.11h-1.19l-1.11-1.1a3.06,3.06,0,0,1-.94-.77c-.17-.34-1.44-.77-1.44-.77h-2.05l-.85,1.11-1.1.26s-.51-.69-.77-.69-1.36.09-1.36.09a4.7,4.7,0,0,0-.94.77c-.25.34-.59,1.1-.85,1.36a15,15,0,0,0-1,1.7l-1.36,1.53-1,.43.17,14.81,3,4.93,1.78,1.87a23,23,0,0,0,2,1.62,17,17,0,0,1,1.7,1.79l.77,3.74v13.36Z"
                          transform="translate(-35.42 -538.51)"/>
                    <polygon id="Hat8" class="cls-1"
                             points="1090.37 344.72 1083.73 338.59 1080.5 333.32 1076.75 326.17 1071.82 322.59 1066.37 321.91 1062.45 325.49 1060.92 330.25 1057.52 334.17 1051.56 335.7 1040.67 335.7 1035.9 333.32 1031.31 329.23 1028.24 327.7 1028.24 325.49 1032.16 325.32 1034.54 320.55 1041.35 319.36 1046.63 321.4 1050.03 322.08 1053.94 317.32 1057.69 314.59 1063.65 313.57 1070.63 313.57 1075.22 314.42 1078.45 319.87 1080.5 324.98 1082.2 330.08 1084.24 333.49 1087.13 337.06 1090.37 339.79 1093.94 341.32 1098.37 341.83 1103.82 341.83 1103.82 292.81 1129.01 321.57 1144.67 310.85 1148.24 310 1150.96 311.02 1156.07 316.81 1170.88 331.79 1182.11 350.34 1190.45 365.49 1190.45 369.06 1188.41 371.62 1172.92 379.79 1171.9 383.7 1172.75 387.62 1188.07 416.38 1103.8 354.59 1103.67 344.93 1091.48 345.06 1090.37 344.72"/>
                    <polygon id="Hat9" class="cls-1"
                             points="1596.5 140.92 1575.34 142.37 1571.43 121.5 1574.91 115.25 1576.69 115.2 1571.67 103.6 1562.96 97.18 1557.3 92.9 1549.4 89 1544.32 87.44 1550.37 133.78 1506.49 127.18 1502.45 106 1494.68 108.14 1486.82 104.77 1481.62 99.38 1470.36 64.42 1467.9 40.37 1470.02 36.17 1486.97 37.03 1489.5 34.68 1483.53 21.68 1535.53 0 1544.56 81.8 1550.07 84.63 1559.82 90.1 1568 96.46 1574.84 101.36 1579.61 114.12 1581.89 113.63 1583.97 115.07 1596.5 140.92"/>
                </g>
            </svg>
        </div>
        <div id="topbgcover" class="bgcover hide"></div>
        <div id="bottombgcover" class="bgcover hide"></div>
        <div id="YT-meet">
            <div id="img-monitor" class="center-frames">
                <svg
                        xmlns:dc="http://purl.org/dc/elements/1.1/"
                        xmlns:cc="http://creativecommons.org/ns#"
                        xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
                        xmlns:svg="http://www.w3.org/2000/svg"
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                        xmlns:sodipodi="http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd"
                        xmlns:inkscape="http://www.inkscape.org/namespaces/inkscape"
                        xmlns:ns1="http://sozi.baierouge.fr"
                        width="358.58923"
                        height="332.45477"
                        id="svg5101"
                        version="1.1"
                        inkscape:version="0.48.3.1 r9886"
                        sodipodi:docname="Mac-Linux LCD  by Merlin2525.svg"
                >
                    <title
                            id="title3296"
                    >Mac-Linux LCD</title
                    >
                    <defs
                            id="defs5103"
                    >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3368"
                        >
                            <stop
                                    style="stop-color:#ff6600;stop-opacity:1;"
                                    offset="0"
                                    id="stop3370"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3372"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3360"
                        >
                            <stop
                                    style="stop-color:#cc9900;stop-opacity:1;"
                                    offset="0"
                                    id="stop3362"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3364"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3352"
                        >
                            <stop
                                    style="stop-color:#003399;stop-opacity:1;"
                                    offset="0"
                                    id="stop3354"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3356"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3344"
                        >
                            <stop
                                    style="stop-color:#ffff00;stop-opacity:1;"
                                    offset="0"
                                    id="stop3346"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3348"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3336"
                        >
                            <stop
                                    style="stop-color:#6666cc;stop-opacity:1;"
                                    offset="0"
                                    id="stop3338"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3340"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3328"
                        >
                            <stop
                                    style="stop-color:#0099ff;stop-opacity:1;"
                                    offset="0"
                                    id="stop3330"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3332"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3320"
                        >
                            <stop
                                    style="stop-color:#ff3300;stop-opacity:1;"
                                    offset="0"
                                    id="stop3322"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3324"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3312"
                        >
                            <stop
                                    style="stop-color:#990000;stop-opacity:1;"
                                    offset="0"
                                    id="stop3314"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3316"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3304"
                        >
                            <stop
                                    style="stop-color:#009900;stop-opacity:1;"
                                    offset="0"
                                    id="stop3306"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="1"
                                    id="stop3308"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3288"
                        >
                            <stop
                                    style="stop-color:#000000;stop-opacity:1;"
                                    offset="0"
                                    id="stop3290"
                            />
                            <stop
                                    style="stop-color:#000000;stop-opacity:0;"
                                    offset="1"
                                    id="stop3292"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient3280"
                        >
                            <stop
                                    style="stop-color:#000000;stop-opacity:1"
                                    offset="0"
                                    id="stop3282"
                            />
                            <stop
                                    style="stop-color:#999999;stop-opacity:0;"
                                    offset="1"
                                    id="stop3284"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                id="linearGradient4519"
                        >
                            <stop
                                    offset="0"
                                    stop-color="#00b5fb"
                                    id="stop4521"
                                    style="stop-color:#98fc66;stop-opacity:1"
                            />
                            <stop
                                    style="stop-color:#339900;stop-opacity:1"
                                    id="stop4527"
                                    stop-color="#00b5fb"
                                    offset="0.3472428"
                            />
                            <stop
                                    offset="1"
                                    stop-color="#000075"
                                    id="stop4523"
                                    style="stop-color:#000000;stop-opacity:1"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient4170"
                        >
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:1;"
                                    offset="0"
                                    id="stop4172"
                            />
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:0;"
                                    offset="1"
                                    id="stop4174"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient4154"
                        >
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:1;"
                                    offset="0"
                                    id="stop4156"
                            />
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:0;"
                                    offset="1"
                                    id="stop4158"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                inkscape:collect="always"
                                id="linearGradient4146"
                        >
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:1;"
                                    offset="0"
                                    id="stop4148"
                            />
                            <stop
                                    style="stop-color:#ffffff;stop-opacity:0;"
                                    offset="1"
                                    id="stop4150"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                id="linearGradient6219"
                                y2="364.09"
                                gradientUnits="userSpaceOnUse"
                                x2="1033.3"
                                gradientTransform="translate(-362.76,85.405)"
                                y1="356.34"
                                x1="975.26001"
                        >
                            <stop
                                    id="stop6207"
                                    stop-color="#ccc"
                                    offset="0"
                            />
                            <stop
                                    id="stop6209"
                                    stop-opacity=".20833"
                                    offset="1"
                            />
                        </linearGradient
                        >
                        <filter
                                id="filter9727"
                                color-interpolation-filters="sRGB"
                        >
                            <feGaussianBlur
                                    id="feGaussianBlur9729"
                                    stdDeviation="2.8209698"
                            />
                        </filter
                        >
                        <linearGradient
                                id="linearGradient4633"
                        >
                            <stop
                                    id="stop4635"
                                    stop-color="#00b5fb"
                                    offset="0"
                            />
                            <stop
                                    offset="0.5"
                                    stop-color="#00b5fb"
                                    id="stop4525"
                                    style="stop-color:#005ab8;stop-opacity:1;"
                            />
                            <stop
                                    id="stop4637"
                                    stop-color="#000075"
                                    offset="1"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                id="linearGradient5412"
                        >
                            <stop
                                    id="stop5414"
                                    stop-opacity=".40625"
                                    offset="0"
                            />
                            <stop
                                    id="stop5422"
                                    stop-color="#808080"
                                    offset=".51999"
                            />
                            <stop
                                    id="stop5420"
                                    stop-color="#fff"
                                    offset=".7847"
                            />
                            <stop
                                    id="stop5416"
                                    stop-opacity=".5625"
                                    offset="1"
                            />
                        </linearGradient
                        >
                        <linearGradient
                                id="linearGradient5811"
                                y2="769.31"
                                gradientUnits="userSpaceOnUse"
                                x2="759.88"
                                gradientTransform="translate(-362.76,85.405)"
                                y1="714.35999"
                                x1="770.84003"
                        >
                            <stop
                                    id="stop5807"
                                    stop-color="#4d4d4d"
                                    stop-opacity=".93671"
                                    offset="0"
                            />
                            <stop
                                    id="stop5809"
                                    stop-color="#4d4d4d"
                                    stop-opacity="0"
                                    offset="1"
                            />
                        </linearGradient
                        >
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient4519"
                                id="radialGradient8653"
                                gradientUnits="userSpaceOnUse"
                                cx="396.42191"
                                cy="585.40186"
                                r="3.8389001"
                                gradientTransform="matrix(0.61664901,-0.35764074,-0.34915634,-0.60202007,274.05417,1091.9971)"
                                fx="396.42191"
                                fy="585.40186"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient5412"
                                id="linearGradient8656"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.49808129,0,0,0.49808129,511.64294,306.6506)"
                                x1="937.64001"
                                y1="640.03998"
                                x2="937.64001"
                                y2="593.96997"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient5412"
                                id="linearGradient8663"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.49808129,0,0,0.49808129,511.64294,306.6506)"
                                x1="574.02002"
                                y1="686.88"
                                x2="890.35999"
                                y2="686.88"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient5811"
                                id="linearGradient8666"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.49808129,0,0,0.49808129,511.64294,306.6506)"
                                x1="770.84003"
                                y1="714.35999"
                                x2="759.88"
                                y2="769.31"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient5412"
                                id="linearGradient8669"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.49808129,0,0,0.49808129,511.64294,306.6506)"
                                x1="784.79999"
                                y1="629.14001"
                                x2="777.88"
                                y2="718.22998"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient4633"
                                id="radialGradient8672"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.59271674,-0.13452678,-0.13637964,0.60088527,626.45566,367.22476)"
                                cx="714.63"
                                cy="345.89999"
                                r="319.13"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient6219"
                                id="linearGradient8676"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(-0.49808129,0,0,0.49808129,511.64294,306.6506)"
                                x1="975.26001"
                                y1="356.34"
                                x2="1033.3"
                                y2="364.09"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient4146"
                                id="linearGradient4152"
                                x1="25.356106"
                                y1="472.50998"
                                x2="166.32663"
                                y2="468.10464"
                                gradientUnits="userSpaceOnUse"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient4154"
                                id="linearGradient4160"
                                x1="168.5293"
                                y1="377.79538"
                                x2="171.46619"
                                y2="454.88864"
                                gradientUnits="userSpaceOnUse"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient4170"
                                id="linearGradient4176"
                                x1="364.56644"
                                y1="529.04498"
                                x2="231.67235"
                                y2="548.86902"
                                gradientUnits="userSpaceOnUse"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3280"
                                id="linearGradient3286"
                                x1="204.91808"
                                y1="251.26611"
                                x2="204.58609"
                                y2="241.88751"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(0.99989707,-0.01434744,0.01434744,0.99989707,-35.450566,346.1834)"
                        />
                        <linearGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3288"
                                id="linearGradient3294"
                                x1="156.13951"
                                y1="600.54761"
                                x2="156.5666"
                                y2="582.04413"
                                gradientUnits="userSpaceOnUse"
                                gradientTransform="matrix(1.0311606,0,0,1.0000363,-13.2785,2.2315184)"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3304"
                                id="radialGradient3310"
                                cx="196.53877"
                                cy="593.24609"
                                fx="196.53877"
                                fy="593.24609"
                                r="4.8162794"
                                gradientTransform="matrix(3.3011016,-0.69771914,-1.0887544,2.7070014,-136.05007,-873.116)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3312"
                                id="radialGradient3318"
                                cx="209.12712"
                                cy="592.65442"
                                fx="209.12712"
                                fy="592.65442"
                                r="4.8162794"
                                gradientTransform="matrix(1.489318,-1.0737616,0.68826907,1.8958269,-839.92906,-304.07818)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3320"
                                id="radialGradient3326"
                                cx="221.78755"
                                cy="593.51691"
                                fx="221.78755"
                                fy="593.51691"
                                r="4.8162794"
                                gradientTransform="matrix(1.1931958,-1.1241099,0.88731672,1.5860323,-899.17961,-96.014333)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3328"
                                id="radialGradient3334"
                                cx="231.4567"
                                cy="593.09515"
                                fx="231.4567"
                                fy="593.09515"
                                r="4.8162794"
                                gradientTransform="matrix(1.6495137,-1.1881389,0.63153843,1.8784968,-854.59037,-243.63069)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3336"
                                id="radialGradient3342"
                                cx="243.97409"
                                cy="592.91803"
                                fx="243.97409"
                                fy="592.91803"
                                r="4.8162794"
                                gradientTransform="matrix(1.6599535,-1.384041,0.71178137,1.8819354,-912.73326,-182.88906)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3344"
                                id="radialGradient3350"
                                cx="256.94751"
                                cy="593.26477"
                                fx="256.94751"
                                fy="593.26477"
                                r="4.8162794"
                                gradientTransform="matrix(1.1929159,-1.4101638,1.0785222,1.8237327,-1019.1123,-123.91393)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3352"
                                id="radialGradient3358"
                                cx="269.00888"
                                cy="592.45911"
                                fx="269.00888"
                                fy="592.45911"
                                r="4.8162794"
                                gradientTransform="matrix(1.2900802,-1.6014357,1.0992707,1.9963461,-1059.0008,-157.11833)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3360"
                                id="radialGradient3366"
                                cx="279.96024"
                                cy="592.99176"
                                fx="279.96024"
                                fy="592.99176"
                                r="4.8162794"
                                gradientTransform="matrix(1.0207449,-1.823271,1.2013418,1.464882,-1047.8872,237.2758)"
                                gradientUnits="userSpaceOnUse"
                        />
                        <radialGradient
                                inkscape:collect="always"
                                xlink:href="#linearGradient3368"
                                id="radialGradient3374"
                                cx="291.92264"
                                cy="593.43152"
                                fx="291.92264"
                                fy="593.43152"
                                r="4.8162794"
                                gradientTransform="matrix(0.87803729,-2.0595803,1.3614185,1.4921838,-1101.9987,311.77004)"
                                gradientUnits="userSpaceOnUse"
                        />
                    </defs
                    >
                    <sodipodi:namedview
                            id="base"
                            pagecolor="#ffffff"
                            bordercolor="#666666"
                            borderopacity="1.0"
                            inkscape:pageopacity="0.0"
                            inkscape:pageshadow="2"
                            inkscape:zoom="0.8774875"
                            inkscape:cx="29.0029"
                            inkscape:cy="77.316251"
                            inkscape:document-units="px"
                            inkscape:current-layer="layer1"
                            showgrid="false"
                            inkscape:window-width="1680"
                            inkscape:window-height="1026"
                            inkscape:window-x="0"
                            inkscape:window-y="654"
                            inkscape:window-maximized="1"
                            fit-margin-top="0"
                            fit-margin-left="0"
                            fit-margin-right="0"
                            fit-margin-bottom="0"
                            showborder="true"
                            inkscape:showpageshadow="false"
                    />
                    <g
                            inkscape:label="Layer 1"
                            inkscape:groupmode="layer"
                            id="layer1"
                            transform="translate(31.913173,-343.12077)"
                    >
                        <path
                                style="opacity:0.75154999;fill:#cccccc"
                                inkscape:connector-curvature="0"
                                id="path4908"
                                d="M 279.39759,369.63547 -15.561164,343.4364 25.864257,616.10104 325.9931,605.25283 c 0.62574,-0.69732 1.01713,-1.67356 0.29018,-3.94979 L 283.53147,374.28755 c -0.4159,-3.33714 -2.13627,-4.25361 -4.13407,-4.65208 z"
                        />
                        <path
                                style="opacity:0.37267001;fill:#4d4d4d"
                                inkscape:connector-curvature="0"
                                id="path4910"
                                d="M 326.00446,605.24785 26.005114,616.12096 c -0.08966,5.87238 -7.999186,7.33674 -15.475386,9.04018 L 308.64134,611.66811 c 8.32045,-0.66743 16.60902,-3.37201 17.36461,-6.42026 z"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="fill:url(#linearGradient8676)"
                                id="path4912"
                                d="m -15.625915,343.39157 c -1.583898,-0.35862 -3.142893,-0.43831 -4.612233,0.24406 l -9.453582,5.54862 c -1.563976,1.38467 -2.161673,2.99347 -2.221443,4.72181 L 8.7651259,622.20751 c 0.3337145,1.50919 0.8965464,2.57508 2.0321721,2.94366 4.637136,-1.42451 15.271172,-2.17163 15.086882,-9.03021 L -15.625915,343.39157 z"
                        />
                        <path
                                style="opacity:0.44099001;filter:url(#filter9727)"
                                inkscape:connector-curvature="0"
                                id="path4914"
                                d="m 108.48,237.64 c -0.05,-4.2 2.42,-5.87 6.93,-5.52 l 549.24,-45.87 c 4.01,-0.13 4.72,2 4.2,4.96 l -73.32,479.58 c 0.3,3.62 -0.97,5.68 -4.39,5.58 L 36.08,657.78 c -5.213,-0.29 -5.626,-1.18 -5.227,-4.86 L 108.48,237.64 z"
                                transform="matrix(-0.49808129,0,0,0.49808129,330.95897,264.11197)"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="opacity:0.78261001;fill:url(#radialGradient8672)"
                                id="path4916"
                                d="m 275.93095,382.47601 c 0.0249,-2.09194 -1.20536,-2.92374 -3.4517,-2.74941 L -1.086922,356.87961 c -1.997306,-0.0648 -2.3509437,0.99616 -2.0919414,2.47048 L 33.340457,598.21992 c 0.239079,1.72834 0.637544,2.78925 2.186577,2.77929 l 276.464996,-9.25933 c 2.5965,-0.14444 2.80221,-0.58773 2.60348,-2.42067 l -38.66456,-206.8432 z"
                        />
                        <path
                                style="fill:url(#linearGradient3286);fill-opacity:1;stroke:none"
                                d="m 125.24092,594.50558 5.85046,-2.98912 102.03935,-3.53297 3.08053,3.14765 z"
                                id="path3278"
                                inkscape:connector-curvature="0"
                                sodipodi:nodetypes="ccccc"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="fill:url(#linearGradient8669)"
                                id="path4918"
                                d="m 151.02212,618.46194 -74.049742,3.69078 -7.486162,29.06305 c -0.229117,8.34784 0.846738,15.39071 8.307996,16.04818 l 78.029418,-5.90227 c -3.67584,-1.91761 -6.2559,-4.80648 -7.9693,-9.94668 -0.51801,-2.13179 -0.62759,-4.26358 -0.84176,-6.39038 l 4.00955,-26.56268 z"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="fill:url(#linearGradient8666)"
                                id="path4920"
                                d="m 224.03088,665.4061 -68.40649,-4.17392 -79.324422,5.83253 39.333482,4.83139 c 9.30914,0.4433 18.8723,0.82184 31.99674,0.31379 l 76.52023,-5.10035 c 0.89654,-0.37356 3.17278,-0.45823 -0.11954,-1.70344 z"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="fill:url(#linearGradient8663)"
                                id="path4922"
                                d="m 225.7393,666.97008 -72.83941,4.89614 c -11.11219,0.68237 -21.98033,0.88658 -32.38525,0.1544 l -41.171395,-4.66204 c -17.886099,-0.93141 -5.528703,-28.10672 -2.345963,-45.39513 l -1.319916,0.17931 c -2.525272,12.35242 -7.625624,23.09105 -7.501104,35.82699 0.388504,5.10035 2.704582,10.13097 10.888057,11.92407 64.481601,11.74973 97.464551,1.79309 146.674981,0.79693 v -3.72067 z"
                        />
                        <path
                                style="opacity:0.37860083;fill:url(#linearGradient4152);fill-opacity:1"
                                inkscape:connector-curvature="0"
                                id="path4924"
                                d="M 154.14509,373.81935 2.6486877,363.09068 39.989842,597.41801 130.96937,594.41458 154.14509,373.81935 z"
                        />
                        <path
                                style="opacity:0.53416;fill:url(#linearGradient4176);fill-opacity:1"
                                inkscape:connector-curvature="0"
                                id="path4926"
                                d="m 280.32403,421.46083 -58.37015,114.15525 89.27111,50.64491 -30.90096,-164.80016 z"
                        />
                        <path
                                style="opacity:0.24845001;fill:url(#linearGradient4160);fill-opacity:1"
                                inkscape:connector-curvature="0"
                                id="path4928"
                                d="M 274.31218,379.8312 -1.2114423,357.08382 C 69.580851,504.47604 251.4901,455.46982 274.31218,379.8312 z"
                        />
                        <path
                                style="opacity:0.44099001;fill:#333333"
                                inkscape:connector-curvature="0"
                                id="path4930"
                                d="m 60.864429,604.56049 -16.511395,0.46322 0.348657,6.42027 16.700666,-0.6226 -0.537928,-6.26089 z"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="opacity:0.44099001;fill:url(#linearGradient8656)"
                                id="path4932"
                                d="m 60.630331,604.78961 -16.008333,0.3885 0.463216,6.07162 15.968486,-0.73717 -0.423369,-5.72295 z"
                        />
                        <path
                                inkscape:connector-curvature="0"
                                style="fill:url(#radialGradient8653)"
                                id="path4934"
                                d="m 312.78897,598.7703 c 0,1.05593 0.8567,1.91263 1.91263,1.91263 1.05593,0 1.91263,-0.8567 1.91263,-1.91263 0,-1.05594 -0.8567,-1.91264 -1.91263,-1.91264 -1.05593,0 -1.91263,0.8567 -1.91263,1.91264 z"
                        />
                        <rect
                                style="opacity:0.69547323;fill:url(#radialGradient3310);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect4094"
                                width="9.6325588"
                                height="11.947719"
                                x="-137.45724"
                                y="589.8811"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                ry="2.2272851"
                        />
                        <rect
                                ry="2.2272851"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                y="589.8811"
                                x="-125.43319"
                                height="11.947719"
                                width="9.6325588"
                                id="rect4096"
                                style="opacity:0.69547323;fill:url(#radialGradient3318);fill-opacity:1;fill-rule:nonzero;stroke:none"
                        />
                        <rect
                                style="opacity:0.69547323;fill:url(#radialGradient3326);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect4098"
                                width="9.6325588"
                                height="11.947719"
                                x="-113.43319"
                                y="589.8811"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                ry="2.2272851"
                        />
                        <rect
                                ry="2.2272851"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                y="589.84814"
                                x="-101.931"
                                height="11.947719"
                                width="9.6325588"
                                id="rect4100"
                                style="opacity:0.69547323;fill:url(#radialGradient3334);fill-opacity:1;fill-rule:nonzero;stroke:none"
                        />
                        <rect
                                style="opacity:0.69547323;fill:url(#radialGradient3342);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect4102"
                                width="9.6325588"
                                height="11.947719"
                                x="-89.906952"
                                y="589.84814"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                ry="2.2272851"
                        />
                        <rect
                                ry="2.2272851"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                y="589.84814"
                                x="-77.906929"
                                height="11.947719"
                                width="9.6325588"
                                id="rect4104"
                                style="opacity:0.69547323;fill:url(#radialGradient3350);fill-opacity:1;fill-rule:nonzero;stroke:none"
                        />
                        <rect
                                style="opacity:0.69547323;fill:url(#radialGradient3358);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect4106"
                                width="9.6325588"
                                height="11.947719"
                                x="-65.987778"
                                y="589.30847"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                ry="2.2272851"
                        />
                        <rect
                                ry="2.2272851"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                y="589.30847"
                                x="-53.963634"
                                height="11.947719"
                                width="9.6325588"
                                id="rect4108"
                                style="opacity:0.69547323;fill:url(#radialGradient3366);fill-opacity:1;fill-rule:nonzero;stroke:none"
                        />
                        <rect
                                style="opacity:0.69547323;fill:url(#radialGradient3374);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect4110"
                                width="9.6325588"
                                height="11.947719"
                                x="-41.963512"
                                y="589.30847"
                                transform="matrix(-0.99940819,0.03439881,0.1580945,0.98742399,0,0)"
                                ry="2.2272851"
                        />
                        <rect
                                style="opacity:0.86831276;fill:url(#linearGradient3294);fill-opacity:1;fill-rule:nonzero;stroke:none"
                                id="rect3276"
                                width="112.19881"
                                height="2.323983"
                                x="103.54657"
                                y="598.28424"
                                transform="matrix(0.99946171,-0.03280677,0.03488311,0.9993914,0,0)"
                                ry="1.1619915"
                        />
                    </g>
                </svg>
            </div>
            <div id="YT-logo" class="center-frames">
                <svg viewBox="0 0 64 60" preserveAspectRatio="xMidYMid meet" focusable="false"
                     class="style-scope ytd-topbar-logo-renderer"
                     style="pointer-events: none; display: block; width: 100%; height: 100%;">
                    <g viewBox="0 0 60 60" preserveAspectRatio="xMidYMid meet"
                       class="style-scope ytd-topbar-logo-renderer">
                        <g class="style-scope ytd-topbar-logo-renderer">
                            <path fill="#FF0000" d="M63,14.87c-0.72-2.7-2.85-4.83-5.56-5.56C52.54,8,32.88,8,32.88,8S13.23,8,8.32,9.31
            c-2.7,0.72-4.83,2.85-5.56,5.56C1.45,19.77,1.45,30,1.45,30s0,10.23,1.31,15.13c0.72,2.7,2.85,4.83,5.56,5.56
            C13.23,52,32.88,52,32.88,52s19.66,0,24.56-1.31c2.7-0.72,4.83-2.85,5.56-5.56C64.31,40.23,64.31,30,64.31,30
            S64.31,19.77,63,14.87z" class="style-scope ytd-topbar-logo-renderer"></path>
                            <polygon fill="#FFFFFF" points="26.6,39.43 42.93,30 26.6,20.57"
                                     class="style-scope ytd-topbar-logo-renderer"></polygon>
                        </g>
                    </g>
                </svg>
            </div>
        </div>
        <div id="LastScene" class="center-frames">
            <img src="resources/images/UTAR_econvo_2020.jpg" style="width:100%;"/>
        </div>
        <div id="chinese-quotes">
            <div id="cq-0">
                <section class="odd">
                    <cn-word><chara>今</chara><chara>天</chara></cn-word>
                    <cn-word><chara>是</chara><chara>我</chara><chara>们</chara><chara>的</chara></cn-word>
                </section>
                <section class="even">
                    <cn-word><chara>毕</chara><chara>业</chara><chara>典</chara><chara>礼</chara><chara>。</chara></cn-word>
                </section>
            </div>
            <div id="cq-1">
                <section class="odd">
                    <cn-word><chara>往</chara><chara>年</chara></cn-word>
                    <cn-word><chara>毕</chara><chara>业</chara><chara>典</chara><chara>礼</chara></cn-word>
                </section>
                <section class="even">
                    <cn-word><chara>都</chara><chara>是</chara><chara>在</chara></cn-word>
                </section>
                <section class="odd">
                    <cn-word><chara>敦</chara><chara>林</chara><chara>良</chara><chara>实</chara><chara>礼</chara><chara>堂</chara></cn-word>
                </section>
                <section class="even">
                    <cn-word><chara>举</chara><chara>行</chara><chara>。</chara></cn-word>
                </section>
            </div>
            <div id="cq-2">
                <section class="text-center">
                    <cn-word><chara>今</chara><chara>年</chara></cn-word>
                    <cn-word><chara>我</chara><chara>们</chara></cn-word>
                    <cn-word><chara>不</chara><chara>一</chara><chara>样</chara><chara>。</chara></cn-word>
                </section>
            </div>
            <div id="cq-3">
                <section class="odd">
                    <cn-word><chara>让</chara><chara>我</chara><chara>们</chara></cn-word>
                    <cn-word><chara>一</chara><chara>同</chara></cn-word>
                </section>
                <section class="even">
                    <cn-word><chara>在</chara><chara>线</chara><chara>上</chara><chara>庆</chara><chara>祝</chara></cn-word>
                </section>
                <section class="odd">
                    <cn-word><chara>我</chara><chara>们</chara><chara>的</chara><chara>毕</chara><chara>业</chara><chara>典</chara><chara>礼</chara><chara>，</chara></cn-word>
                </section>
            </div>
            <div id="cq-4">
                <section class="odd">
                    <cn-word><chara>第</chara><chara>一</chara><chara>次</chara></cn-word>
                    <cn-word><chara>的</chara></cn-word>
                </section>
                <section class="even">
                    <cn-word><chara>线</chara><chara>上</chara><chara>毕</chara><chara>业</chara><chara>典</chara><chara>礼</chara><chara>。</chara></cn-word>
                </section>
            </div>
        </div>
        <div id="english-quotes">
            <div id="eq-0">
                <section class="odd">
                    <en-word><chara>T</chara><chara>o</chara><chara>d</chara><chara>a</chara><chara>y</chara></en-word>
                    <en-word><chara>i</chara><chara>s</chara><chara>&nbsp;</chara><chara>o</chara><chara>u</chara><chara>r</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>g</chara><chara>r</chara><chara>a</chara><chara>d</chara><chara>u</chara><chara>a</chara><chara>t</chara><chara>i</chara><chara>o</chara><chara>n</chara></en-word>
                    <en-word><chara>c</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>m</chara><chara>o</chara><chara>n</chara><chara>y</chara><chara>.</chara></en-word>
                </section>
            </div>
            <div id="eq-1">
                <section class="odd">
                    <en-word><chara>P</chara><chara>r</chara><chara>e</chara><chara>v</chara><chara>i</chara><chara>o</chara><chara>u</chara><chara>s</chara><chara>&nbsp;</chara><chara>y</chara><chara>e</chara><chara>a</chara><chara>r</chara><chara>s</chara><chara>,</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>g</chara><chara>r</chara><chara>a</chara><chara>d</chara><chara>u</chara><chara>a</chara><chara>t</chara><chara>i</chara><chara>o</chara><chara>n</chara></en-word>
                    <en-word><chara>c</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>m</chara><chara>o</chara><chara>n</chara><chara>i</chara><chara>e</chara><chara>s</chara></en-word>
                </section>
                <section class="odd">
                    <en-word><chara>w</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>&nbsp;</chara><chara>h</chara><chara>e</chara><chara>l</chara><chara>d</chara><chara>&nbsp;</chara><chara>i</chara><chara>n</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>D</chara><chara>e</chara><chara>w</chara><chara>a</chara><chara>n</chara><chara>&nbsp;</chara><chara>T</chara><chara>u</chara><chara>n</chara><chara>&nbsp;</chara><chara>D</chara><chara>r</chara><chara>&nbsp;</chara><chara>L</chara><chara>i</chara><chara>n</chara><chara>g</chara><chara>&nbsp;</chara><chara>L</chara><chara>i</chara><chara>o</chara><chara>n</chara><chara>g</chara><chara>&nbsp;</chara><chara>S</chara><chara>i</chara><chara>k</chara><chara>.</chara></en-word>
                </section>
            </div>
            <div id="eq-2">
                <section class="odd">
                    <en-word><chara>T</chara><chara>h</chara><chara>i</chara><chara>s</chara><chara>&nbsp;</chara><chara>y</chara><chara>e</chara><chara>a</chara><chara>r</chara><chara>,</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>w</chara><chara>e</chara></en-word>
                    <en-word><chara>a</chara><chara>r</chara><chara>e</chara><chara>&nbsp;</chara><chara>d</chara><chara>o</chara><chara>i</chara><chara>n</chara><chara>g</chara></en-word>
                    <en-word><chara>d</chara><chara>i</chara><chara>f</chara><chara>f</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>n</chara><chara>t</chara><chara>l</chara><chara>y</chara><chara>.</chara></en-word>
                </section>
            </div>
            <div id="eq-3">
                <section class="odd">
                    <en-word><chara>L</chara><chara>e</chara><chara>t</chara><chara>&nbsp;</chara><chara>u</chara><chara>s</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>c</chara><chara>e</chara><chara>l</chara><chara>e</chara><chara>b</chara><chara>r</chara><chara>a</chara><chara>t</chara><chara>e</chara><chara>&nbsp;</chara><chara>o</chara><chara>u</chara><chara>r</chara></en-word>
                </section>
                <section class="odd">
                    <en-word><chara>g</chara><chara>r</chara><chara>a</chara><chara>d</chara><chara>u</chara><chara>a</chara><chara>t</chara><chara>i</chara><chara>o</chara><chara>n</chara><chara>&nbsp;</chara><chara>c</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>m</chara><chara>o</chara><chara>n</chara><chara>y</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>o</chara><chara>n</chara><chara>l</chara><chara>i</chara><chara>n</chara><chara>e</chara><chara>&nbsp;</chara><chara>t</chara><chara>o</chara><chara>g</chara><chara>e</chara><chara>t</chara><chara>h</chara><chara>e</chara><chara>r</chara><chara>,</chara></en-word>
                </section>
            </div>
            <div id="eq-4">
                <section class="odd">
                    <en-word><chara>O</chara><chara>u</chara><chara>r</chara><chara>&nbsp;</chara><chara>f</chara><chara>i</chara><chara>r</chara><chara>s</chara><chara>t</chara><chara>&nbsp;</chara><chara>o</chara><chara>n</chara><chara>l</chara><chara>i</chara><chara>n</chara><chara>e</chara></en-word>
                </section>
                <section class="even">
                    <en-word><chara>g</chara><chara>r</chara><chara>a</chara><chara>d</chara><chara>u</chara><chara>a</chara><chara>t</chara><chara>i</chara><chara>o</chara><chara>n</chara><chara>&nbsp;</chara><chara>c</chara><chara>e</chara><chara>r</chara><chara>e</chara><chara>m</chara><chara>o</chara><chara>n</chara><chara>y</chara><chara>.</chara></en-word>
                </section>
            </div>
        </div>
    </div>
    <script>
        document.addEventListener("DOMContentLoaded",function(){
            document.getElementById("playClickable").addEventListener("click",function(){
                document.getElementById("playScr").style.display="none";
                /*Word Fading*/
                /*CN word*/
                anm_cq0();
                anm_cq1();
                anm_cq2();
                anm_cq3();
                anm_cq4();
                /*EN word*/
                anm_eq0();
                anm_eq1();
                anm_eq2();
                anm_eq3();
                anm_eq4();
                /*End - Word Fading*/
                document.getElementById("FirstScene-0").classList.toggle("start",true);
                setTimeout(function(){
                    document.getElementById("FirstScene-1").classList.toggle("start",true);
                    setTimeout(function(){
                        document.getElementById("FirstScene-0").classList.toggle("start",false);
                        document.getElementById("FirstScene-1").classList.toggle("start",false);
                        document.getElementById("DTLLS_0").classList.toggle("start",true);
                        setTimeout(function(){
                            document.getElementById("DTLLS_1").classList.toggle("start",true);
                            setTimeout(function(){
                                document.getElementById("DTLLS_0").classList.toggle("start",false);
                            },2000);
                            setTimeout(function(){
                                document.getElementById("topbgcover").classList.toggle("hide",false);
                                document.getElementById("bottombgcover").classList.toggle("hide",false);
                                document.getElementById("GraduanThrowHats").classList.toggle("start",true);
                                document.querySelector("#GraduanThrowHats svg #Hands").classList.toggle("start",true);
                                document.querySelector("#GraduanThrowHats svg #Peoples").classList.toggle("start",true);
                                setTimeout(function(){
                                    document.querySelector("#GraduanThrowHats svg #Hats").classList.toggle("start",true);
                                    setTimeout(function(){
                                        document.querySelector("#GraduanThrowHats svg #Hats").classList.toggle("start",false);
                                        setTimeout(function(){
                                            document.querySelector("#GraduanThrowHats svg #Hats").classList.toggle("start",true);
                                            setTimeout(function(){
                                                document.querySelector("#GraduanThrowHats svg #Hats").classList.toggle("start",false);
                                            },1000);
                                        },1000);
                                    },1000);
                                },500);
                                setTimeout(function(){
                                    document.getElementById("DTLLS_1").classList.toggle("start",false);
                                    document.getElementById("GraduanThrowHats").classList.toggle("start",false);
                                    document.querySelector("#GraduanThrowHats svg #Hands").classList.toggle("start",false);
                                    document.querySelector("#GraduanThrowHats svg #Peoples").classList.toggle("start",false);
                                    setTimeout(function(){
                                        document.getElementById("img-monitor").classList.toggle("start",true);
                                        setTimeout(function(){
                                            document.getElementById("YT-logo").classList.toggle("start",true);
                                            setTimeout(function(){
                                                document.getElementById("YT-logo").classList.toggle("start",false);
                                                setTimeout(function(){
                                                    document.getElementById("img-monitor").classList.toggle("start",false);
                                                    document.getElementById("LastScene").classList.toggle("start",true);
                                                    setTimeout(function(){
                                                        document.getElementById("LastScene").classList.toggle("start",false);
                                                        document.getElementById("playScr").style.display="";
                                                    },6000);
                                                },1000);
                                            },3500);
                                        },1500);
                                    },500);
                                },5500);
                            },3000);
                        },3000);
                    },5000);
                },1000);
            },true);
        },true);
        function delayedWordFadeIn0(element,delay_ms,fadeout_delay_ms){
            setTimeout(()=>{element.classList.toggle("word-fade-in",true);},delay_ms);
            delayedWordFadeOut(element,fadeout_delay_ms);
        }
        function delayedWordFadeOut(element,delay_ms){
            setTimeout(()=>{element.classList.toggle("word-fade-in",false);},delay_ms);
        }
        function delayedWordFadeIn(ele_enWord,startTimeAfterClick,duration_ms,timeFadeOut_ms,fadeOut_duration_ms){
            let ttl_count = ele_enWord.querySelectorAll("chara").length;let anm_interval = parseInt((duration_ms/ttl_count)+"");
            let anm_interval_fo = parseInt((fadeOut_duration_ms/ttl_count)+"");
            ele_enWord.querySelectorAll("chara").forEach((y,z)=>{
                delayedWordFadeIn0(y,startTimeAfterClick+(anm_interval*z),timeFadeOut_ms+(anm_interval_fo*z));
            });
        }
        function anm_cq0(){
            delayedWordFadeIn(document.querySelector("#cq-0 section:nth-child(1) cn-word:nth-child(1)"),0,1000,5000,500);
            delayedWordFadeIn(document.querySelector("#cq-0 section:nth-child(1) cn-word:nth-child(2)"),1000,1000,5000,500);
            delayedWordFadeIn(document.querySelector("#cq-0 section:nth-child(2) cn-word:nth-child(1)"),2000,1000,5000,500);
        }
        function anm_cq1(){
            delayedWordFadeIn(document.querySelector("#cq-1 section:nth-child(1) cn-word:nth-child(1)"),6000,750,11000,500);
            delayedWordFadeIn(document.querySelector("#cq-1 section:nth-child(1) cn-word:nth-child(2)"),6750,750,11000,500);
            delayedWordFadeIn(document.querySelector("#cq-1 section:nth-child(2) cn-word:nth-child(1)"),7500,750,11000,500);
            delayedWordFadeIn(document.querySelector("#cq-1 section:nth-child(3) cn-word:nth-child(1)"),8250,750,11000,500);
            delayedWordFadeIn(document.querySelector("#cq-1 section:nth-child(4) cn-word:nth-child(1)"),9000,750,11000,500);
        }
        function anm_cq2(){
            delayedWordFadeIn(document.querySelector("#cq-2 section:nth-child(1) cn-word:nth-child(1)"),12000,500,16000,500);
            delayedWordFadeIn(document.querySelector("#cq-2 section:nth-child(1) cn-word:nth-child(2)"),12500,500,16000,500);
            delayedWordFadeIn(document.querySelector("#cq-2 section:nth-child(1) cn-word:nth-child(3)"),13000,750,16000,500);
        }
        function anm_cq3(){
            delayedWordFadeIn(document.querySelector("#cq-3 section:nth-child(1) cn-word:nth-child(1)"),18000,500,22000,500);
            delayedWordFadeIn(document.querySelector("#cq-3 section:nth-child(1) cn-word:nth-child(2)"),18500,500,22000,500);
            delayedWordFadeIn(document.querySelector("#cq-3 section:nth-child(2) cn-word:nth-child(1)"),19000,750,22000,500);
            delayedWordFadeIn(document.querySelector("#cq-3 section:nth-child(3) cn-word:nth-child(1)"),19750,750,22000,500);
        }
        function anm_cq4(){
            delayedWordFadeIn(document.querySelector("#cq-4 section:nth-child(1) cn-word:nth-child(1)"),25000,500,30000,500);
            delayedWordFadeIn(document.querySelector("#cq-4 section:nth-child(1) cn-word:nth-child(2)"),25500,500,30000,500);
            delayedWordFadeIn(document.querySelector("#cq-4 section:nth-child(2) cn-word:nth-child(1)"),26000,750,30000,500);
        }
        function anm_eq0(){
            delayedWordFadeIn(document.querySelector("#eq-0 section:nth-child(1) en-word:nth-child(1)"),3000,750,6500,500);
            delayedWordFadeIn(document.querySelector("#eq-0 section:nth-child(1) en-word:nth-child(2)"),3750,750,6500,500);
            delayedWordFadeIn(document.querySelector("#eq-0 section:nth-child(2) en-word:nth-child(1)"),4500,500,6500,500);
            delayedWordFadeIn(document.querySelector("#eq-0 section:nth-child(2) en-word:nth-child(2)"),5000,500,6500,500);
        }
        function anm_eq1(){
            delayedWordFadeIn(document.querySelector("#eq-1 section:nth-child(1) en-word:nth-child(1)"),8000,1000,14000,500);
            delayedWordFadeIn(document.querySelector("#eq-1 section:nth-child(2) en-word:nth-child(1)"),9000,500,14000,500);
            delayedWordFadeIn(document.querySelector("#eq-1 section:nth-child(2) en-word:nth-child(2)"),9500,500,14000,500);
            delayedWordFadeIn(document.querySelector("#eq-1 section:nth-child(3) en-word:nth-child(1)"),10000,1000,14000,500);
            delayedWordFadeIn(document.querySelector("#eq-1 section:nth-child(4) en-word:nth-child(1)"),11000,1000,14000,500);
        }
        function anm_eq2(){
            delayedWordFadeIn(document.querySelector("#eq-2 section:nth-child(1) en-word:nth-child(1)"),15000,800,20000,500);
            delayedWordFadeIn(document.querySelector("#eq-2 section:nth-child(2) en-word:nth-child(1)"),15300,500,20000,500);
            delayedWordFadeIn(document.querySelector("#eq-2 section:nth-child(2) en-word:nth-child(2)"),15800,500,20000,500);
            delayedWordFadeIn(document.querySelector("#eq-2 section:nth-child(2) en-word:nth-child(3)"),15800,500,20000,500);
        }
        function anm_eq3(){
            delayedWordFadeIn(document.querySelector("#eq-3 section:nth-child(1) en-word:nth-child(1)"),21000,800,25000,500);
            delayedWordFadeIn(document.querySelector("#eq-3 section:nth-child(2) en-word:nth-child(1)"),21800,500,25500,500);
            delayedWordFadeIn(document.querySelector("#eq-3 section:nth-child(3) en-word:nth-child(1)"),22300,500,25500,500);
            delayedWordFadeIn(document.querySelector("#eq-3 section:nth-child(4) en-word:nth-child(1)"),22800,500,26000,500);
        }
        function anm_eq4(){
            delayedWordFadeIn(document.querySelector("#eq-4 section:nth-child(1) en-word:nth-child(1)"),27000,800,33000,500);
            delayedWordFadeIn(document.querySelector("#eq-4 section:nth-child(2) en-word:nth-child(1)"),27800,500,33500,500);
        }
    </script>
</body>
</html>
