<template>
  <div class="footer">
    <div class="container">
      <div class="top">
        <div class="description">
          <div class="logo">
            <img src="@/assets/logo.png" alt="logo" />
          </div>
          <div class="desc">
            We are a team of designers and developers that create high quality
            wordpress, shopify, Opencart
          </div>
        </div>
        <div class="contact-us">
          <div class="title">Contact Us</div>
          <ul>
            <li>
              <i class="bi bi-house-door"></i
              ><span>4710-4890 Breckinridge USA</span>
            </li>
            <li>
              <i class="bi bi-envelope"></i><a href="#">demo@yourdomain.com</a>
            </li>
            <li>
              <i class="bi bi-telephone"></i
              ><a href="#">(012) 800 456 789-987</a>
            </li>
          </ul>
        </div>
        <div class="information">
          <div class="title">Information</div>
          <ul>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Delivery Information</a></li>
            <li><a href="#">Privet Policy</a></li>
            <li><a href="#">Terms & Conditions</a></li>
            <li><a href="#">Contact Us</a></li>
            <li><a href="#">Site Map</a></li>
          </ul>
        </div>
        <div class="follow-us">
          <div class="title">Follow Us</div>
          <ul>
            <li>
              <a href="#"><i class="bi bi-facebook"></i></a>
            </li>
            <li>
              <a href="#"><i class="bi bi-twitter"></i></a>
            </li>
            <li>
              <a href="#"><i class="bi bi-instagram"></i></a>
            </li>
            <li>
              <a href="#"><i class="bi bi-youtube"></i></a>
            </li>
          </ul>
        </div>
      </div>
      <div class="bottom">
        <div class="be-subscribe">
          <div class="title">Signup for newsletter</div>
          <div class="input">
            <input type="email" />
            <button>Subscribe</button>
          </div>
        </div>
        <div class="payment">
          <img
            src="https://htmldemo.net/corano/corano/assets/img/payment.png"
            alt="payment"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
$color-gold: #c29958;

.footer {
  padding: 80px 0;
  background-color: #f7f7f7;
  color: #555555;
  .container {
    width: 75%;
    margin: 0 auto;
    text-align: left;
    .top {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 50px;
      font-size: 0.85rem;
      line-height: 24px;
      @media (max-width: 992px) {
        grid-template-columns: repeat(2, 1fr);
        margin-bottom: 40px;
      }
      .description {
        .logo {
          margin-bottom: 20px;
        }
      }
      .contact-us {
        .title {
          margin-bottom: 20px;
          font-size: 1rem;
          font-weight: 700;
          color: #000;
        }
        ul {
          display: flex;
          flex-direction: column;
          gap: 7px;
          li {
            i.bi {
              font-size: 0.9rem;
              margin-right: 5px;
            }
            a {
              color: #555555;
              transition: all 400ms ease;
              &:hover {
                color: $color-gold;
                letter-spacing: 1px;
              }
            }
          }
        }
      }
      .information {
        .title {
          margin-bottom: 20px;
          font-size: 1rem;
          font-weight: 700;
          color: #000;
        }
        ul {
          display: grid;
          grid-template-columns: repeat(2, auto);
          row-gap: 10px;
          li {
            a {
              transition: all 400ms ease;
              color: #555555;
              &:hover {
                color: $color-gold;
              }
            }
          }
        }
      }
      .follow-us {
        .title {
          margin-bottom: 20px;
          font-size: 1rem;
          font-weight: 700;
          color: #000;
        }
        ul {
          display: flex;
          gap: 10px;
          li {
            a {
              height: 45px;
              width: 45px;
              display: flex;
              justify-content: center;
              align-items: center;
              color: #555555;
              background-color: #fff;
              font-size: 1.2rem;
              border: solid 1px #dedede;
              border-radius: 50%;
              transition: all 400ms ease;
              &:hover {
                background-color: $color-gold;
                color: #fff;
                border: solid 1px $color-gold;
              }
            }
          }
        }
      }
    }
    .bottom {
      margin-top: 20px;
      display: flex;
      justify-content: space-between;
      @media (max-width: 992px) {
        flex-direction: column;
      }
      .be-subscribe {
        width: 100%;
        @media (max-width: 992px) {
        flex-direction: column;
      }
        .title {
          margin-bottom: 20px;
          font-size: 1rem;
          font-weight: 700;
          color: #000;
        }
        .input {
          width: 100%;
          position: relative;
          border-bottom: #777777 solid 1px;
          input {
            color: #777777;
            width: 100%;
            height: 100%;
            padding: 10px 80px 10px 0;
            outline: none;
            border: none;
            background-color: transparent;
          }
          button {
            height: 100%;
            width: 80px;
            position: absolute;
            right: 0;
            cursor: pointer;
            border: none;
            background-color: transparent;
            font-weight: 700;
            font-size: 0.88rem;
            color: $color-gold;
            transition: all 400ms ease;
            &:hover {
              color: #000;
            }
          }
        }
      }
      .payment {
        align-self: flex-end;
        @media (max-width: 992px) {
          align-self: flex-start;
          margin-top: 20px;
        }
        img {
        }
      }
    }
  }
}
</style>
