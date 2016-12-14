# css-balloonsy
Animation for catching helium balloon containing link (CSS only)

:green_apple: [**demo**](https://j-kallunki.github.io/css-balloonsy/)

Stylus (css):
```stylus
$color1 = #0099FF
$color1-light = #FFF8F6
$color2 = #FF6600

$container-height = 300px
$blocky-size = 60px

.blockgony // block style by author Joonas Kallunki
  .blocky-row
    clear left
  .blocky
    float left
    margin-right ($blocky-size*-.2)
    margin-bottom ($blocky-size*-.6)
  .blocky-middle
    display flex
    align-items center
    justify-content center
    float left
    width $blocky-size
    height $blocky-size
    text-align center
    font-size .8em
    font-weight 500
    text-decoration none
  a:hover .blocky-middle
    text-decoration underline
  &.blocky-even
    margin-top ($blocky-size*.5)
  &.blocky-white
    .blocky-middle
      background-color transparent
      border-color transparent

.balloonsy-container
  position relative
  height $container-height
  width 350px
  overflow hidden
  border solid 8px $color2
  border-radius 2px

.blockgony
  height 100%
  min-height 100%
  .blocky
    position relative
    animation flowup 12s linear infinite
    &:hover
      animation-play-state paused
    &:nth-child(2n)
      animation-duration 14s
    &:nth-child(3n)
      animation-duration 16s
  .blocky-middle
    color $color1-light
    background-color $color1
    transform rotate(40deg)
    border-radius 50% 50% 0 50%
  .blocky-text
    transform rotate(-40deg)  
  .blocky a:hover
    .blocky-middle
      animation bgrchange .4s ease-in forwards

@keyframes flowup
  0%
    transform translateY($container-height)
  100%
    transform translateY($blocky-size*-1.2)

@keyframes bgrchange
  to
    background-color $color2
```
JADE:
```jade
.balloonsy-container
  .blockgony.clearfix
      .blocky
        a(href="#")
          .blocky-middle
            .blocky-text Balloonsy
      .blocky.blocky-even
        a(href="#")
          .blocky-middle
            .blocky-text Balloon2
      .blocky.blocky-even
        a(href="#")
          .blocky-middle
            .blocky-text Balloon3
      .blocky
        a(href="#")
          .blocky-middle
            .blocky-text Balloon4
      .blocky.blocky-even
        a(href="#")
          .blocky-middle
            .blocky-text Balloon5
      .blocky
        a(href="#")
          .blocky-middle
            .blocky-text Balloon6
      .blocky.blocky-even
        a(href="#")
          .blocky-middle
            .blocky-text Balloon7
```
