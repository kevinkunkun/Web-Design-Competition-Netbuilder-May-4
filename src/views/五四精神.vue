<script>
export default {
  name: "五四精神",
  mounted() {
    const header = document.querySelector('header');
    const img = document.querySelector('.img');
    const back = document.querySelector('.back');
    let scrollDistance = 0;
    let requestId = null;

    function updateHeaderClipPath() {
      const clipPathValue = `polygon(0 0, 100% 0%, 100% ${(scrollDistance <= 600) ? 100 - ((scrollDistance / 600) * 60) : 75}%, 0 100%)`;
      header.style.clipPath = clipPathValue;
      const scaleValue = 1 + ((scrollDistance / 600) * 1);
      console.log(scrollDistance)
      img.style.transform = `scale(${scaleValue})`;
      // back.style.mag = `${scaleValue}`;
      const opacityValue = (scrollDistance / 600);
    }

    function scrollHandler(event) {
      if (event.deltaY < 0) {
        scrollDistance = Math.max(0, scrollDistance + event.deltaY);
      } else {
        scrollDistance = Math.min(600, scrollDistance + event.deltaY);
      }
      if (!requestId) {
        requestId = window.requestAnimationFrame(() => {
          updateHeaderClipPath();
          requestId = null;
        });
      }
    }

    window.addEventListener('wheel', scrollHandler);
  }
}
</script>

