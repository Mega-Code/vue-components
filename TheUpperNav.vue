<template>
  <div class="upper-nav">
    <div class="container">
      <div class="upper-nav-content">
        <ul class="left-side">
          <li
            class="langs brd-lft-rgh"
            @mouseenter="showLangsMenu = true"
            @mouseleave="showLangsMenu = false"
          >
            english
            <i class="fas fa-chevron-down"></i>
            <!-- Langs menu -->
            <transition name="fade">
              <ul class="langs-menu" v-show="showLangsMenu">
                <li>english</li>
                <li>frensh</li>
                <li>espaniol</li>
              </ul>
            </transition>
          </li>
          <li
            class="country brd-rgh"
            @mouseenter="showCountryMenu = true"
            @mouseleave="showCountryMenu = false"
          >
            country
            <i class="fas fa-chevron-down"></i>
            <!-- Langs menu -->
            <transition name="fade">
              <ul class="country-menu" v-show="showCountryMenu">
                <li>united state (USD)</li>
                <li>frensh (EUR)</li>
                <li>jaban (YEN)</li>
              </ul>
            </transition>
          </li>
          <p>FREE SHIPPING FOR ALL ORDERS OF $150</p>
        </ul>
        <div class="contact-us">
          <ul class="social-media">
            <li>
              <a href="#"><i class="fab fa-facebook-f"></i></a>
            </li>
            <li>
              <a href="#"><i class="fab fa-twitter"></i></a>
            </li>
            <li>
              <a href="#"><i class="fab fa-youtube"></i></a>
            </li>
            <li>
              <a href="#"><i class="fab fa-instagram"></i></a>
            </li>
          </ul>
          <div class="links">
            <a href="#" class="brd-lft">newsletter</a>
            <a href="#" class="brd-lft">contact us</a>
            <a href="#" class="brd-lft-rgh">faqs</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showLangsMenu: false,
      showCountryMenu: false
    };
  }
};
</script>

<style scoped lang="scss">
.upper-nav {
  background-color: #83b735;
  text-transform: uppercase;
  font-size: 12px;
  font-family: "Poppins", sans-serif;

  .upper-nav-content {
    display: flex;
    justify-content: space-between;
    align-items: center;

    // Left side
    .left-side {
      display: flex;
      justify-content: space-between;
      color: #fff;

      li {
        cursor: pointer;
        padding: 15px 10px;
      }
      p {
        padding: 15px 17px;
      }
      i {
        margin-left: 4px;
        font-size: 10px;
      }

      // Languages menu
      .langs {
        position: relative;

        .langs-menu {
          position: absolute;
          background: #fff;
          color: #797979;
          padding: 5px 0;
          text-transform: capitalize;
          width: 150px;
          z-index: 1000;
          top: 50px;
          box-shadow: 1px 1px 2px #33333363;

          li {
            padding: 12px 10px;
            font-size: 13px;
            margin: 0;
            transition: all 0.2s ease-in;

            &:hover {
              background: #7373732e;
            }
          }
        }
      }
      // Country Menu
      .country {
        position: relative;
        // border-right: 1px solid #dedddd61;

        .country-menu {
          position: absolute;
          background: #fff;
          color: #797979;
          padding: 5px 0;
          text-transform: capitalize;
          width: 150px;
          z-index: 1000;
          top: 50px;
          box-shadow: 1px 1px 2px #33333363;

          li {
            padding: 12px 10px;
            font-size: 13px;
            margin: 0;
            transition: all 0.2s ease-in;

            &:hover {
              background: #7373732e;
            }
          }
        }
      }
    }

    // Right Side (contact us)
    .contact-us {
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 400px;

      // Social meida
      .social-media {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 120px;
        font-size: 16px;

        li {
          a {
            color: #fff !important;
            &:hover {
              color: #e6e6e6e8 !important;
            }
          }
        }
      }
      .links {
        a {
          padding: 15px 10px;
          color: #fff;
          &:hover {
            color: #e6e6e6e8;
          }
        }
      }
    }
  }
}

// Vue transition
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
