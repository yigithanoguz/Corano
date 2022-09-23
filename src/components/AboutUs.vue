<template>
  <div class="about-us">
    <div class="container">
      <img
        src="https://htmldemo.net/corano/corano/assets/img/about/about.jpg"
        alt=""
      />
      <div class="content">
        <div class="title">About Us</div>
        <div class="summary">
          Founded in 1986, I.D. Jewelry, LLC, a family owned & operated business
          has become a house-hold name in states all over the USA as well as
          countries all over the world.
        </div>
        <p>
          For those that rather the full immersion of the in store experience we
          welcome your company and look forward to meeting you face to face.
          Being located in the 47 street diamond district, known to be the
          largest diamond.
        </p>
        <p>
          Based in the heart of New York’s Diamond District, also known as the
          NYC diamond district, I. D. Jewelry has some of the most competitively
          priced in the market. It is our goal to supply our clients.
        </p>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.about-us {
  height: 530px;
  width: 100%;
  margin-top: 80px;
  @media (max-width: 1200px) {
      height: auto;
    }
  .container {
    height: 100%;
    width: 75%;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 30px;
    @media (max-width: 1200px) {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    @media (max-width: 576px) {
      width: 100%;
      padding: 0 20px;
    }
    img {
      // width: 100%;
      height: 100%;
    }
    .content {
      display: flex;
      flex-direction: column;
      justify-content: center;
      text-align: left;
      @media (max-width: 1200px) {
        text-align: center;
        padding: 0 100px;
      }
      @media (max-width: 992px) {
        padding: 0;
      }
      gap: 30px;
      .title {
        font-size: 3.25rem;
        font-weight: 700;
        color: #d1d1d1;
      }
      .summary {
        font-size: 1.2rem;
        font-weight: 700;
        color: #000;
        line-height: 26px;
      }
      p {
        font-size: 0.95rem;
        color: #555555;
        line-height: 26px;
      }
    }
  }
}
</style>
