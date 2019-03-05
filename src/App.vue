<template>
  <div id="app">
    <indicator></indicator>
    <div class="cover" :style="{'background-image': 'url(' + srcRWD(cover, coverWeb) + ')' }" ref="beginning">
      <div class="cover-title">
        <h3>
          BR：嘻哈就是我畢生的事業<br>我要衝出台灣
        </h3>
      </div>
    </div>
    <div class="back-to-home" ref="home" :class="{ 'hidden-home' : isShowHome }">
      <a class="home" href="https://udn.com/upf/ubrand/2019_data/DaretoDream/index.html">
        <img :src="srcRWD(home, homeWeb)" alt="">
        HOME
      </a>
    </div>
    <br>
    <content-container>
      <div>
        <share href="https://udn.com/upf/ubrand/2019_data/DaretoDream_BR/index.html"></share>
      </div>
      <br>
      <div class="title-track-same-month">
         <youtube src="https://www.youtube.com/embed/p54sxKiKghM"></youtube>
      </div>
      <br>
      <p>一般人鮮少接觸嘻哈音樂(HIP-POP)，可能會對BR這個名字感覺陌生，可是對華語饒舌圈來說，這個名字卻是一股不可忽視的嘻哈新勢力。</p>
      <br>
      <p>旁人眼中的BR是個學霸，大學跟研究所都念台大。據他本人的說法是為了持續鑽研嘻哈，他才跑去念台大。只是沒想到剛進台大，學校的嘻研社團就因無人經營，面臨廢社命運。為了重振社團，BR花了很多心力跟時間，光是大一上學期就差點搞到二一。</p>
      <br>
      <p>大二時為了轉系，他捲土重來參加轉學考，照樣考回台大，順利從地理系轉到生物產業機電工程學系，像這樣跨領域、跨專業、唸書、考試彷彿都是輕而易舉的小事情，因為對BR來說，<b>玩嘻哈才是真正的大事情</b>。</p>
      <br>
      <column-one description="鏡頭裡總是冷酷的BR，其實內心溫暖易感，跟外表有極大反差。" src="@/../static/pic1.png" src-web="@/../static/pic1_web.png"></Column-One>
      <br>
      <h3>獎項只是一個鼓勵　<br class="mobile-only">不代表你比所有人厲害</h3>
      <br>
      <p>BR大三那年，他參加一場指標性的Freestyle大賽，他用連珠炮的快嘴與精深的歌詞韻腳，擊潰了華語饒舌圈的資深大腕，自此他一戰成名，被譽為饒舌圈的「Freestyle戰神」，成為眾所期待的新星。但他並不因此自滿，「我覺得獎項是一個鼓勵，並不是得到那個獎，你就比所有人厲害。<b>重點在於你沒有得那個獎的時候，有沒有辦法說服自己，我就是那麼厲害。</b>」</p>
      <br>
      <column-one description="BR拿出自己珍藏的CD，像老師一樣一一細數嘻哈樂壇的進化史。" src="@/../static/pic2.png" src-web="@/../static/pic2_web.png"></Column-One>
      <br>
      <h3>衝出台灣　<br class="mobile-only">向頂尖一流饒舌歌手看齊</h3>
      <br>
      <p>有點小害羞地說到夢想要跟偶像Wiz Kalifa合作時，BR的眼神都亮了起來。為了能更接近偶像，跟全球一線頂尖的饒舌歌手看齊，BR放眼國際市場，替自己設定「衝出台灣」的目標。現在他每天勤於練習Freestyle創作，隨時追蹤嘻哈音樂脈動，只要一聽到喜歡的歌就會買實體CD回家收藏。「我把嘻哈當作是我畢生的事業在做，因此我對自己的期許就是做出對這個時代好的音樂，用我的方式跟我的經歷做出來。」</p>
      <br>
      <column-one description="BR說，當饒舌歌手就要有自己的價值觀，必須不斷挖掘自己，講一些真實的東西。" src="@/../static/pic3.png" src-web="@/../static/pic3_web.png"></Column-One>
      <br>
      <h3>想往上爬　<br class="mobile-only">就不畏築夢時的艱辛</h3>
      <br>
      <p>然而，近兩年台灣樂壇吹起一陣嘻哈風潮，新一代嘻哈歌手輩出，很多早關注BR的粉絲開始替他著急怎麼還在原地踏步？甚至不那麼BR了？為此，BR坦言，過去一年當替代役錯過上舞台的機會，但這不會因此改變他的計畫，「我已經制定好了目標跟執行計畫，現在就是一步一步實質地把我腦袋裡想的東西做出來。」</p>
      <br>
      <p>「我知道台灣的環境，大家會覺得務實一點比較好，可是總是要有人去敢做這些事，敢去想這些事，知道怎麼把夢建築起來，但我想要往上爬，就必須要承受創新的過程有很多的不解跟批評。我知道我的優點是我一直有在進步，我不怕，但我要把它做出來。」</p>
      <br>
      </content-container>
      <content-container class="web-only" style="background-image: linear-gradient(to bottom, #f2f2f2, rgba(255, 255, 255, 0)); ">
      <div class="anchor-web">
        <h3 class="anchor-web-title">點看其他人物故事</h3>
        <ul>
          <li v-for="item in profiles" :key="item.id" :class="{ shake: item.isLock }">
            <a :href="item.link">
              <img :src="item.profile_web"  @click="handleLinkTo(item.isLock, item.idTo, $event)" alt="">
              <div class="describe">
                <p>{{ item.title }}</p>
                <p>{{ item.name }}</p>
             </div>
            </a>
          </li>
        </ul>
      </div>
      </content-container>
      <div class="anchor-mobile">
        <h3 class="anchor-mobile-title">點看其他人物故事</h3>
        <ul>
          <li v-for="item in profiles" :key="item.id" :class="{ shake: item.isLock }">
            <a :href="item.link">
              <img :src="item.profile"  @click="handleLinkTo(item.isLock, item.idTo, $event)" alt="">
              <div class="describe">
                <p>{{ item.title }}</p>
                <p>{{ item.name }}</p>
             </div>
            </a>
          </li>
        </ul>
      </div>
      <content-container>
      <br>
      <div class="share-and-logo">
        <div class="share">
          <share href="https://udn.com/upf/ubrand/2019_data/DaretoDream_BR/index.html"></share>
        </div>
        <div class="logo">
          <logo use-ubrand="yes" use-vision='no'>
            <div>
              <img :src="logo" alt="">
            </div>
          </logo>
        </div>
      </div>
      <p><br></p>
      <editor>
        <div>文字採訪：林筱穎</div>
        <div>影音製作：劉宜峰</div>
        <div>視覺設計：呂宗原</div>
        <div>網頁製作：胡凈悟、吳偉賢</div>
        <div>議題行銷：張乃文、陳欣媛、王敏霏</div>
        <div>監製：潘如瑩、董谷音、蔡幸怡、陳曼薇</div>
        <div>2019.3.15</div>
      </editor>
      <p><br></p>
      <fb-comment href="https://udn.com/upf/ubrand/2019_data/DaretoDream_BR/index.html"></fb-comment>
    </content-container>
    <back-top></back-top>
    <back-home></back-home>
    <foot></foot>
  </div>
