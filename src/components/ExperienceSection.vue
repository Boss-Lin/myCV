<template>
  <section class="experience" id="experience">
    <h1 class="heading">my <span>work experience</span></h1>

    <div class="box-container">
      <div v-for="exp in experiences" :key="exp.period" class="box">
        <i class="fas fa-graduation-cap"></i>
        <span>{{ exp.period }}</span>
        <h2>{{ exp.title }}</h2>
        <h3>{{ exp.company }}</h3>
        <p v-for="(desc, i) in exp.descriptions" :key="i">{{ desc }}</p>
        <a v-if="exp.link" :href="exp.link">myProject</a>
        <h6>Use tools</h6>
        <ul>
          <li v-for="tool in exp.tools" :key="tool">{{ tool }}</li>
        </ul>
        <template v-if="exp.devItems">
          <h6>開發項目有</h6>
          <ul>
            <li v-for="item in exp.devItems" :key="item">{{ item }}</li>
          </ul>
        </template>
      </div>
    </div>
  </section>
</template>

<script setup>
const experiences = [
  {
    period: '2025.08 ~ 2025.12',
    title: 'Java Engineer',
    company: '盛大資訊股份有限公司(台積電專案：PartitionCheck)',
    descriptions: [
      '內部DBA需求專案，利用Excel紀錄需要執行的大量SQL並搜尋資料庫，回傳對方需求格式的Excel。',
      'In-plant employees use dedicated GPTs. Collaborate with another Python engineer to develop the screen.',
    ],
    tools: ['Git', 'Vue3.js', 'Java', 'Springboot', 'Oracle'],
  },
  {
    period: '2024.03 ~ 2025.07',
    title: 'Java Engineer',
    company: '緯創軟體股份有限公司(友達專案：廠內 GPT系統)',
    descriptions: [
      '以前端工程師身份，協助廠內Python工程師開發專屬於客戶端的GPT，負責開發畫面',
      'In-plant employees use dedicated GPTs. Collaborate with another Python engineer to develop the screen.',
    ],
    tools: ['Git', 'Vue3.js', 'Pinia.js', 'Chart.js', 'Websocket', 'Quasar', 'Router'],
  },
  {
    period: '2024.03 ~ 2025.06',
    title: 'Java Engineer',
    company: '緯創軟體股份有限公司(友達專案：廠內SCC_ETL系統)',
    descriptions: [
      '依管理者設定特定時間去執行上述的 SCC 系統。',
      'The administrator sets a specific time to execute the above SCC system.',
    ],
    tools: ['Java', 'Springboot', 'Git', 'oracle', 'MSSQL'],
  },
  {
    period: '2024.03 ~ 2025.06',
    title: 'Java Engineer',
    company: '緯創軟體股份有限公司(友達專案：廠內SCC系統)',
    descriptions: [
      '負責開發一套監控工廠內部狀況的系統，讓管理人員能夠即時監控生產能力。',
      'Responsible for developing a system to monitor the internal conditions of the factory, allowing managers to monitor production capacity in real time.',
    ],
    tools: ['Java', 'Springboot', 'Git', 'Oracle', 'MSSQL', 'Vue3.js', 'Pinia.js', 'Chart.js', 'Websocket'],
  },
  {
    period: '2023.08 ~ 2023.11',
    title: 'Python Engineer',
    company: '印度商威普羅股份有限公司台灣分公司',
    descriptions: [
      '依照客戶需求，整合所有設備商設備並進行自動化測試。',
      "Integrate all equipment vendors' equipment and conduct automated testing according to customer needs.",
    ],
    tools: ['Python', 'Git', 'Selenium'],
  },
  {
    period: '2022.04 ~ 2023.08',
    title: 'Java Engineer',
    company: '德義資訊股份有限公司 - 圖書館後台管理系統',
    descriptions: [
      '依照客戶需求，完成相關開發。',
      'Maintain and operate client web pages and develop functions required by customers.',
    ],
    tools: ['Java', 'Spring boot', 'JavaScript', 'Vue.Js', 'MS SQL', 'Oracle', 'Git'],
    devItems: [
      '管理> 維護> Z39屬性設定',
      '管理> 功能維護> 主題維護',
      '流通> 借閱預約查詢> 調整預約順位',
      '流通> 線上盤點',
      '採購> 訂購> 檢查薦購',
      '期刊> 訂購> 檢查薦購',
      '白箱弱點掃描修正',
      '採購> 訂購> 檢查薦購 的新增功能',
    ],
  },
  {
    period: '2021.05 ~ 2021.11',
    title: 'resident engineer - PHP',
    company: 'systex(精誠資訊) -駐點維護案',
    descriptions: [
      '依照客戶需求，完成相關維護及開發。',
      'Maintain and operate client web pages and develop functions required by customers.',
    ],
    tools: ['PHP', 'HTML', 'CSS', 'Laravel MVC', 'MySQL', 'PostgreSQL', 'Docker', 'Git'],
  },
  {
    period: '2021.01 ~ 2021.05',
    title: 'full stack engineer - JAVA',
    company: 'Shoalter(英屬維京群島商易貿創投有限公司台灣分公司) - 店商專案',
    descriptions: [
      '這是我第一份Java的相關工作，工作內容是修改專案的bug並開發推播功能。',
      'In my first job, I am a java engineer, which is about e-commerce websites. The job content is to check the code for bugs and fix them.',
    ],
    tools: ['java', 'spring boot MVC', 'MySQL', 'docker', 'rabbitmq', 'Git'],
  },
  {
    period: '2019.05 ~ 2020.02',
    title: 'student - JAVA',
    company: 'Institute for Information Industry(資策會)',
    descriptions: ['這是在資策學員時，做的專案。', 'This is what I did when I was a student.'],
    link: 'https://drive.google.com/file/d/11Kqn1XC868acQgbG4j4yw7XeOJATqmvo/view',
    tools: ['java', 'HTML', 'CSS', 'JavaScript', 'spring boot MVC', 'Oracle'],
  },
]
</script>
