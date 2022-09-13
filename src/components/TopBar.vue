<template>
  <div class="top-bar">
    <div class="container">
      <div class="welcome">Welcome to Corano Jewelry online store</div>
      <div class="options">
        <ul>
          <!-- <li @mouseover="currencyHover = true" @mouseleave="currencyLeave"> -->
          <li>
            $ Currency <i class="bi bi-chevron-down"></i>
            <!-- <ul v-show="currencyHover" :class="{ active: currencyHover, reverse: currencyReverse }"> -->
            <ul>
              <li>$ USD</li>
              <li>€ EURO</li>
            </ul>
          </li>
          <li>
            <img
              src="https://htmldemo.net/corano/corano/assets/img/icon/en.png"
              alt="English"
            />
            English <i class="bi bi-chevron-down"></i>
            <ul>
              <li>
                <img
                  src="https://htmldemo.net/corano/corano/assets/img/icon/en.png"
                  alt="English"
                />
                English
              </li>
              <li>
                <img
                  src="https://htmldemo.net/corano/corano/assets/img/icon/fr.png"
                  alt="French"
                />
                French
              </li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TopBar",
  // data() {
  //   return {
  //     currencyHover: false,
  //     currencyReverse: false,
  //   };
  // },
  // methods: {
  //   currencyLeave() {
  //     this.currencyReverse = true;
  //     setTimeout(() => {
  //       this.currencyHover = false;
  //       this.currencyReverse = false;
  //     }, 500);
  //   },
  // },
};
</script>

<style lang="scss" scoped>
$color-bg: #f4f4f4;
$color-text: #555555;
$color-white: #fff;
$color-gold: #c29958;
$color-border: #efefef;

// ul {
//   &.active {
//     list-style: none;
//     width: 150px;
//     padding: 30px 20px;
//     position: absolute;
//     top: 35px;
//     right: 0;
//     font-size: 0.8rem;
//     animation-name: slide;
//     animation-duration: 500ms;
//     background-color: $color-white;
//     color: $color-text;
//     border: solid 1px $color-border;
//     display: flex;
//     flex-direction: column;
//     align-items: flex-start;
//     gap: 15px;
//     @keyframes slide {
//       from {
//         top: 85px;
//       }
//       to {
//         top: 35px;
//       }
//     }
//     li {
//       transition: color 300ms;
//       &:hover {
//         color: $color-gold;
//       }
//     }
//   }
// }

.top-bar {
  height: 45px;
  background-color: $color-bg;
  color: $color-text;
  font-size: 0.875rem;
  border: $color-border solid 1px;
  .container {
    height: 100%;
    width: 75%;
    margin: 0 auto;
    padding: 0 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .welcome {
    }
    .options {
      height: 100%;
      > ul {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 30px;
        > li {
          height: 100%;
          position: relative;
          display: flex;
          justify-content: center;
          align-items: center;
          gap: 5px;
          cursor: pointer;
          i.bi {
            font-size: 0.7rem;
          }
          ul {
            display: none;
            height: auto;
            width: 150px;
            padding: 30px 20px;
            position: absolute;
            top: 35px;
            right: 0;
            opacity: 1;
            font-size: 0.8rem;
            animation-name: slide;
            animation-duration: 500ms;
            background-color: $color-white;
            color: $color-text;
            border: solid 1px $color-border;
            z-index: 10;
          }
          &:hover {
            ul {
              display: flex;
              flex-direction: column;
              align-items: flex-start;
              gap: 15px;
              @keyframes slide {
                from {
                  top: 85px;
                  opacity: 0;
                }
                to {
                  top: 35px;
                  opacity: 1;
                }
              }
              li {
                transition: color 300ms;
                &:hover {
                  color: $color-gold;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