<template>
  <div class="shell">
    <img class="back" src="@/assets/back/1.jpg">
    <header>
      <div class="img">
      </div>
    </header>

    <div class="main">
      <main>
        <article>
          <div class="multicol">
            <a name="541"></a>
            <h1 class="h1">五四精神·背景启示录</h1><br>
            <p class="p1">
              五四运动是1919年中国学生和民众反对巴黎和会决定将山东主权转让给日本的爱国运动。北京大学等高校学生在5月4日发起抗议，迅速引发全国范围的群众运动，工人、商人和市民纷纷支持。这场运动不仅反对不公平条约，还推动了新文化运动，提倡科学和民主，反对封建旧礼教。鲁迅、陈独秀、李大钊等知识分子通过《新青年》等刊物传播新思想，促进了中国社会的变革和现代化。五四运动标志着中国人民的觉醒，探索国家独立和民族复兴之路，对中国政治、文化产生了深远影响，是中华民族追求自由、民主和进步精神的象征。
            </p>
            <img src="@/assets/back/image_23.jpg" alt="" class="img1"><br>
            <p>
              五四运动是中国近现代史上的一个重要转折点，它标志着中国社会思想和政治发展的重大变革。1919年5月4日，北京大学等高等院校的学生因巴黎和会上中国外交的失败而举行了声势浩大的爱国运动，抗议列强对中国的不公待遇，尤其是对山东问题的解决方式。学生们走上街头，发表演说，焚烧赵家楼，呼喊“外争主权，内除国贼”的口号，掀起了一场反对帝国主义和封建主义的群众运动。这场运动迅速蔓延至全国，得到了广大工人、商人和市民的响应，形成了一股强大的社会力量。
            </p>
            <br><br><br>
            <p>
              五四运动不仅是一次反帝反封建的政治斗争，更是一场思想解放的文化运动。它打破了千百年来封建礼教的束缚，提倡科学和民主，推动了新文化运动的深入发展。五四运动中的青年学生们，高举着“德先生”（民主）和“赛先生”（科学）的旗帜，呼唤着民族独立和社会进步。他们的勇敢和智慧，激发了全国人民的觉醒，成为了中国现代化进程的重要推动力。
            </p>

          </div>

          <br><br><hr><br><br>

          <div class="multicol">
            <a name="542"></a>
           <h1 class="h1">五四精神·思维启迪卷</h1><br>
            <p class="p1">
              五四精神是1919年五四运动中展现的爱国、进步、民主和科学精神，源于对国家和民族命运的深切关注。青年学生和知识分子勇敢反对帝国主义和封建主义，推动社会觉醒和改革，倡导科学与民主，反对旧礼教，促进了思想解放和文化进步。五四精神推动新文化运动，以科学和民主为核心，唤起民众觉醒和社会现代化。这种精神不仅是对特定历史事件的总结，更是长期激励中国人民追求进步和变革的动力，强调个人社会责任和国家关心，至今仍激励着中国人为国家富强、民主进步和社会和谐而奋斗。
            </p>
            <img src="@/assets/back/image_19.jpg" alt="" class="img2">
            <br><br>
            <h2 class="h2">思维启迪·爱国卷</h2>
              <p>
                爱国是五四精神的核心，体现了对国家和民族命运的深切关注。1919年，五四运动的导火索是中国在巴黎和会上的外交失败，中国作为战胜国期望收回山东主权却被转让给日本，这一消息引发全国愤怒。学生们对国家主权被侵犯感到极度不满，迅速组织大规模抗议活动，北京学生走上街头，高呼口号，声讨卖国贼，要求政府拒绝签署不平等条约。抗议迅速蔓延全国，工人、商人和市民纷纷响应，展示了空前的团结和爱国热情。这场运动不仅揭露了列强对中国的压迫和不公，也激发了全国范围内的民族觉醒，提升了中华民族的自豪感和自我认同感。五四运动中的爱国精神成为推动中国现代化和民族独立的重要动力，并在之后继续发扬光大。在抗日战争和新中国成立后的社会主义建设中，这种精神激励着人民不断探索和创新，为国家富强和人民幸福努力。
              </p>
              <br><br><br>
              <img src="@/assets/back/5402.jpg" alt="" class="img3"><br><br><br>
              <p>
               爱国精神不仅限于政治抗争，它更渗透到了社会的各个方面。文学艺术领域，涌现出一大批以反映时代变迁和民族命运为主题的作品，激励了无数青年投入到民族复兴的伟大事业中。经济领域，爱国精神推动了民族工业的发展，越来越多的企业家以实业救国为己任，投身于振兴国家经济的洪流中。教育领域，爱国主义教育成为学校的重要课程，培养了无数有理想、有担当的爱国青年，为国家未来的发展奠定了坚实的人才基础。
              </p>
              <br><br>
              <p>
               在现代社会，爱国精神仍然具有强大的生命力和感召力。面对全球化带来的挑战和机遇，中国人民始终保持着高度的民族自信和团结一致的精神，推动着国家的持续进步和繁荣。无论是在科技创新、文化交流还是国际合作中，爱国精神始终激励着每一个中国人，为实现中华民族的伟大复兴而不懈努力。爱国不仅是一种情感，更是一种行动，它激励着一代又一代的中国人，勇敢面对挑战，创造更加辉煌的未来。
            </p>
            <br><br>
            <h2 class="h2">思维启迪·进步卷</h2>
             <p>
              进步是五四精神的另一个重要方面，代表着对社会改革和现代化的追求。五四运动时期，学生和知识分子对封建制度和旧文化进行了激烈批判，提倡新文化、新思想，希望通过改革实现社会进步。进步精神推动了新文化运动，倡导科学和民主，反对封建迷信和旧礼教，提倡男女平等、个性解放等现代思想。这种进步精神激励了一代又一代的中国人，追求更加公平、开放和现代化的社会。
            </p>
            <br><br>
              <p>
              五四运动后的新文化运动，强调以“德先生”（Democracy）和“赛先生”（Science）为旗帜，掀起了一场思想解放的风暴。知识分子们撰写文章、发表演讲，揭露封建制度的腐朽，提倡用科学的方法解决社会问题。他们认为，只有摆脱封建枷锁，接受现代思想，中国才能走向富强。进步精神不仅推动了文化领域的变革，也促进了社会各方面的进步，如教育改革、法律制度完善和经济结构调整。
            </p>
            <br><br><br>
            <img src="@/assets/back/5403.jpg" alt="" class="img5">
            <img src="@/assets/back/5405.jpg" alt="" class="img6">
            <br><br><br><br><br><br><br><br><br><br><br><br><br><br>
            <br><br><br><br><br><br><br><br><br><br><br><br><br><br>
            <br><br><br><br><br>
              <p>
              进步精神还体现在对个体权利和自由的尊重上。五四时期的思想家们强调个性解放，提倡平等和自由，反对任何形式的压迫和歧视。他们认为，只有在一个尊重个人价值和自由的社会中，才能实现真正的进步。进步精神促使中国社会不断追求公正和平等，推动了女性解放运动和劳动权益保护等社会变革。
            </p>
            <br><br>
              <p>
              在当代，进步精神仍然是推动社会发展的重要力量。面对全球化和信息化带来的新挑战，中国社会在经济、科技、文化等各个领域不断追求创新和突破，努力实现可持续发展。进步不仅是一种理念，更是一种实践，它激励着人们不断超越自我，创造更加美好的未来。
            </p>
            <br><br>
            <h2 class="h2">思维启迪·民主卷</h2>
            <img src="@/assets/back/image_20.jpg" alt="" class="img10"><br><br><br>
             <p>
              民主是五四精神的核心价值之一。五四运动的发起者大多是受过新思想熏陶的青年学生，他们向往西方的民主制度，主张以民主思想来改造中国的政治制度。他们反对专制和独裁，提倡人民当家作主，追求政治上的平等和自由。五四运动的民主诉求对中国政治思想产生了深远影响，为中国现代民主化进程奠定了基础。民主精神在当代中国依然具有重要意义，体现在对公民权利和参与政治生活的重视上。
            </p>
            <br><br>
              <p>
              五四运动期间，学生们高举“民主”大旗，呼吁政府倾听民意，尊重人民的基本权利。他们组织集会、发表宣言，要求实行宪政，反对封建专制和军阀统治。这些行动不仅揭示了当时政治制度的弊端，也表达了对民主理想的强烈追求。民主精神成为推动中国社会进步和政治改革的重要力量，引领着中国人民走向更加公正和自由的未来。
            </p>
            <br><br><br><br>
            <img src="@/assets/back/image_22.jpg" alt="" class="img11">
              <p>
              在五四精神的感召下，中国的民主进程不断推进。新中国成立后，人民当家作主的理念得以确立，人民代表大会制度和基层民主选举制度逐步完善，为公民参与政治生活提供了制度保障。民主精神还体现在对法治建设的重视上，通过完善法律体系，保障公民的合法权益，促进社会的公平正义。
            </p>
            <br><br>
              <p>
              在现代社会，民主精神不仅体现在政治领域，也渗透到了社会生活的各个方面。公共事务的民主决策、企业管理的民主参与、学校教育的民主氛围，都体现了民主精神的广泛影响。公民的民主意识不断增强，越来越多的人积极参与到公共事务中，通过多种渠道表达自己的意愿和观点，推动社会的持续进步。
            </p>
            <br><br>
              <p>
            民主精神激励着每一个公民，为实现更加公平和谐的社会而努力奋斗。无论是在政治改革、社会治理还是日常生活中，民主精神始终是推动社会发展的重要力量。它不仅是一种价值观，更是一种实践方式，体现了人民对美好生活的不懈追求。
          </p>
          <br><br>
          <h2 class="h2">思维启迪·科学卷</h2><br>
          <img src="@/assets/back/image_26.jpg" alt="" class="img12">
            <p>
              科学精神在五四运动中同样占据重要地位。五四时期，知识分子积极倡导科学方法和科学思想，反对封建迷信和传统观念。他们认为，科学是国家富强和社会进步的基础，提倡通过科学研究和教育来推动社会发展。五四运动后，科学精神逐渐深入人心，推动了中国科学技术的发展和教育事业的进步。科学精神在当代中国依然是推动创新和发展的重要力量，体现在对科学研究和技术创新的重视上。
            </p>
            <br><br>
              <p>
              五四运动时期的知识分子通过出版刊物、举办讲座等形式，广泛传播科学知识，倡导科学精神。他们认为，科学不仅仅是技术的进步，更是一种思维方式和价值观念。通过科学的方法，可以理性地分析和解决社会问题，推动社会的全面进步。这种科学精神激发了人们对知识的渴求和对真理的追求，成为推动中国现代化的重要力量。
            </p>
            <br><br><br><br><br><br><br><br><br>
            <img src="@/assets/back/5404.jpg" alt="" class="img13">
            <p>
              在五四精神的影响下，中国的科学事业取得了长足的进步。新中国成立后，国家高度重视科学技术的发展，建立了完整的科研体系和教育体系，培养了大量的科技人才。科学精神推动了科技创新，带来了经济的快速发展和社会的全面进步。中国在航天、信息技术、生物工程等领域取得了世界瞩目的成就，成为全球科技发展的重要力量。
            </p>
            <br><br>
              <p>
              当代中国，科学精神依然是推动社会进步的重要动力。政府不断加大对科研的投入，鼓励创新创业，支持高新技术产业的发展。教育改革注重培养学生的科学素养和创新能力，提倡通过科学教育提升全民科学素质。科学精神不仅体现在科研领域，也融入到人们的日常生活中，成为社会进步的重要支撑。
            </p>
            <br><br>
              <p>
              科学精神激励着中国人民不断追求知识和创新，推动国家走向更加美好的未来。无论是在科技前沿的探索，还是在日常生活的点滴创新中，科学精神始终激励着每一个人，为实现国家的繁荣和进步贡献力量。科学不仅是一种方法，更是一种精神，它引领着人们走向未知的领域，探索无尽的可能。
            </p>
         </div>

          <br><br><hr><br><br>

          <div class="multicol">
            <a name="543"></a>
            <h1 class="h1">五四精神·传承里程碑</h1><br>
            <p class="p1">
              五四精神的传承与发展体现了中国社会在追求现代化过程中不断进步的历程。这种精神在不同历史阶段都发挥了重要作用，激励着中国人民不断追求国家独立、社会进步和个人解放。新中国成立后，五四精神在推动社会主义建设和改革开放中继续发挥作用，倡导科学、民主和创新，推动教育、科技和文化事业的发展。改革开放以来，五四精神成为激励创新、勇于探索和敢于担当的动力源泉，鼓励一代又一代人致力于实现中华民族的伟大复兴。在当今时代，五四精神依然具有重要意义，强调爱国主义、集体主义和科学精神，呼吁年轻一代关注社会问题，积极参与国家建设，为实现中国梦贡献力量。五四精神不仅是历史的宝贵遗产，更是现代中国社会发展的内在动力，体现了中华民族追求真理、勇于变革和不断进步的优良传统。它不仅引领着中国的未来方向，也为全球范围内的进步和变革提供了宝贵的精神资源。
            </p>
            <img src="@/assets/back/image_18.jpg" alt="" class="img14">
            <p>
              五四精神虽然产生于特定的历史时期，但其精神内涵具有跨越时空的永恒价值。今天，五四精神仍然是激励我们前行的强大动力，具有重要的时代意义和现实价值。
            </p>
            <br><br>
              <p>
              在新时代，爱国主义依然是中华民族的精神纽带和力量源泉。爱国不仅是五四精神的核心内容，也是新时代中国特色社会主义建设的强大动力。新时代的中国青年，继承和发扬五四精神，把个人理想与国家前途紧密结合起来，为实现中华民族的伟大复兴而不懈奋斗。
            </p>
            <br><br><br>
            <img src="@/assets/back/image_24.jpg" alt="" class="img7">
              <p>
              进步精神在今天同样具有重要意义。新时代的中国，正处在深化改革和全面发展的关键时期，社会各领域都需要不断创新和进步。五四精神所倡导的进步思想，激励我们勇于探索，敢于突破，为建设社会主义现代化强国贡献智慧和力量。
            </p>
            <br><br>
              <p>
              民主精神是现代社会的重要价值追求。新时代的中国，正在推进社会主义民主政治建设，努力实现人民当家作主。五四精神中的民主理念，推动了我国政治体制的不断完善和发展，保障了人民的权利和自由。
            </p>
            <br><br>
              <p>
              科学精神是现代文明的基石。新时代的中国，正在向科技强国迈进，科学技术的发展对国家的繁荣富强至关重要。五四精神所倡导的科学态度和方法，激励我们重视科学教育，推动科技创新，为国家的长远发展提供不竭动力。
            </p>
          </div>

          <br><br><hr><br><br>

          <div class="multicol">
            <a name="544"></a>
            <h1 class="h1">五四精神·新时代风向标</h1><br>
            <p class="p1">
              五四运动对当今社会的影响深远，首先是爱国精神的传承，激励中国人民在全球化挑战中凝聚力量、推动发展。其次，五四运动倡导的科学和民主思想在现代社会具有重要指导意义，推动创新和社会公平。批判精神和思想解放仍然引导社会进步和改革，强调社会责任感和担当精神，有助于构建和谐社会，实现共同富裕。此外，新文化运动精神推动中华文化的传承与创新，增强文化自信。五四精神不仅是历史记忆，更是现代社会的宝贵财富，激励每一个中国人为实现中国梦而奋斗。
            </p>
            <img src="@/assets/back/image_25.jpg" alt="" class="img8">
            <p>
              五四精神不仅是历史的回响，更是当下社会发展的动力源泉。在新时代，五四精神的实践主要体现在教育、文化、科技和社会各个领域。在教育方面，五四精神倡导的科学和民主理念推动着教育改革和素质教育的发展，培养了大批具有创新精神和实践能力的优秀人才。在文化方面，五四精神激励着文化创新和传承，促进了中华优秀传统文化与现代文化的融合发展。
            </p>
            <br><br>
            <p>
              在科技方面，五四精神所提倡的实事求是和科学求真的态度，成为推动科技创新的重要力量。无论是在基础科学研究，还是在应用技术开发领域，五四精神都激励着科研工作者勇攀高峰，攻坚克难，为国家的科技进步和产业升级作出了重要贡献。
            </p>
            <br><br>
            <p>
              在社会方面，五四精神所强调的民主与进步，推动了社会治理的现代化和法治化进程。新时代的中国，在推进依法治国、建设社会主义法治国家的过程中，五四精神提供了重要的思想支持和价值导向。五四精神中的爱国主义情怀，激励着亿万人民团结一心，为实现中国梦而共同努力。
            </p>
            <br><br>
            <img src="@/assets/4.webp" alt="" class="img9">
            <p>
              五四精神的实践不仅体现在国内，也在国际舞台上彰显出中国青年的风采。新时代的中国青年，积极参与国际事务，展现了中国的自信和担当，传递着五四精神的正能量。无论是在国际组织、学术交流，还是在全球公益事业中，五四精神都在新时代的中国青年身上得到传承和发扬，成为展示中国形象的重要窗口。
            </p>
            <br><br>
            <p>
              五四精神在新时代的实践，体现了其强大的生命力和广泛的社会影响。我们要继续弘扬五四精神，把它作为推动国家发展、社会进步的重要精神动力，为实现中华民族的伟大复兴贡献智慧和力量。
            </p>
            <hr>
          </div>
        </article>
      </main>
    </div>
    <div class="con">
			<a href="#541"><span class="note">
			      五四精神·背景启示录
			</span>
			<span class="logo">
				<span class="static"><img src="@/assets/logo.png" alt=""></span>
				<span class="hidden"><img src="@/assets/logo1.png" alt=""></span>
			</span>
			</a>
			<a href="#542"><span class="note">
			     五四精神·思维启迪卷
			</span>
			<span class="logo">
				<span class="static"><img src="@/assets/logo.png" alt=""></span>
				<span class="hidden"><img src="@/assets/logo1.png" alt=""></span>
			</span>
			</a>
			<a href="#543"><span class="note">
			     五四精神·传承里程碑
			</span>
			<span class="logo">
				<span class="static"><img src="@/assets/logo.png" alt=""></span>
				<span class="hidden"><img src="@/assets/logo1.png" alt=""></span>
			</span>
			</a>
      <a href="#544"><span class="note">
			     五四精神·新时代风向标
			</span>
			<span class="logo">
				<span class="static"><img src="@/assets/logo.png" alt=""></span>
				<span class="hidden"><img src="@/assets/logo1.png" alt=""></span>
			</span>
			</a>
		</div>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;700&display=swap');

