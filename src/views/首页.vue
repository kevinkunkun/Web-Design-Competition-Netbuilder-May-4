<script>

export default {
  mounted() {
    var items = document.getElementsByClassName('item')
// 循环遍历每个item
    for (var i = 0; i < items.length;
         i++
    ) {
      // 获取当前item
      var item = items[i];
      var frame = item.getElementsByClassName('frame')[0];
      var frontBox = frame.getElementsByClassName('front')[0];
      var leftBox = frame.getElementsByClassName('left')[0];
      var rightBox = frame.getElementsByClassName('right')[0];
      // 设置背景图片
      frontBox.style.backgroundImage = "url(" + require("@/assets/dashboard/" + (i + 1).toString() + ".jpg") + ")";
      leftBox.style.backgroundImage = ("url(" + require("@/assets/dashboard/" + (i + 1).toString() + ".jpg") + ")");
      rightBox.style.backgroundImage = ("url(" + require("@/assets/dashboard/" + (i + 1).toString() + ".jpg") + ")");
    }
    (function () {
      "use strict";
      var shell = document.getElementsByClassName('shell')[0];
      var slider = shell.getElementsByClassName('shell_slider')[0];
      var items = shell.getElementsByClassName('item');
      var prevBtn = shell.getElementsByClassName('prev')[0];
      var nextBtn = shell.getElementsByClassName('next')[0];
      // 定义变量
      var width, height, totalWidth, margin = 20,
          currIndex = 0,
          interval, intervalTime = 3000;

      function init() {
        // 初始化函数
        resize();
        move(Math.floor(items.length / 2));
        bindEvents();
        timer();
      }

      function resize() {
        // 窗口大小变化时调整大小
        width = Math.max(window.innerWidth * .20, 275);
        height = window.innerHeight * .5;
        totalWidth = width * items.length;
        // 设置slider宽度
        slider.style.width = totalWidth + "px";
        // 设置每个item的宽度和高度
        for (var i = 0; i < items.length; i++) {
          let item = items[i];
          item.style.width = (width - (margin * 2)) + "px";
          item.style.height = height + "px";
        }
      }

      function bindEvents() {
        // 窗口大小变化时调整大小
        window.onresize = resize;
        // 点击prev按钮切换item
        prevBtn.addEventListener('click', () => {
          prev();
        });
        nextBtn.addEventListener('click', () => {
          next();
        });
      }

      init();

      function move(index) {
        // 移动shell到指定的item
        if (index < 1) index = items.length;
        if (index > items.length) index = 1;
        currIndex = index;
        // 遍历所有item
        for (var i = 0; i < items.length; i++) {
          let item = items[i],
              box = item.getElementsByClassName('frame')[0];
          if (i == (index - 1)) {
            // 当前item添加active类并设置3D效果
            item.classList.add('item--active');
            box.style.transform = "perspective(1200px)";
          } else {
            // 其他item移除active类并设置3D效果
            item.classList.remove('item--active');
            box.style.transform = "perspective(1200px) rotateY(" + (i < (index - 1) ? 40 : -40) + "deg)";
          }
        }
        // 移动slider
        slider.style.transform = "translate3d(" + ((index * -width) + (width / 2) + window.innerWidth / 2) + "px, 0, 0)";
        // 设置body背景图片
        var frontBox = items[index - 1].getElementsByClassName('front')[0];
        document.getElementById("back").style.backgroundImage = frontBox.style.backgroundImage;
      }

      function timer() {
        // 定时器，自动切换shell
        clearInterval(interval);
        interval = setInterval(() => {
          move(++currIndex);
        }, intervalTime);
      }

      // 切换item
      function prev() {
        move(--currIndex);
        timer();
      }

      function next() {
        move(++currIndex);
        timer();
      }
    })();

  }
}

</script>

<template>
  <div id="back" class="back">
    <div class="logo">
    <img src="@/assets/back/logo02.png" alt="" class="logo1">
    </div>
    <div class="shell">
      <div class="shell_body">
        <div class="button">
          <div class="prev"><i class="iconfont icon-left"></i></div>
          <div class="next"><i class="iconfont icon-right"></i></div>
        </div>

        <div class="shell_slider">
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>《五四运动》油画</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>《五四运动》浮雕</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>不忘初心 薪火相传</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>五四运动口号</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>上海学生联合会</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>上海工人罢工</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>
          <div class="item">
            <div class="frame">
              <div class="box front">
                <span>火烧赵家楼</span>
              </div>
              <div class="box left"></div>
              <div class="box right"></div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@import "@/assets/css/iconfont.css";
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;700&display=swap');

/* 设置html和body元素为flex布局，水平和垂直居中对齐，高度为100vh，背景图大小为cover，溢出隐藏，背景图过渡动画时间为0.7秒 */

.back {
  background-size: cover;
  align-items: center;
  height: calc(100vh - 100px);
  overflow: hidden;
  z-index: 1;
  transition: background-image .7s ease-in-out;
}

/* 设置.shell元素为相对定位，flex布局，水平和垂直居中对齐，宽度和高度为100%，盒模型为border-box，背景颜色为rgba(99, 99, 99, 0.8) */
.shell {
  background-size: cover;
  width: 100%;
  overflow: hidden;
  z-index: 1;
  transition: background-image .7s ease-in-out;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  box-sizing: border-box;
}

