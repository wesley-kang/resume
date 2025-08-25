<script setup lang="ts">
import { ref, reactive, computed } from 'vue'

// 语言切换状态
const currentLang = ref<'zh' | 'en'>('en')

// 切换语言函数
const toggleLanguage = () => {
  currentLang.value = currentLang.value === 'zh' ? 'en' : 'zh'
}

// 多语言文本
const texts = {
  zh: {
    languageSwitch: '中/EN',
    personalSummary: '个人简介',
    skills: '专业技能',
    workExperience: '工作经验',
    projectExperience: '项目经验',
    education: '教育背景',
    certificates: '证书与荣誉',
    achievements: '主要成果：',
    major: '专业：',
    gpa: 'GPA：',
    role: '角色：',
    location: '地点：'
  },
  en: {
    languageSwitch: 'EN/中',
    personalSummary: 'Personal Summary',
    skills: 'Professional Skills',
    workExperience: 'Work Experience',
    projectExperience: 'Project Experience',
    education: 'Education',
    certificates: 'Certificates & Honors',
    achievements: 'Key Achievements:',
    major: 'Major:',
    gpa: 'GPA:',
    role: 'Role:',
    location: 'Location:'
  }
}

// 当前语言文本
const t = computed(() => texts[currentLang.value])

// 个人信息数据（双语）
const personalInfo = reactive({
  zh: {
    name: '康恒',
    title: '全栈工程师',
    email: '940429703@qq.com',
    phone: '+8613049832721',
    location: '深圳市',
    website: 'https://gitee.com/hengk',
    summary: '经验丰富的全栈工程师10年, 热衷于运用前沿技术栈构建响应式、高并发的Web应用.拥有覆盖整个产品生命周期的开发部署经验,' + 
                '深谙前后端架构设计与性能优化。乐于在敏捷开发环境中与产品、设计及测试团队紧密协作，共同将创意高效转化为对用户有价值的卓越产品。'
  },
  en: {
    name: 'Kang Heng',  
    title: 'Full Stack Developer',
    email: '940429703@qq.com',
    phone: '+8613049832721',
    location: 'ShenZhen, China',
    website: 'https://gitee.com/hengk',
    summary: 'Highly motivated and results-oriented FullStack Engineer' +
                ' with 10 years of experience in developing and deploying scalable web applications.' +
                ' Proficient in both front-end and back-end technologies, with a strong focus on building responsive,' + 
                ' user-friendly, and high-performance solutions. ' + 
                ' Adept at problem-solving and collaborating with cross-functional teams to deliver exceptional products.'
  }
})

// 当前语言的个人信息
const currentPersonalInfo = computed(() => personalInfo[currentLang.value])

// 技能数据
const skills = ref([
 
  { name: 'C++', level: 90, category: 'backend' },
  { name: 'Python', level: 90, category: 'backend' },
  { name: 'Golang', level: 80, category: 'backend' },
  { name: 'Vue.js', level: 90, category: 'frontend' },
  { name: 'TypeScript', level: 80, category: 'frontend' },
  { name: 'JavaScript', level: 80, category: 'frontend' }
])

// 工作经验数据（双语）
const experience = reactive({
  zh: [
    {
      id: 1,
      position: '高级前端开发工程师',
      company: 'ABC科技有限公司',
      period: '2022.03 - 至今',
      location: '北京',
      duties: [
        '负责公司主要产品的前端架构设计和开发',
        '带领团队完成多个大型项目的前端开发工作',
        '优化前端性能，提升用户体验30%',
        '制定前端开发规范和最佳实践'
      ]
    },
    {
      id: 2,
      position: '前端开发工程师',
      company: 'XYZ互联网公司',
      period: '2020.06 - 2022.02',
      location: '上海',
      duties: [
        '参与多个Web应用和移动端H5项目的开发',
        '与UI设计师和后端工程师协作完成产品功能',
        '维护和优化现有项目代码，提升代码质量',
        '参与技术选型和架构讨论'
      ]
    }
  ],
  en: [
    {
    id: 1,
    position: 'Software Engineer',
    company: 'Peking University Software Engineering Center',
    period: 'June 2016 - July 2019',
    location: 'Beijing',
    duties: [
        'Responsible for software architecture design and development of main products',
        'Led team to complete software development of multiple large-scale projects',
        'Optimized project performance, improved user experience',
        'Established development standards and best practices'
      ]
    },
    {
      id: 2,
      position: 'Software Engineer',
      company: 'Institute of Automation, Chinese Academy of Sciences',
      period: 'August 2019 - March 2022',
      location: 'Beijing',
      duties: [
        'Implement the algorithm from the paper and try to achieve the results mentioned in the article.',
        'Integrate the algorithm into a real product.',
        'Continuously iterate on the product based on real-world performance.',
      ]
    },
     {
      id: 3,
      position: 'Software Engineer',
      company: 'Baidu, Inc.',
      period: 'April 2022 - May 2023',
      location: 'Shenzhen',
      duties: [
        'eveloping and maintaining core software systems for various products',
        'Collaborating with product managers and other engineering teams to define requirements and implement features that improve user experience.',
        'Optimizing system performance and stability by conducting code reviews, troubleshooting issues, and implementing bug fixes',
      ]
    },
    {
      id: 4,
      position: 'Software Engineer',
      company: 'Wuhan Fengyi Logistics Co., Ltd.',
      period: 'June 2023 - Present',
      location: 'Shenzhen',
      duties: [
        'Responsible for the digitalization of company business processes.',
        'Establish a  development team.',
        'tablish a strict development process.',
      ]
    }
  ]
})