* {
  padding: 0;
  margin: 0;
}

.back {
  background-size: cover;
  position: fixed;
  width: 100%;
  margin-top: -85px;
  height: 100%;
  z-index: -99;
}

body {
  height: 2000px;
  overflow-x: hidden;

}

.shell {
  width: 100%;
  display: flex;
  flex-direction: column;

}

header {
  width: 100%;
  height: 700px;
  overflow: hidden;
  clip-path: polygon(0 0, 100% 0%, 100% 100%, 0 100%);
  transition: clip-path 0.5s ease;
  position: relative;
}

.img1{
  float: left;
  display: block;
  margin-top: 20px;
  margin-left: 20px;
  margin-right: 20px;
  width: 510px;
  height: 650px;
}

.img2{
  float: right;
  display: block;
  margin: 20px;
  width: 550px;
  height: 650px;
}

.img3{
  float: left;
  display: block;
  margin-top: 150px;
  margin-left: 20px;
  margin-right: 20px;
  width: 800px;
  height: 600px;
}

.img4{
  float: right;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 600px;
  height: 400px;
}

.img5{
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 700px;
  height: 500px;
  float: right;
}

.img6{
  float: left;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 700px;
  height: 500px;
}

.img7{
  float: right;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 500px;
  height: 700px;
}