/* 设置.button元素为flex布局，两端对齐，宽度为380px，绝对定位，左侧偏移量为50%，水平居中，底部偏移量为-80px */
.button {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 380px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: -50px;
}

/* 设置.prev和.next元素过渡动画时间为0.25秒，层级为99999，底部偏移量为5px */
.prev,
.next {
  transition: transform 0.25s ease;
  z-index: 99999;
  bottom: 5px;
}

/* 设置.prev和.next元素中的i元素字体大小为90px，颜色为#fff，光标为指针，文字阴影为0 0 10px #ffffff */
.prev i,
.next i {
  font-size: 90px;
  color: #fff;
  cursor: pointer;
  text-shadow: 0 0 10px #ffffff;
}

/* 设置.shell_body元素宽度为100%，缩放为0.8倍，上内边距为20px，下内边距为150px */
.shell_body {
  width: 100%;
  transform: scale(.8);
  padding: 20px 0 150px 0;
}

/* 设置.shell_slider元素为相对定位，过渡动画时间为1秒，背景为透明 */
.shell_slider {
  position: relative;
  transition: transform 1s ease-in-out;
  background: transparent;
}

/* 设置.item元素为相对定位，左浮动，左右外边距为20px */
.item {
  position: relative;
  float: left;
  margin: 0 20px;
}

/* 设置.frame元素为相对定位，宽度和高度为100%，过渡动画时间为1秒，3D变换模式为保留3D效果 */
.frame {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 1s ease-in-out;
  transform-style: preserve-3d;
}

/* 设置.frame元素的伪元素为绝对定位，底部偏移量为-16%，宽度为100%，高度为60px，背景颜色为#ffffff1c，盒阴影为0px 0px 15px 5px #ffffff1c，3D变换为绕X轴旋转90度并向上平移20px */
.frame:after {
  content: "";
  position: absolute;
  bottom: -16%;
  width: 100%;
  height: 60px;
  background: #ffffff1c;
  box-shadow: 0px 0px 15px 5px #ffffff1c;
  transform: rotateX(90deg) translate3d(0px, -20px, 0px);
}

/* 设置.box元素为flex布局，纵向排列，水平和垂直居中对齐，绝对定位，宽度和高度为100%，边框为4px实心白色，透视效果为1000px，3D变换模式为保留3D效果 */
.box {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: absolute;
  width: 100%;
  height: 100%;
  border: 4px solid #fff;
  perspective: 1000px;
  transform-style: preserve-3d;
}

/* 设置.box元素中的h1和span元素颜色为#fff，Z轴平移距离为20px */
.box h1,
.box span {
  color: rgba(255, 0, 0, 0.812);
  transform: translateZ(20px);
}

/* 设置.box元素中的h1元素文字阴影为0 0 30px #1f05b4，字体大小为100px */
.box h1 {
  text-shadow: 0 0 30px #1f05b4;
  font-size: 100px;
}

.box span {
  position: absolute;
  bottom: 20px;
  padding: 0 25px;
  text-shadow: 2px 2px 4px #555555; /* 适度的文字阴影 */
  color: #ff6666; /* 鲜艳的橙色 */
  font-weight: bold; /* 加粗文字，增加严谨感 */
  font-family: 'Noto Sans SC', serif; /* 使用具有历史感的字体 */
  font-size: 38px; /* 合理的字体大小 */
}

/* 设置.box元素中的span元素为绝对定位，底部偏移量为20px，左右内边距为25px，文字阴影为0 0 10px #1f05b4 */
/* .box span {
  position: absolute;
  bottom: 20px;
  padding: 0 25px;
  text-shadow: 0 0 10px white;
} */

.front,
.left,
.right {
  box-shadow: 0 0 50px #ffffff;
  background-size: cover;
}

/* 设置.front、.left和.right元素的盒阴影为0 0 50px #ffffff，背景图大小为cover */
/* .front,
.left,
.right {
  box-shadow: 0 0 50px #ffffff;
  font-size: 38px;
  background-size: cover;
} */

/* 设置.left和.right元素的顶部偏移量为0，宽度为60px，背面不可见 */
.right,
.left {
  top: 0;
  width: 60px;
  backface-visibility: hidden;
}

/* 设置.left元素的左侧偏移量为0，左边框宽度为5px，3D变换为向右平移1px，Z轴平移-60px，绕Y轴逆时针旋转90度，变换原点为左侧 */
.left {
  left: 0;
  border-left-width: 5px;
  transform: translate3d(1px, 0, -60px) rotateY(-90deg);
  transform-origin: 0%;
}

/* 设置.right元素的右侧偏移量为0，右边框宽度为5px，3D变换为向左平移1px，Z轴平移-60px，绕Y轴顺时针旋转90度，变换原点为右侧 */
.right {
  right: 0;
  border-right-width: 5px;
  transform: translate3d(-1px, 0, -60px) rotateY(90deg);
  transform-origin: 100%;
}

.logo{
  position: fixed;
  left: 50%;
  transform:translate(-50%,-50%);
  margin-top: 100px;
  margin-bottom: 0px;
}

.logo1{
  width: 1300px;
  height: 150px;
}

</style>
