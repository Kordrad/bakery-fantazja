<template>
    <div>
      <img :src="image" v-bind:alt="alt"/>
      <div>
        <h1>{{title}}</h1>
        <p>
          {{description}}
        </p>
      </div>
    </div>
</template>

<script>
export default {
  name: 'icons',
  props: {
    title: {
      type: String,
      default: 'Lorem Ipsum',
    },
    description: {
      type: String,
      default: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi odio neque, posuere nec placerat a, pretium ultricies velit.',
    },
    image: {
      type: String,
      default: require('../assets/img/icons/cake.svg'),
    },
    alt: {
      type: String,
      default: 'Image',
    },
  },
};
</script>

<style lang="scss" scoped>
  @mixin leaf($color) {
    background-image: url("data:image/svg+xml;charset=UTF-8,%3c?xml version='1.0' encoding='UTF-8' standalone='no'?%3e%3c!-- Created with Inkscape (http://www.inkscape.org/) --%3e%3csvg xmlns:dc='http://purl.org/dc/elements/1.1/' xmlns:cc='http://creativecommons.org/ns%23' xmlns:rdf='http://www.w3.org/1999/02/22-rdf-syntax-ns%23' xmlns:svg='http://www.w3.org/2000/svg' xmlns='http://www.w3.org/2000/svg' xmlns:sodipodi='http://sodipodi.sourceforge.net/DTD/sodipodi-0.dtd' xmlns:inkscape='http://www.inkscape.org/namespaces/inkscape' version='1.1' id='svg4537' width='2621.3333' height='1153.3333' viewBox='0 0 2621.3333 1153.3333' sodipodi:docname='leaf.svg' inkscape:version='0.92.4 (5da689c313, 2019-01-14)'%3e%3cmetadata id='metadata4543'%3e%3crdf:RDF%3e%3ccc:Work rdf:about=''%3e%3cdc:format%3eimage/svg+xml%3c/dc:format%3e%3cdc:type rdf:resource='http://purl.org/dc/dcmitype/StillImage' /%3e%3cdc:title%3e%3c/dc:title%3e%3c/cc:Work%3e%3c/rdf:RDF%3e%3c/metadata%3e%3cdefs id='defs4541' /%3e%3csodipodi:namedview pagecolor='%23ffffff' bordercolor='%23666666' borderopacity='1' objecttolerance='10' gridtolerance='10' guidetolerance='10' inkscape:pageopacity='0' inkscape:pageshadow='2' inkscape:window-width='1920' inkscape:window-height='1001' id='namedview4539' showgrid='false' inkscape:zoom='0.42404828' inkscape:cx='1061.2467' inkscape:cy='822.69169' inkscape:window-x='-9' inkscape:window-y='-9' inkscape:window-maximized='1' inkscape:current-layer='svg4537' /%3e%3cpath style='fill:%23#{$color};fill-opacity:1;stroke-width:3.3350296' d='M 2.8669094,1137.803 C 2.9789881,1117.6242 17.524691,1042.831 33.123233,982.2267 62.846394,866.74463 115.48113,740.22948 175.57428,639.82508 282.81033,460.65375 425.32443,326.72615 605.20355,236.08109 711.18602,182.67418 822.91258,146.67278 944.95132,126.60492 c 96.48818,-15.86637 149.46298,-19.742 268.46988,-19.64116 115.4805,0.0978 146.8082,2.71025 225.1145,18.77226 22.0112,4.51489 49.7753,9.1532 61.698,10.30737 154.3908,14.9456 245.6069,19.22938 420.2138,19.73449 116.9964,0.33845 170.0535,-0.72765 191.7642,-3.8532 65.5684,-9.43949 78.2337,-11.51582 118.3935,-19.40935 120.5485,-23.69412 281.4735,-76.795112 374.5357,-123.5869367 l 16.0201,-8.05489143 -1.8405,10.98555313 c -1.0123,6.042054 -4.1461,25.993185 -6.964,44.335848 -31.1963,203.064777 -122.1097,414.926537 -246.0862,573.472047 -33.4849,42.82161 -38.6697,48.58071 -88.8036,98.6415 -82.9974,82.87622 -158.5626,137.35346 -263.3049,189.82455 -117.2139,58.71876 -225.9775,91.5942 -380.5269,115.0199 -60.6031,9.1859 -120.8537,12.6622 -221.7794,12.7962 -117.8194,0.1565 -142.1536,-1.7544 -221.7795,-17.4158 -60.223,-11.845 -137.4263,-19.6483 -270.13741,-27.3041 -97.14504,-5.60402 -369.66975,-5.7627 -410.20863,-0.2388 -118.86006,16.196 -201.51218,34.8602 -308.49024,69.6623 -41.74668,13.581 -125.264786,46.176 -160.348446,62.5799 -37.3749446,17.4752 -38.0965233,17.562 -38.0243646,4.5704 z' id='path4553' inkscape:connector-curvature='0' /%3e%3c/svg%3e ");
  }
  img{
    width: 100%;
  }
  h1 {
    display: inline-block;
    left: 50%;
    transform: translateX(-50%);
    position: relative;
    $height: 15px;
    $padding: 15px;
    font-weight: 400;
    color: #743629;
    &:before, &:after {
      content: "";
      position: absolute;
      white-space: pre;
      min-height: $height;
      min-width: $height*2;
      display: block;
      @include leaf(743629);
      background-size: contain;
      background-position: center center;
      background-repeat: no-repeat;
      top: 50%;
    }

    &:before {
      left: (-$height*2)-$padding;
      /*transform: translate(50%);*/
      transform: scaleX(-1) translateY(-50%);
    }

    &:after {
      right: (-$height*2)-$padding;
      transform: translateY(-50%);
    }
  }

  p {
    font-style: italic;
    font-weight: 300;
    color: #333;
  }

  h1, p {
    text-align: center;
  }
</style>
