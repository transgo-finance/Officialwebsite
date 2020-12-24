<template>
  <div class="home">
    <header class="header-wrapper">
      <div class="logo-wrapper">
        <img class="logo" src="../assets/logo.svg" alt="logo" />
        <!-- <span>Transgo</span> -->
      </div>

      <div class="language-wrapper">
        <!-- <select v-model="lang" name="lang" id="lang" @change="getVal">
          <option value="en">English</option>
          <option value="zh">中文</option>
        </select> -->
        <span @click="changeLang('en')" class="lang" :class="[lang === 'en' ? 'activeLang' : '']">En</span>
        <span @click="changeLang('zh')" class="lang" :class="[lang === 'zh' ? 'activeLang' : '']">中</span>
      </div>
    </header>

    <main class="main-wrapper">
      <section class="first-section-container">
        <div class="first-section-wrapper">
          <img class="leftLogo" src="../assets/leftLogo.svg" alt="leftLogo" />
          <div class="content-item">
            <h1>{{ $t('section1.t1') }}</h1>
            <h1 class="mt10">{{ $t('section1.t2') }}</h1>
            <button class="launchBtn">COMING SOON</button>
          </div>
          <img class="rightLogo" src="../assets/rightLogo.svg" alt="rightLogo" />
        </div>
      </section>

      <section class="second-section-container">
        <div class="second-section-wrapper">
          <div class="content-item">
            <p class="title">{{ $t('section2.item1.t1') }}</p>
            <div class="img-item">
              <img src="../assets/smallLogo.svg" alt="small logo" />
            </div>
            <!-- <p class="subtitle">跨链解决方案</p> -->
            <p class="intro">
              {{ $t('section2.item1.i1') }}
            </p>
          </div>

          <div class="content-item">
            <p class="title">{{ $t('section2.item2.t1') }}</p>
            <div class="img-item">
              <img src="../assets/smallLogo.svg" alt="small logo" />
            </div>
            <!-- <p class="subtitle">跨链资产迁移</p> -->
            <p class="intro">{{ $t('section2.item2.i1') }}</p>
          </div>

          <div class="content-item">
            <p class="title">{{ $t('section2.item3.t1') }}</p>
            <div class="img-item">
              <img src="../assets/smallLogo.svg" alt="small logo" />
            </div>
            <!-- <p class="subtitle">跨链资产迁移</p> -->
            <p class="intro">
              {{ $t('section2.item3.i1') }}
            </p>
          </div>

          <div class="content-item">
            <p class="title">{{ $t('section2.item4.t1') }}</p>
            <div class="img-item">
              <img src="../assets/smallLogo.svg" alt="small logo" />
            </div>
            <!-- <p class="subtitle">跨链资产迁移</p> -->
            <p class="intro">{{ $t('section2.item4.i1') }}</p>
          </div>
        </div>
      </section>

      <section class="third-section-container">
        <div class="section-title-wrapper">
          <div class="title">
            <h3>{{ $t('section3.t1') }}</h3>
            <span class="bottom-bg"></span>
          </div>
        </div>
        <div class="third-section-wrapper">
          <img class="slide-img" src="../assets/slide.svg" alt="slide" />
          <div class="content-item">
            <div class="item-wrapper">
              <p class="title-content">
                <span class="num">1</span>
                <span class="title">{{ $t('section3.item1.t1') }}</span>
              </p>
              <p class="intro-wrapper">{{ $t('section3.item1.i1') }}</p>
            </div>

            <div class="item-wrapper">
              <p class="title-content">
                <span class="num">2</span>
                <span class="title">{{ $t('section3.item2.t1') }}</span>
              </p>
              <p class="intro-wrapper">
                {{ $t('section3.item2.i1') }}
              </p>
            </div>

            <div class="item-wrapper">
              <p class="title-content">
                <span class="num">3</span>
                <span class="title">{{ $t('section3.item3.t1') }}</span>
              </p>
              <p class="intro-wrapper">
                {{ $t('section3.item3.i1') }}
              </p>
            </div>

            <div class="item-wrapper">
              <p class="title-content">
                <span class="num">4</span>
                <span class="title">{{ $t('section3.item4.t1') }}</span>
              </p>
              <p class="intro-wrapper">{{ $t('section3.item4.i1') }}</p>
            </div>
          </div>
        </div>
      </section>

      <section class="last-section-container">
        <div class="section-title-wrapper">
          <div class="title">
            <h3>{{ $t('section4.t1') }}</h3>
            <span class="bottom-bg"></span>
          </div>
        </div>
        <timeline class="timeline-section"></timeline>
      </section>
    </main>

    <footer class="footer-wrapper">
      <div class="left-wrapper">
        <img src="../assets/logo.svg" alt="logo" />
        <p>&copy; 2020 Copyrights</p>
      </div>
      <div class="right-wrapper">
        <a href="#" class="item">
          <img src="../assets/telegram.svg" alt="telegram" />
        </a>
        <a href="https://twitter.com/transgoofficial" target="_blank" class="item">
          <img src="../assets/twitter.svg" alt="twitter" />
        </a>
        <a href="https://medium.com/transgo" target="_blank" class="item">
          <img src="../assets/medium.svg" alt="medium" />
        </a>
      </div>
    </footer>
  </div>