// 当前语言的工作经验
const currentExperience = computed(() => experience[currentLang.value])

// 教育背景数据（双语）
const education = reactive({
  zh: [
    {
      id: 1,
      degree: '本科',
      school: '某某大学',
      major: '计算机科学与技术',
      period: '2016.09 - 2020.06',
      gpa: '3.8/4.0'
    }
  ],
  en: [
    {
      id: 1,
      degree: 'Bachelor\'s Degree',
      school: 'Wuhan University of Science and Technology',
      major: 'Computer Science and Technology',
      period: 'Sep 2012 - Jun 2016',
      gpa: '3.5/4.0'
    }
  ]
})

// 当前语言的教育背景
const currentEducation = computed(() => education[currentLang.value])

// 项目经验数据（双语）
const projects = reactive({
  zh: [
    {
      id: 1,
      name: '企业管理系统',
      period: '2023.01 - 2023.06',
      role: '前端负责人',
      description: '基于Vue3和Element Plus开发的企业内部管理系统，包含用户管理、权限控制、数据统计等功能模块。',
      technologies: ['Vue3', 'TypeScript', 'Element Plus', 'Pinia', 'Vue Router'],
      achievements: ['提升系统响应速度40%', '用户满意度达95%'],
      projectUrl: 'https://github.com/username/enterprise-management-system', // 新增
      demoUrl: 'https://demo.enterprise-system.com' // 新增
    },
    {
      id: 2,
      name: '电商小程序',
      period: '2022.08 - 2022.12',
      role: '核心开发者',
      description: '使用uni-app开发的跨平台电商小程序，支持商品浏览、购物车、订单管理等核心功能。',
      technologies: ['uni-app', 'Vue2', 'uView', 'WeChat API'],
      achievements: ['日活用户超过1万', '转化率提升25%'],
      projectUrl: 'https://github.com/username/enterprise-management-system', // 新增
      demoUrl: 'https://demo.enterprise-system.com' // 新增
    }
  ],
  en: [
    {
      id: 1,
      name: 'A Robust Text Region Detection Algorithm',
      period: 'Jun 2016 - Jul 2019',
      role: 'Responsible person',
      description: 'This text detection algorithm is built upon the Connectionist Text Proposal Network (CTPN),'+
      ' a deep learning framework specifically designed for accurate and robust detection of text in natural scene images.' +
      'The algorithm first extracts convolutional feature maps from the input image using a Convolutional Neural Network (CNN),'+
      ' typically VGG16. A bidirectional LSTM (Bi-LSTM) layer is then applied on top of these features to capture sequential patterns in horizontal text lines,' + 
      " enhancing the model's ability to understand context along the width of text regions.",
      technologies: ['c++', 'tensorflow'],
      achievements: ['Improved system response speed by 40%', 'Accuracy reached 95%'],
      projectUrl: 'https://gitee.com/hengk/ctpn',
      demoUrl: '' // 新增
    },
    {
      id: 2,
      name: 'A Fast Water Meter Text Recognition Algorithm',
      period: 'Aug 2019 - Mar 2022',
      role: 'Responsible person',
      description: 'This project is a water meter text recognition algorithm. The algorithm is based on the deep learning'+
      ' framework caffe. The algorithm is trained on a dataset of water meter images.' +
      ' The algorithm is able to recognize the text on the water meter. The algorithm is fast and accurate.' +
      'The proposed algorithm is a unified pipeline for end-to-end scene text reading, combining the strengths' + 
      ' of the SSD (Single Shot MultiBox Detector) for text detection and the CRNN (Convolutional Recurrent ' + 
      'Neural Network) for text recognition. In the first stage, SSD is employed to rapidly and accurately localize text'+
      ' regions within the input image. Leveraging its multi-scale feature maps and single-shot detection mechanism, SSD ' + 
      'efficiently generates bounding boxes around potential text instances, even under varying scales and orientations.' + 
      ' This stage ensures real-time performance, which is critical for applications on resource-constrained devices.' + 
      'he detected text regions are then cropped and fed into the CRNN model for recognition. CRNN combines convolutional' + 
      ' layers to extract visual features, bidirectional LSTM layers to model contextual information along the sequence, and ' + 
      ' a Connectionist Temporal Classification (CTC) layer to transcribe the features into character sequences without requiring ' + 
      ' character segmentation. This enables robust recognition of text strings with diverse fonts, colors, and backgrounds.',
      achievements: ['Improved system response speed by 50%', 'Accuracy reached 95%'],
      technologies: ['c++', 'caffe'],
      projectUrl: '',
      demoUrl: '' // 
   
    }
  ]
})

