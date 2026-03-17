<template>
  <div class="cv-print">
    <!-- Header -->
    <div class="cv-header">
      <img :src="profileImg" alt="林意翔" class="cv-avatar" />
      <div class="cv-title">
        <h1>林意翔</h1>
        <h2>Java Engineer</h2>
      </div>
    </div>

    <!-- Skills -->
    <div class="cv-section">
      <h3 class="cv-section-title">My <span>Skill</span></h3>
      <div class="cv-skills">
        <div v-for="group in skillGroups" :key="group.category" class="cv-skill-box">
          <p class="cv-skill-category">{{ group.category }}</p>
          <p v-for="item in group.items" :key="item" class="cv-skill-item">{{ item }}</p>
        </div>
      </div>
    </div>

    <!-- Experience -->
    <div class="cv-section">
      <h3 class="cv-section-title">My <span>Work Experience</span></h3>
      <div class="cv-experiences">
        <div v-for="exp in experiences" :key="exp.period" class="cv-exp-box">
          <div class="cv-exp-header">
            <span class="cv-period">{{ exp.period }}</span>
            <span class="cv-job-title">{{ exp.title }}</span>
          </div>
          <p class="cv-company">{{ exp.company }}</p>
          <p v-for="(desc, i) in exp.descriptions" :key="i" class="cv-desc">{{ desc }}</p>
          <div class="cv-tools">
            <span v-for="tool in exp.tools" :key="tool" class="cv-tag">{{ tool }}</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import profileImg from '../assets/個人照.jpg'

const skillGroups = [
  { category: 'Programming Language', items: ['Java', 'PHP', 'HTML', 'CSS', 'JavaScript'] },
  { category: 'Database', items: ['Oracle', 'MySQL', 'PostgreSQL', 'MS SQL'] },
  { category: 'Framework', items: ['Spring Boot', 'Struts', 'Servlet', 'Tapestry', 'Laravel'] },
  { category: 'Other Tools', items: ['Docker', 'RabbitMQ'] },
]

const experiences = [
  {
    period: '2025.08 ~ 2025.12',
    title: 'Java Engineer',
    company: '盛大資訊股份有限公司 (台積電專案：PartitionCheck)',
    descriptions: ['內部DBA需求專案，利用Excel紀錄需要執行的大量SQL並搜尋資料庫，回傳對方需求格式的Excel。'],
    tools: ['Git', 'Vue3.js', 'Java', 'Springboot', 'Oracle'],
  },
  {
    period: '2024.03 ~ 2025.07',
    title: 'Java Engineer',
    company: '緯創軟體股份有限公司 (友達專案：廠內 GPT系統)',
    descriptions: ['以前端工程師身份，協助廠內Python工程師開發專屬於客戶端的GPT，負責開發畫面。'],
    tools: ['Git', 'Vue3.js', 'Pinia.js', 'Chart.js', 'Websocket', 'Quasar', 'Router'],
  },
  {
    period: '2024.03 ~ 2025.06',
    title: 'Java Engineer',
    company: '緯創軟體股份有限公司 (友達專案：廠內SCC系統)',
    descriptions: ['負責開發一套監控工廠內部狀況的系統，讓管理人員能夠即時監控生產能力。'],
    tools: ['Java', 'Springboot', 'Git', 'Oracle', 'MSSQL', 'Vue3.js', 'Pinia.js', 'Chart.js', 'Websocket'],
  },
  {
    period: '2023.08 ~ 2023.11',
    title: 'Python Engineer',
    company: '印度商威普羅股份有限公司台灣分公司',
    descriptions: ['依照客戶需求，整合所有設備商設備並進行自動化測試。'],
    tools: ['Python', 'Git', 'Selenium'],
  },
  {
    period: '2022.04 ~ 2023.08',
    title: 'Java Engineer',
    company: '德義資訊股份有限公司 - 圖書館後台管理系統',
    descriptions: ['依照客戶需求，完成相關開發。'],
    tools: ['Java', 'Spring Boot', 'JavaScript', 'Vue.js', 'MS SQL', 'Oracle', 'Git'],
  },
  {
    period: '2021.05 ~ 2021.11',
    title: 'Resident Engineer - PHP',
    company: 'Systex (精誠資訊) - 駐點維護案',
    descriptions: ['依照客戶需求，完成相關維護及開發。'],
    tools: ['PHP', 'HTML', 'CSS', 'Laravel MVC', 'MySQL', 'PostgreSQL', 'Docker', 'Git'],
  },
  {
    period: '2021.01 ~ 2021.05',
    title: 'Full Stack Engineer - Java',
    company: 'Shoalter (易貿創投) - 電商專案',
    descriptions: ['修改專案的bug並開發推播功能。'],
    tools: ['Java', 'Spring Boot MVC', 'MySQL', 'Docker', 'RabbitMQ', 'Git'],
  },
  {
    period: '2019.05 ~ 2020.02',
    title: 'Student - Java',
    company: 'Institute for Information Industry (資策會)',
    descriptions: ['資策學員時期完成的專案。'],
    tools: ['Java', 'HTML', 'CSS', 'JavaScript', 'Spring Boot MVC', 'Oracle'],
  },
]
</script>