</template>

<script>
import jscookie from 'js-cookie';
export default {
  name: 'Home',
  data() {
    return {
      lang: 'zh',
    };
  },
  components: {
    timeline: () => import('../components/timeline.vue'),
  },
  methods: {
    changeLang(val) {
      let lang = val;
      this.lang = lang;
      jscookie.set('langkey', this.lang, { expires: 180 });
      this.$i18n.locale = lang;
    },

    initLang() {
      let langkey = jscookie.get('langkey');
      this.lang = langkey;
      this.$i18n.locale = this.lang;
    },
  },
  mounted() {
    this.initLang();
  },
};
</script>

<style lang="less" scoped>
@import './home/media.less';

.home {
  width: 100%;
  height: 100%;
  .header-wrapper {
    margin-top: 20px;
    width: 100%;
    overflow: hidden;
    .language-wrapper {
      .lang {
        display: inline-block;
        text-align: center;
        width: 40px;
        height: 40px;
        line-height: 40px;
        color: #fff;
        font-size: 16px;
        background-color: transparent;
        cursor: pointer;
      }

      .activeLang {
        border-radius: 100%;
        background-color: #fff;
        color: #000;
        font-weight: 600;
        font-size: 16px;
      }
    }
  }
  .main-wrapper {
    .first-section-container {
      .first-section-wrapper {
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        .content-item {
          text-align: center;
          h1 {
            color: #fff;
            font-weight: 400;
          }
          .launchBtn {
            outline: none;
            background-color: transparent;
            color: #fff;
            font-weight: 400;
            border: 1px solid #fff;
            border-radius: 6px;
            cursor: pointer;
          }
        }
      }
    }

    .second-section-container {
      width: 100%;
      margin-top: 30px;
      margin-bottom: 30px;
      .second-section-wrapper {
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        flex-wrap: wrap;
        .content-item {
          margin-top: 20px;
          padding: 30px 10px 35px 28px;
          background: linear-gradient(155deg, #020961 0%, #0a134f 100%);
          border-radius: 11px;
          .title {
            font-size: 26px;
            font-weight: 400;
            color: #ffffff;
            line-height: 37px;
          }
          .img-item {
            margin-top: 15px;
            width: 63px;
            height: 63px;
            margin-bottom: 24px;
            img {
              max-width: 100%;
            }
          }
          .subtitle {
            // margin-top: 24px;
            font-size: 18px;
            font-weight: 600;
            color: #275fe1;
            line-height: 25px;
          }
          .intro {
            margin-top: 10px;
            font-size: 13px;
            font-weight: 600;
            color: #ffffff;
            line-height: 18px;
          }
        }
      }
    }

    .third-section-container {
      width: 100%;
      margin-top: 100px;
      .third-section-wrapper {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
        .content-item {
          .item-wrapper {
            margin-top: 30px;
            .title-content {
              .num {
                margin-right: 30px;
                font-size: 50px;
                font-weight: 600;
                color: #101f5a;
                line-height: 70px;
              }
              .title {
                font-weight: 600;
                color: #ffffff;
                line-height: 40px;
              }
            }
            .intro-wrapper {
              margin-left: 60px;
              color: #ffffff;
              line-height: 18px;
            }
          }
        }
      }
    }

    .last-section-container {
      width: 100%;
      margin-top: 100px;
    }
  }

  .footer-wrapper {
    padding: 40px 65px;
    .left-wrapper {
      text-align: center;
      p {
        margin-top: 10px;
        font-size: 13px;
        color: #ffffff;
        line-height: 18px;
      }
    }
    .right-wrapper {
      margin-top: 36px;
      .item {
        margin-right: 20px;
      }
    }
  }
}
.section-title-wrapper {
  text-align: center;
  .title {
    width: 190px;
    height: 56px;
    margin: 0 auto;
    position: relative;
    h3 {
      position: absolute;
      bottom: 4px;
      left: 50%;
      transform: translateX(-50%);
      color: #fff;
      font-size: 30px;
      z-index: 5;
    }
    span {
      position: absolute;
      bottom: 0;
      left: 0;
      display: inline-block;
      width: 100%;
      padding: 10px 5px;
      background-color: #101f5a;
    }
  }
}
</style>