// 当前语言的项目经验
const currentProjects = computed(() => projects[currentLang.value])

// 证书和荣誉（双语）
const certificates = reactive({
  zh: [
    {
      id: 1,
      name: 'Vue.js 认证开发者',
      issuer: 'Vue.js官方',
      date: '2023.05'
    },
    {
      id: 2,
      name: '优秀员工',
      issuer: 'ABC科技有限公司',
      date: '2023.12'
    }
  ],
  en: [
    {
      id: 1,
      name: 'Vue.js Certified Developer',
      issuer: 'Vue.js Official',
      date: 'May 2023'
    },
    {
      id: 2,
      name: 'Outstanding Employee',
      issuer: 'ABC Technology Co., Ltd.',
      date: 'Dec 2023'
    }
  ]
})

// 当前语言的证书
const currentCertificates = computed(() => certificates[currentLang.value])
</script>

<template>
  <div class="resume-container">
    <!-- 语言切换按钮 -->
    <div class="language-switch">
      <button @click="toggleLanguage" class="lang-btn">
        {{ t.languageSwitch }}
      </button>
    </div>

    <!-- 头部个人信息 -->
    <header class="header">
      <div class="profile-section">
        <div class="avatar">
          <div class="avatar-placeholder">
            {{ currentPersonalInfo.name.charAt(0) }}
          </div>
        </div>
        <div class="basic-info">
          <h1 class="name">{{ currentPersonalInfo.name }}</h1>
          <p class="title">{{ currentPersonalInfo.title }}</p>
          <div class="contact-info">
            <div class="contact-item">
              <span class="icon">📧</span>
              <span>{{ currentPersonalInfo.email }}</span>
            </div>
            <div class="contact-item">
              <span class="icon">📱</span>
              <span>{{ currentPersonalInfo.phone }}</span>
            </div>
            <div class="contact-item">
              <span class="icon">📍</span>
              <span>{{ currentPersonalInfo.location }}</span>
            </div>
            <div class="contact-item">
              <span class="icon">🌐</span>
              <a :href="currentPersonalInfo.website" target="_blank">{{ currentPersonalInfo.website }}</a>
            </div>
          </div>
        </div>
      </div>
    </header>

    <main class="main-content">
      <!-- 个人简介 -->
      <section class="section">
        <h2 class="section-title">{{ t.personalSummary }}</h2>
        <p class="summary">{{ currentPersonalInfo.summary }}</p>
      </section>

      <!-- 专业技能 -->
      <section class="section">
        <h2 class="section-title">{{ t.skills }}</h2>
        <div class="skills-grid">
          <div v-for="skill in skills" :key="skill.name" class="skill-item">
            <div class="skill-header">
              <span class="skill-name">{{ skill.name }}</span>
              <span class="skill-level">{{ skill.level }}%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" :style="{ width: skill.level + '%' }"></div>
            </div>
          </div>
        </div>
      </section>

      <!-- 工作经验 -->
      <section class="section">
        <h2 class="section-title">{{ t.workExperience }}</h2>
        <div class="experience-list">
          <div v-for="exp in currentExperience" :key="exp.id" class="experience-item">
            <div class="exp-header">
              <div class="exp-title-group">
                <h3 class="exp-title">{{ exp.position }}</h3>
                <p class="exp-company">{{ exp.company }} · {{ exp.location }}</p>
              </div>
              <span class="exp-period">{{ exp.period }}</span>
            </div>
            <ul class="exp-duties">
              <li v-for="duty in exp.duties" :key="duty">{{ duty }}</li>
            </ul>
          </div>
        </div>
      </section>

      <!-- 项目经验 -->
      <section class="section">
        <h2 class="section-title">{{ t.projectExperience }}</h2>
        <div class="projects-list">
          <div v-for="project in currentProjects" :key="project.id" class="project-item">
            <div class="project-header">
              <div class="project-title-group">
                <h3 class="project-name">{{ project.name }}</h3>
                <p class="project-role">{{ t.role }} {{ project.role }}</p>
              </div>
              <span class="project-period">{{ project.period }}</span>
            </div>
            <p class="project-desc">{{ project.description }}</p>
                  <!-- 新增项目地址部分 -->
            <div class="project-links" v-if="project.projectUrl || project.demoUrl">
              <a v-if="project.projectUrl" :href="project.projectUrl" target="_blank" class="project-link">
                <span class="link-icon">🔗</span>
                {{ currentLang === 'zh' ? '项目地址' : 'Project URL' }}
              </a>
              <!-- <a v-if="project.demoUrl" :href="project.demoUrl" target="_blank" class="project-link demo-link">
                <span class="link-icon">🚀</span>
                {{ currentLang === 'zh' ? '在线演示' : 'Live Demo' }}
              </a> -->
            </div>
            <div class="project-tech">
              <span v-for="tech in project.technologies" :key="tech" class="tech-tag">{{ tech }}</span>
            </div>
            <div class="project-achievements">
              <h4>{{ t.achievements }}</h4>
              <ul>
                <li v-for="achievement in project.achievements" :key="achievement">{{ achievement }}</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- 教育背景 -->
      <section class="section">
        <h2 class="section-title">{{ t.education }}</h2>
        <div class="education-list">
          <div v-for="edu in currentEducation" :key="edu.id" class="education-item">
            <div class="edu-header">
              <div class="edu-title-group">
                <h3 class="edu-degree">{{ edu.degree }}</h3>
                <p class="edu-school">{{ edu.school }}</p>
              </div>
              <span class="edu-period">{{ edu.period }}</span>
            </div>
            <p class="edu-details">{{ t.major }}{{ edu.major }} | {{ t.gpa }}{{ edu.gpa }}</p>
          </div>
        </div>
      </section>

      <!-- 证书和荣誉 -->
      <!-- <section class="section">
        <h2 class="section-title">{{ t.certificates }}</h2>
        <div class="certificates-list">
          <div v-for="cert in currentCertificates" :key="cert.id" class="certificate-item">
            <div class="cert-info">
              <h3 class="cert-name">{{ cert.name }}</h3>
              <p class="cert-issuer">{{ cert.issuer }}</p>
            </div>
            <span class="cert-date">{{ cert.date }}</span>
          </div>
        </div>
      </section> -->
    </main>
  </div>
