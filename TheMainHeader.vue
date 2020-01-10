<template>
  <div>
    <div class="main-header">
      <div class="container">
        <div class="main-header-content">
          <div class="side-menu">
            <i class="fas fa-bars"></i>
            MENU
          </div>
          <div class="logo">
            <router-link tag="a" to="/">
              <img :src="require('@/assets/svg/logo.svg')" alt="" />
            </router-link>
          </div>
          <!-- Search for products -->
          <div class="search-products">
            <input type="text" name="" id="" placeholder="Search for products" />
            <select name="" id="">
              <option value="" disabled>Select Category</option>
              <option value="accessories">Accessories</option>
              <option value="cooks">Cooks</option>
              <option value="toys">Toys</option>
              <option value="clocks">Clocks</option>
              <option value="tables">Tables</option>
            </select>
            <div class="search-icon"><i class="fas fa-search"></i></div>
          </div>
          <!-- User action -->
          <div class="user-action">
            <div class="register">
              <a href="#">login</a>
              <a href="#">register</a>
            </div>
            <div class="shopping-cart">
              <a href="#">
                <i class="far fa-heart"></i>
              </a>
              <a href="#" class="relative">
                <i class="fas fa-random"></i>
                <span class="cart-count">
                  {{ cartCount }}
                </span>
              </a>
              <a href="#" class="relative">
                <i class="fab fa-opencart"></i>
                <span class="cart-count">
                  {{ cartCount }}
                </span>
              </a>
            </div>
          </div>
          <a href="#" class="products-cart">
            <i class="fab fa-opencart"></i>
            <span class="cart-count">
              {{ cartCount }}
            </span>
          </a>
        </div>
      </div>
    </div>
    <!-- Fixed bottom nav -->
    <div class="fixed-bottom-nav">
      <div class="item">
        <i class="fas fa-shopping-bag"></i>
        <span>Shop</span>
      </div>
      <div class="item">
        <i class="far fa-heart"></i>
        <span>WishList</span>
      </div>
      <div class="item">
        <i class="far fa-user"></i>
        <span>My Account</span>
      </div>
      <div class="item">
        <i class="fas fa-random"></i>
        <span>Compare</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cartCount: 0
    };
  }
};
</script>

<style scoped lang="scss">
.main-header {
  border-bottom: 1px solid #9e9e9e30;
  padding: 30px 0;

  // Main header content
  .main-header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-family: "Poppins", sans-serif;

    .side-menu,
    .products-cart {
      display: none;
    }

    // Logo
    .logo {
      img {
        max-width: 200px;
      }
    }

    // Search Products
    .search-products {
      border: 2px solid #9e9e9e30;
      display: flex;
      align-items: center;

      // input
      input {
        padding: 10px 8px;
        width: 350px;
        color: #848484;
        border: none;

        &:focus {
          outline: 0;
        }
      }

      // Select
      select {
        padding: 10px 0;
        border: none;
        border-left: 1px solid #9e9e9e30;
        text-align: center;
        color: #848484;
      }

      // Search icon
      .search-icon {
        display: block;
        padding: 10px;
        border-left: 1px solid #9e9e9e30;
        color: #848484;
      }
    }

    // User action
    .user-action {
      display: flex;
      justify-content: space-between;
      align-items: center;

      // User register
      .register {
        margin-right: 20px;
        a {
          text-transform: uppercase;
          color: #4c4444;
          font-size: 14px;
          margin-left: 12px;
          font-weight: 500;
        }
      }

      // Shopping cart
      .shopping-cart {
        width: 100px;
        justify-content: space-between;
        display: flex;

        a {
          color: #848484;
          font-weight: 700;

          // product in cart
          .cart-count {
            position: absolute;
            background: #83b735;
            color: #fff;
            font-weight: 100;
            height: 15px;
            width: 15px;
            text-align: center;
            font-size: 11px;
            border-radius: 50%;
            top: -5px;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 1200px) {
  .search-products {
    input {
      width: auto !important;
    }
  }
  .products-cart {
    display: none !important;
  }
}

@media screen and (max-width: 992px) {
  .side-menu {
    display: block !important;
  }
  .search-products,
  .user-action {
    display: none !important;
  }
  .products-cart {
    display: block !important;
    position: relative;

    .cart-count {
      position: absolute;
      background: #83b735;
      color: #fff;
      font-weight: 100;
      height: 15px;
      width: 15px;
      text-align: center;
      font-size: 11px;
      border-radius: 50%;
      top: -5px;
    }
  }
}

// Fixed bottom nav
.fixed-bottom-nav {
  position: fixed;
  bottom: 0;
  width: 100%;
  padding: 9px 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  box-shadow: 1px 1px 3px #333;
  font-family: "Poppins", sans-serif;
  display: none;

  .item {
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    font-size: 13px;
    text-transform: uppercase;
    color: #404040;

    span {
      margin-top: 4px;
      font-size: 11px;
    }
  }
}

@media screen and (max-width: 992px) {
  .fixed-bottom-nav {
    display: flex !important;
  }
}
</style>
