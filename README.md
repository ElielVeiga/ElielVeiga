
## Eae, meu nome é Eliel Veiga, programador javascript 

<div style="display: inline_block"><br>
  <img align="center" alt="Rafa-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="Rafa-Ts" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-plain.svg">
  <img align="center" alt="Rafa-React" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original.svg">
  <img align="center" alt="Rafa-HTML" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original.svg">
  <img align="center" alt="Rafa-CSS" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original.svg">
</div>
  
  ##
 
<div> 
  <a href="https://www.instagram.com/eliel_737" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href = "mailto:elielveiga777@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/eliel-veiga-7407b6289" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  
</div>
<figure class="pac-man">
  <figcaption>Pac-Man</figcaption>
</figure>

<ul class="dots">
  <li class="dot"></li>
  <li class="dot"></li>
  <li class="dot"></li>
  <li class="dot"></li>
</ul>

<style>
$background: #000;
$pac-man:    #ffff00;
$border:     #171bff;
$dot:        #ffddd5;
//## Others
$size:       15vmin;
$dot-size:   $size / 6;
$time:       175;

html {
  box-sizing: border-box;
  padding: $size / 3;
  background: $background;
  height: 100%;
}
body {
  position: relative;
  margin: 0;
  box-sizing: border-box;
  background: $background; 
  border: $dot-size double $border;
  border-radius: $dot-size * 2;
  height: 100%;
  // overflow: hidden;
}


//** Animations
//
//## Setting up the animations for Pac Man's upper and lower mandibles
@keyframes chomp {
  0%   { transform: rotate(0);     }
  100% { transform: rotate(45deg); }
}

@keyframes travel {
  0% { right: -#{$dot-size}; }
  100% { right: 100%; }
}

@keyframes embiggen {
  0% { 
    width: $dot-size;
    height: $dot-size;
  }
  49.9% { 
    width: $dot-size;
    height: $dot-size;
  }
  50% { 
    width: $dot-size * 3;
    height: $dot-size * 3;
  }
  74.9% { 
    width: $dot-size * 3;
    height: $dot-size * 3;
  }
  75% { 
    width: $dot-size;
    height: $dot-size;
  }
  100% { 
    width: $dot-size;
    height: $dot-size;
  }
}


//** Pac Man
//
//## In all his chomping glory
.pac-man {
  display: block;
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 2;
  transform: translateX(-50%) translateY(-50%);
  margin: 0;
  width: $size;
  height: $size;
  
  &::before,
  &::after {
    position: absolute;
    top: 0;
    left: 0;
    background-size: 100% 100%; 
    border-radius: 50%;
    width: 100%;
    height: 100%;
    content: '';
  }
  
  &::before {
    background-image: linear-gradient(-45deg, transparent 50%, $pac-man 50%, $pac-man);
    animation: chomp #{$time}ms ease-in alternate infinite;
  }
  
  &::after {
    background-image: linear-gradient(-180deg, transparent 50%, $pac-man 50%, $pac-man);
    transform: rotate(45deg);
    animation: chomp #{$time}ms ease-out alternate-reverse infinite;
  }
  
  figcaption {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0,0,0,0);
    border: 0;
  }
}


//** Dots
//
//## Drawing and animation the dots to be eaten
.dots {
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 1;
  transform: translateX(#{$dot-size * -1.5}) translateY(-50%);
  width: calc(50% + #{$dot-size});
  height: $dot-size * 3;
  margin: 0;
  padding: 0;
  list-style: none;
  overflow: hidden;
}

.dot {
  position: absolute;
  top: 50%;
  right: -#{$dot-size};
  transform: translateY(-50%);
  background-color: $dot;
  border-radius: 37.5%;
  width: $dot-size;
  height: $dot-size;
  
  &:nth-child(1) {
    animation: 
      travel #{$time * 8}ms linear infinite,
      embiggen #{$time * 32}ms linear infinite;
  }
  &:nth-child(2) {
    animation: travel #{$time * 8}ms linear #{$time * 2}ms infinite;
  }
  &:nth-child(3) {
    animation: travel #{$time * 8}ms linear #{$time * 2 * 2}ms infinite;
  }
  &:nth-child(4) {
    animation: travel #{$time * 8}ms linear #{$time * 3 * 2}ms infinite;
  }
}
</style>