</template>

<script>
import Vue from 'vue'
import srcRWD from '@/mixin/srcRWD.js'
import globalComponents from '@/plugins/baseComponents.js'
import videoBox from '@/components/videoBox.vue'
import backHome from '@/components/backHome.vue'

Vue.use(globalComponents)

export default {
  name: 'App',
  mixins: [srcRWD],
  components: {
    videoBox,
    backHome
  },
  data () {
    return {
      isShowHome: false,
      cover: require('@/../static/cover.png'),
      coverWeb: require('@/../static/cover_web.png'),
      logo: require('@/../static/logo.png'),
      home: require('@/../static/home.png'),
      homeWeb: require('@/../static/homeWeb.png'),
      profiles: [
      {
        id: 'duncan_btn',
        idTo: 'duncan',
        title: '圖文創作者',
        name: 'Duncan',
        profile: require('@/../static/profiles/duncan.png'),
        profile_web: require('@/../static/profiles/duncan_web.png'),
        link: 'https://udn.com/upf/ubrand/2019_data/DaretoDream_Duncan/index.html',
        isLock: false
      },
      {
        id: 'br_btn',
        idTo: 'br',
        title: '饒舌歌手',
        name: 'BR',
        profile: require('@/../static/profiles/br.png'),
        profile_web: require('@/../static/profiles/br_web.png'),
        link: 'https://udn.com/upf/ubrand/2019_data/DaretoDream_BR/index.html',
        isLock: false
      },
      {
        id: 'angel_btn',
        idTo: 'angel',
        title: '小提琴手',
        name: 'Angel',
        profile: require('@/../static/profiles/angel.png'),
        profile_web: require('@/../static/profiles/angel_web.png'),
        link: 'https://udn.com/upf/ubrand/2019_data/DaretoDream_Angel/index.html',
        isLock: false
      },
      {
        id: 'anonymous2_btn',
        idTo: 'anonymous2',
        title: '4月',
        name: '即將推出',
        profile: require('@/../static/profiles/lock.png'),
        profile_web: require('@/../static/profiles/lock_web.png'),
        link: '.',
        isLock: true
      },
      {
        id: 'anonymous3_btn',
        idTo: 'anonymous3',
        title: '5月',
        name: '即將推出',
        profile: require('@/../static/profiles/lock.png'),
        profile_web: require('@/../static/profiles/lock_web.png'),
        link: '.',
        isLock: true
      },
      {
        id: 'anonymous4_btn',
        idTo: 'anonymous4',
        title: '6月',
        name: '即將推出',
        profile: require('@/../static/profiles/lock.png'),
        profile_web: require('@/../static/profiles/lock_web.png'),
        link: '.',
        isLock: true
      }]
    }
  },
  methods: {
    handleLinkTo (isLock ,idTo ,event) {

      let label = "[DaretoDream_BR][" + idTo + "][外連到" + idTo + "]"

      if(isLock) {
        label = "[DaretoDream_BR][" + idTo + "][目前無法外連]"
        event.preventDefault()
      }

      window.ga("send", {
        "hitType": "event",
        "eventCategory": "OptionButton",
        "eventAction": "click",
        "eventLabel": label
      })
    },
    handle_scroll () {
      let currentHeight = window.pageYOffset
      if (currentHeight > 0) {
        this.isShowHome = true
      } else {
        this.isShowHome = false
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handle_scroll)
  },
  destroyed () {
    window.removeEventListener('scroll', this.handle_scroll)
   }
}
</script>

<style  lang="scss">
@import './assets/CSS/theme.css';
@import './assets/CSS/UdnFontSize.css';

html, body {
  margin: 0;
  padding: 0;
}
#app {
    font-family: Microsoft JhengHei;
    .web-only {
      @media screen and (max-width: 768px) {
        display: none;
      }
      @media screen and (min-width: 768px) and (max-width: 1023px) {
          display: none;
      }
    }
    .mobile-only {
      @media screen and (min-width: 768px) and (max-width: 1023px) {
        display: none;
      }
      @media screen and (min-width: 1024px) {
        display: none;
      }
    }
    .cover {
      position: relative;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
      height: 100vh;
      .main-cover {
        width: 100%;
      }
      .cover-title {
        width: 100%;
        background-color: rgba(#e60414, 0.6);
        position: absolute;
          bottom: 110px;
          left: 0;
        @media screen and (min-width: 768px) and (max-width: 1023px) {
          bottom: 0;
        }
        @media screen and (min-width: 1024px) {
          bottom: 0;
        }
        h3 {
          margin: 0px;
          padding: 9px 15px 12px 15px;
          color: white;
          font-weight: bolder;
          @media screen and (min-width: 768px) and (max-width: 1023px) {
            font-size: 5vw;
            padding: 9px 50px 12px 50px;
          }
          @media screen and (min-width: 1024px) {
            font-size: 5vw;
            padding: 9px 50px 12px 50px;
          }
        }
      }
    }
    .back-to-home {
      width: 48px;
      height: 47px;
      background-color: #e60414;
      border-radius: 51% 0 0 51%;
      padding: 10px;
      position: fixed;
      right: 0;
      bottom: 10vh;
      z-index: 100;
      font-size: 9px;
      white-space: nowrap;
      cursor: pointer;
      display: flex;
      align-items: center;
      transform: translateX(100%);
      opacity: 0;
      transition: all 1s;
      font-weight: 900;
      @media screen and (min-width: 768px) and (max-width: 1023px) {
        display: none;
      }
      @media screen and (min-width: 1024px) {
        display: none;
      }
      a {
        color: white;
        cursor: pointer;
        width: 100%;
        height: 100%;
        img {
          display: block;
          width: 9px;
          position: relative;
          left: 50%;
          transform: translate(-25%);
        }
      }
    }
    .hidden-home {
      transform: translateX(0%);
      opacity: 1;
    }
   .anchor-web {
      @media screen and (max-width: 768px) {
        display: none;
      }
      .anchor-web-title {
        padding: 21px 0 55px 0;
        font-size: 37.9px;
        font-weight: bold;
        text-align: center;
      }
      ul {
        display: flex;
        justify-content: space-around;
        margin:0;
        padding: 0;
        text-indent: 0;
        list-style-type: 0;
        li {
          overflow: hidden;
          height: auto;
          width: 110px;
          display: flex;
          align-items: center;
          justify-content: center;
          flex-direction: column;
          position: relative;
          a {
            text-decoration: none;
            color: black;
            width: 100%;
          }
          img {
            width: 100%;
            cursor: pointer;
            border-radius: 51%;
          }
          p {
            margin: 0;
            line-height: 1;
            text-align: center;
            font-size: 17px;
            line-height: 1.35;
            font-weight: bolder;
          }
          .locked {
            background-color: gray;
            width: 100%;
            height: 100%;
            position: absolute;
          }
        }
        .shake:hover, .shake:active {
            animation: shake 0.82s cubic-bezier(.36,.07,.19,.97) both;
            transform: translate3d(0, 0, 0);
            backface-visibility: hidden;
            perspective: 1000px;
          }
          @keyframes shake {
            10%, 90% {
              transform: translate3d(-1px, 0, 0);
            }

            20%, 80% {
              transform: translate3d(2px, 0, 0);
            }

            30%, 50%, 70% {
              transform: translate3d(-4px, 0, 0);
            }

            40%, 60% {
              transform: translate3d(4px, 0, 0);
            }
          }
      }
    }
   .anchor-mobile {
     background-image: linear-gradient(to bottom, #f2f2f2, rgba(255, 255, 255, 0));
     padding-bottom: 13px;
      @media screen and (min-width: 1024px) {
        display: none;
      }
      .anchor-mobile-title {
        padding: 25px 0;
        font-size: 25px;
        font-weight: 900;
        text-align: center;
        color: black;
        margin: 0;
        text-align: center;
      }
      ul {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        margin:0;
        padding: 0;
        text-indent: 0;
        list-style-type: 0;
        li {
          overflow: hidden;
          width: 30%;
          display: flex;
          align-items: center;
          justify-content: center;
          position: relative;
          margin: 5px 0;
          flex-direction: column;
          text-align: center;
          @media screen and (min-width: 768px) and (max-width: 1023px) {
            width: 15%;
            height: auto;
          }
          a {
            width: 100%;
            text-decoration: none;
            color: black;
          }
          img {
            width: 75%;
            cursor: pointer;
            border-radius: 51%;
            margin: 5px;
          }
          p {
            margin: 0;
            line-height: 1;
            text-align: center;
            font-size: 12px;
            line-height: 1.33;
            font-weight: bolder;
          }
          .locked {
            background-color: gray;
            width: 100%;
            height: 100%;
            position: absolute;
          }
        }
        .shake:hover, .shake:active {
            animation: shake 0.82s cubic-bezier(.36,.07,.19,.97) both;
            transform: translate3d(0, 0, 0);
            backface-visibility: hidden;
            perspective: 1000px;
          }
          @keyframes shake {
            10%, 90% {
              transform: translate3d(-1px, 0, 0);
            }

            20%, 80% {
              transform: translate3d(2px, 0, 0);
            }

            30%, 50%, 70% {
              transform: translate3d(-4px, 0, 0);
            }

            40%, 60% {
              transform: translate3d(4px, 0, 0);
            }
          }
      }
    }
    .share-and-logo {
      display: flex;
      justify-content: flex-start;
      flex-direction: column;
      @media (min-width: 768px) and (max-width: 1024px){
        justify-content: space-between;
        flex-direction: row;
      }
      @media screen and (min-width: 1025px){
        justify-content: space-between;
        flex-direction: row;
      }
      .share {
        min-width: 35%;
      }
      .logo {
        @media (min-width: 768px) and (max-width: 1024px){
          margin-top: -5px;
        }
        @media screen and (min-width: 1025px){
          margin-top: -5px;
        }
      }
    }
}
</style>