.img8{
  float: left;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 550px;
  height: 750px;
}

.img9{
  float: right;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 700px;
  height: 500px;
}

.img10{
  float: right;
  display: block;
  margin-top: 30px;
  margin-left: 20px;
  margin-right: 10px;
  margin-bottom: 20px;
  width: 550px;
  height: 650px;
}

.img11{
  float: left;
  display: block;
  margin-top: 30px;
  margin-left: 20px;
  margin-right: 20px;
  width: 550px;
  height: 700px;
}

.img12{
  float: right;
  display: block;
  margin-left: 20px;
  margin-right: 20px;
  width: 500px;
  height: 700px;
}

.img13{
  float: left;
  display: block;
  margin-top: 80px;
  margin-left: 20px;
  margin-right: 20px;
  width: 800px;
  height: 550px;
}

.img14{
  float: left;
  display: block;
  margin: 20px;
  width: 650px;
  height: 450px;
}

.p1 {
  font-weight: bold;
  font-size: 30px; /* 字体大小 */
  font-family: 'STKaiti', '华文楷体', serif;
  color: #003366; /* 深蓝色字体，与其他部分风格一致 */
  background: linear-gradient(90deg, #ffffff 25%, #ff4d4d 75%); /* 渐变背景，与红色背景协调 */
  padding: 10px 20px; /* 内边距，增加文字块的可读性 */
  border-radius: 10px; /* 圆角边框，增加活泼感 */
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* 轻微阴影，增加立体感 */
  text-align: left; 
  margin: 20px 0; /* 外边距，增加段落间距 */
}


/* .p1{
  font-weight: bold;
  font-size: 40px;
} */

.h2 {
            font-family: 'Times New roman', serif;
            font-size: 70px;   
            color: #003366; /* 深蓝色文字，与红色背景形成对比 */
            text-shadow: 1px 1px 2px #ffffff, 0 0 25px #ffffff, 0 0 5px #ffffff; /* 白色光晕效果 */
            font-weight: bold; 
            text-align: center;  
            margin-bottom: 20px;
            position: relative;
        }
/* 
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0);
            }
            40% {
                transform: translateY(-10px);
            }
            60% {
                transform: translateY(-5px);
            }
        } */

/* .h2{
  font-family: '华文新魏';
  font-size: 70px;   
	color:#CC3299; 
	text-shadow: 0 8px 10px #FF6666; 
	font-weight: bolder; 
	text-align: center;  
  margin-bottom: 20px;
} */


.img {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background: url("@/assets/54JS.webp");
  background-size: cover;
  transform: scale(1);
  transition: transform 0.5s ease;
}

.h1{
    font-size: 100px; /*设置字体大小*/
    font-weight: 800; /*设置字体粗细*/
    font-family: '华文新魏';
    margin-top: 20px;
    margin-bottom: 10px;
    color: #FFFFFF;
    text-shadow: 1px 0px #FF0000, 1px 2px #CC0000, 3px 1px #FF0000,
                 2px 3px #CC0000, 4px 2px #FF0000, 4px 4px #CC0000,
                 5px 3px #FF0000, 5px 5px #CC0000, 7px 4px #FF0000,
                 6px 6px #CC0000, 8px 5px #FF0000, 7px 7px #CC0000,
                 9px 6px #FF0000, 9px 8px #CC0000, 11px 7px #FF0000; /*设置文字阴影*/
}

.main {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  flex-direction: column;

}

/* .main h2 {
  font-size: 50px;
  margin-bottom: 40px;
} */

.main span {
  padding: 0 100px;
  font-size: 30px;
}

p {
  font-weight: normal; /* 字体粗细调整为正常 */
  font-size: 26px; /* 增加字体大小 */
  font-family: 'Noto Sans SC', serif;
  line-height: 1.8; /* 增加行高，提高阅读舒适度 */
  margin: 15px 0; /* 增加上下外边距，分隔段落 */
  text-align: justify; /* 两端对齐，使文本更整齐 */
  text-indent: 2em; /* 首行缩进 */
  color: #333333; /* 使用深灰色以提高可读性 */
  background-color: #fdf5e6; /* 浅蓝色背景，增加活泼感 */
  padding: 15px 20px; /* 增加内边距，提升文本块的可读性 */
  border-radius: 10px; /* 圆角边框，增加视觉柔和度 */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* 轻微阴影，增加立体感 */
  overflow: hidden;
  transition: transform 0.2s; /* 增加动画效果 */
}

/* p:hover {
  transform: scale(1.05); 
} */



/* p {
  font-weight: 25;
  font-size: 30px;
  font-family: '楷体';
  line-height: 1.4;
  margin: 10px;
  text-align: left;
  text-indent: 2em;
  color: black;
  overflow: hidden;
} */

      .con{
				position: fixed;
				right: 1%;
        top: 75%;
        transform:translate(-50%,-50%);
			}
			.con a{
				display: block;
				position: relative;
				margin: 25px 0;
			}
			.con a .note{
				display: none;
				position: absolute;
				width: 100px;
				left: -105px;
				text-align: center;
				font-family: '楷体';
        color: yellow !important;
        font-size: 25px;
			}
			.logo img{
				width: 60px;
			}
			.hidden{
				display: none;
			}
			.con a:hover .static{
				display: none;
			}
			.con a:hover .hidden{
				display: inline-block;
			}
			.con a:hover .note{
				display: inline-block;
				color: white;
			}

p a {
  font-weight: bolder;
  color: #000;
  text-decoration: none;
}

@supports (font-variant-caps: small-caps) {
  .multicol:first-of-type p:first-of-type {
    font-variant-caps: small-caps;
  }
}

.multicol {
  column-count: 1;
  column-gap: 2rem;
}


article {
  width: 80%;
  margin: 0 auto 4rem;
}

article img {
  width: 100%;
}

article header {
  margin-bottom: 2.5rem;
  padding-bottom: 4rem;
  border-bottom: 1px solid rgba(0, 0, 0, 0.8);
}



@media all and (max-width: 600px) {
  body {
    margin: 0;
  }

  article {
    width: 100%;
  }

  .multicol {
    padding: 0 1rem;
  }

  article header {
    margin-bottom: 2.5rem;
    padding-bottom: 0;
    border-bottom: none;
  }


}
</style>
