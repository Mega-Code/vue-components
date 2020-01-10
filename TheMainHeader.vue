<template>
  <div>
    <div class="main-header">
      <div class="container">
        <div class="main-header-content">
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
        </div>
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
</style>