</template>

<style scoped>
.resume-container {
  max-width: 1000px;
  margin: 0 auto;
  background: white;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
  min-height: 100vh;
  position: relative;
}

.language-switch {
  position: absolute;
  top: 20px;
  right: 20px;
  z-index: 100;
}

.lang-btn {
  background: rgba(255, 255, 255, 0.9);
  border: 2px solid #667eea;
  color: #667eea;
  padding: 8px 16px;
  border-radius: 20px;
  cursor: pointer;
  font-weight: 500;
  font-size: 0.9rem;
  transition: all 0.3s ease;
  backdrop-filter: blur(10px);
}

.lang-btn:hover {
  background: #667eea;
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.3);
}

.header {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 60px 40px 40px;
}

.profile-section {
  display: flex;
  align-items: center;
  gap: 30px;
}

.avatar {
  flex-shrink: 0;
}

.avatar-placeholder {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 3rem;
  font-weight: bold;
  border: 4px solid rgba(255, 255, 255, 0.3);
}

.basic-info {
  flex: 1;
}

.name {
  font-size: 2.5rem;
  font-weight: 700;
  margin: 0 0 10px 0;
}

.title {
  font-size: 1.2rem;
  margin: 0 0 20px 0;
  opacity: 0.9;
}

.contact-info {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.contact-item {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.95rem;
}

.contact-item a {
  color: white;
  text-decoration: none;
}

.contact-item a:hover {
  text-decoration: underline;
}

.icon {
  font-size: 1.1rem;
}

.main-content {
  padding: 40px;
}

.section {
  margin-bottom: 40px;
}

.section-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #2d3748;
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid #667eea;
}