<style scoped>
.cv-print {
  display: none;
}

@media print {
  .cv-print {
    display: block;
    width: 210mm;
    height: 297mm;
    overflow: hidden;
    background: #111;
    color: #fff;
    padding: 7mm 10mm;
    font-family: 'Nunito', sans-serif;
    font-size: 8pt;
  }

  .cv-header {
    display: flex;
    align-items: center;
    gap: 12px;
    border-bottom: 2px solid #f9ca24;
    padding-bottom: 6px;
    margin-bottom: 8px;
  }

  .cv-avatar {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid #f9ca24;
  }

  .cv-title h1 {
    font-size: 16pt;
    color: #fff;
    margin: 0;
  }

  .cv-title h2 {
    font-size: 9pt;
    color: #f9ca24;
    font-weight: 400;
    margin: 2px 0 0;
  }

  .cv-section {
    margin-bottom: 8px;
  }

  .cv-section-title {
    font-size: 11pt;
    color: #fff;
    border-bottom: 1px solid #333;
    padding-bottom: 2px;
    margin-bottom: 6px;
  }

  .cv-section-title span {
    color: #f9ca24;
  }

  .cv-skills {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .cv-skill-box {
    background: #1e1e1e;
    border: 1px solid #333;
    border-radius: 4px;
    padding: 5px 8px;
    min-width: 90px;
  }

  .cv-skill-category {
    color: #f9ca24;
    font-weight: 600;
    font-size: 7pt;
    margin-bottom: 2px;
    text-transform: uppercase;
  }

  .cv-skill-item {
    color: #ddd;
    font-size: 7pt;
    line-height: 1.4;
  }

  .cv-experiences {
    display: flex;
    flex-direction: column;
    gap: 4px;
  }

  .cv-exp-box {
    background: #1e1e1e;
    border: 1px solid #333;
    border-radius: 4px;
    padding: 5px 8px;
    page-break-inside: avoid;
    break-inside: avoid;
  }

  .cv-exp-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2px;
  }

  .cv-period {
    color: #f9ca24;
    font-size: 7pt;
  }

  .cv-job-title {
    color: #aaa;
    font-size: 7pt;
  }

  .cv-company {
    color: #fff;
    font-weight: 600;
    font-size: 7.5pt;
    margin-bottom: 2px;
  }

  .cv-desc {
    color: #bbb;
    font-size: 7pt;
    line-height: 1.3;
    margin-bottom: 2px;
  }

  .cv-tools {
    display: flex;
    flex-wrap: wrap;
    gap: 2px;
    margin-top: 3px;
  }

  .cv-tag {
    background: #333;
    color: #f9ca24;
    font-size: 6.5pt;
    padding: 1px 4px;
    border-radius: 2px;
  }
}
</style>