.summary {
  font-size: 1rem;
  line-height: 1.6;
  color: #4a5568;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 20px;
}

.skill-item {
  background: #f7fafc;
  padding: 20px;
  border-radius: 8px;
  border-left: 4px solid #667eea;
}

.skill-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.skill-name {
  font-weight: 500;
  color: #2d3748;
}

.skill-level {
  font-weight: 600;
  color: #667eea;
}

.skill-bar {
  height: 8px;
  background: #e2e8f0;
  border-radius: 4px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  background: linear-gradient(90deg, #667eea, #764ba2);
  border-radius: 4px;
  transition: width 0.3s ease;
}

.experience-list,
.education-list,
.projects-list,
.certificates-list {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.experience-item,
.education-item,
.project-item,
.certificate-item {
  background: #f7fafc;
  padding: 25px;
  border-radius: 8px;
  border-left: 4px solid #667eea;
}

.exp-header,
.edu-header,
.project-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  margin-bottom: 15px;
}

.exp-title,
.edu-degree,
.project-name {
  font-size: 1.2rem;
  font-weight: 600;
  color: #2d3748;
  margin: 0 0 5px 0;
}

.exp-company,
.edu-school,
.project-role {
  font-weight: 500;
  color: #4a5568;
  margin: 0;
  font-size: 0.95rem;
}

.exp-period,
.edu-period,
.project-period {
  background: #667eea;
  color: white;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
  white-space: nowrap;
}

.edu-details {
  color: #718096;
  margin: 10px 0 0 0;
  font-size: 0.9rem;
}

.exp-duties {
  list-style: none;
  padding: 0;
  margin: 0;
}

.exp-duties li {
  position: relative;
  padding-left: 20px;
  margin-bottom: 8px;
  color: #4a5568;
  line-height: 1.5;
}

.exp-duties li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: #667eea;
  font-weight: bold;
}

.project-desc {
  color: #4a5568;
  line-height: 1.6;
  margin: 0 0 15px 0;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-bottom: 15px;
}

.tech-tag {
  background: #667eea;
  color: white;
  padding: 4px 10px;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 500;
}

.project-achievements h4 {
  color: #2d3748;
  font-size: 0.9rem;
  margin: 0 0 8px 0;
}

.project-achievements ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.project-achievements li {
  position: relative;
  padding-left: 20px;
  margin-bottom: 5px;
  color: #4a5568;
  font-size: 0.9rem;
}

.project-achievements li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #48bb78;
  font-weight: bold;
}

.certificate-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.cert-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: #2d3748;
  margin: 0 0 5px 0;
}

.cert-issuer {
  color: #4a5568;
  margin: 0;
  font-size: 0.9rem;
}

.cert-date {
  background: #667eea;
  color: white;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .language-switch {
    top: 10px;
    right: 10px;
  }
  
  .lang-btn {
    padding: 6px 12px;
    font-size: 0.8rem;
  }
  
  .header {
    padding: 50px 20px 30px;
  }
  
  .profile-section {
    flex-direction: column;
    text-align: center;
    gap: 20px;
  }
  
  .name {
    font-size: 2rem;
  }
  
  .contact-info {
    justify-content: center;
    flex-direction: column;
    gap: 10px;
  }
  
  .main-content {
    padding: 30px 20px;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .exp-header,
  .edu-header,
  .project-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
  }
  
  .certificate-item {
    flex-direction: column;
    align-items: flex-start;
    gap: 10px;
  }
}

/* 语言切换动画 */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
/* 在现有样式中添加项目链接样式 */
.project-links {
  margin: 12px 0;
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.project-link {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 12px;
  background: #f8f9fa;
  border: 1px solid #e9ecef;
  border-radius: 6px;
  text-decoration: none;
  color: #495057;
  font-size: 14px;
  transition: all 0.2s ease;
}

.project-link:hover {
  background: #e9ecef;
  border-color: #007bff;
  color: #007bff;
  transform: translateY(-1px);
}

.project-link.demo-link:hover {
  border-color: #28a745;
  color: #28a745;
}

.link-icon {
  font-size: 16px;
}

@media print {
  .project-link {
    background: none;
    border: none;
    padding: 0;
    color: #333;
  }
  
  .project-link:after {
    content: " (" attr(href) ")";
    font-size: 12px;
    color: #666;
  }
}
</style>