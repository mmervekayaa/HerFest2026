<template>
  <div class="speakers-page">
    <div class="container">
      <h2 class="section-title">KONUŞMACILAR</h2>

      
      <div class="speakers-grid">
        <div v-for="(speaker, index) in speakers" :key="index" class="speaker-card">
          <div class="speaker-image">
            <img :src="speaker.image" :alt="speaker.name" />
            <div class="speaker-overlay">
              <div class="social-links">
                <a v-if="speaker.linkedin" :href="speaker.linkedin" target="_blank" class="social-link">
                  <i class="fab fa-linkedin"></i>
                </a>
                <a v-if="speaker.twitter" :href="speaker.twitter" target="_blank" class="social-link">
                  <i class="fab fa-twitter"></i>
                </a>
                <a v-if="speaker.github" :href="speaker.github" target="_blank" class="social-link">
                  <i class="fab fa-github"></i>
                </a>
              </div>
            </div>
          </div>
          <div class="speaker-info">
            <h3>{{ speaker.name }}</h3>
            <p class="title">{{ speaker.title }}</p>
            <div class="tags">
              <span v-for="(tag, tagIndex) in speaker.tags" :key="tagIndex" class="tag">
                {{ tag }}
              </span>
            </div>
            <p v-for="(paragraph, pIndex) in speaker.bio" :key="pIndex" class="bio">{{ paragraph }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SpeakersPage',
  data() {
    return {
      speakers: [
        {
          name: 'Prof. Dr. Ebru Akpınar',
          title: 'Mühendislik Fakültesi Dekanı, Fırat Üniversitesi',
          image: require('@/assets/Ebru_Akpinar.jpg'),
          tags: ['Akademisyen', 'Mühendislik', 'Teknoloji'],
          bio: [
            'Fırat Üniversitesi Mühendislik Fakültesi Dekanı Prof. Dr. Ebru Akpınar, akademik tecrübeleri ve vizyonu ile teknoloji ve mühendislik alanındaki gelişim süreçlerini desteklemektedir.'
          ],
          linkedin: 'https://www.linkedin.com/in/dr-ebru-kavak-akpinar-96a38848?utm_source=share_via&utm_content=profile&utm_medium=member_ios'
        },
        {
          name: 'Sercan Akdemir',
          title: 'Global Teknoloji Lideri & Speak Up Kurucusu',
          image: require('@/assets/Sercan_Akdemir.jpg'),
          tags: ['Global Teknoloji', 'Girişimci', 'Liderlik'],
          bio: [
            'Global teknoloji lideri ve Speak Up kurucusu Sercan Akdemir, teknoloji ve iletişim ekosistemindeki tecrübeleriyle vizyoner bir bakış açısı sunmaktadır.'
          ],
          linkedin: 'https://www.linkedin.com/in/sercan-akdemir-aktuglu-5234618?utm_source=share_via&utm_content=profile&utm_medium=member_ios'
        },
        {
          name: 'Oya Sertdemir Düşmez',
          title: 'Redcolour Boya ve Özel Bilgem Okulları Başkanı',
          image: require('@/assets/Oya_Sertdemir_Dusmez.jpg'),
          tags: ['Girişimci', 'Eğitim', 'Liderlik'],
          bio: [
            'Redcolour Boya ve Özel Bilgem Okulları Başkanı Oya Sertdemir Düşmez, ticari girişimcilik ve eğitim vizyonuyla farklı sektörlere ivme ve değer kazandırmaktadır.'
          ],
          linkedin: 'https://www.linkedin.com/in/oya-sertdemir-düşmez-831568200?utm_source=share_via&utm_content=profile&utm_medium=member_ios'
        },
        {
          name: 'Gözde Aydın',
          title: 'Core Logistics Platform Deputy General Manager',
          image: require('@/assets/gozde_aydin_yeni.jpg'),
          tags: ['Lojistik', 'Teknoloji', 'Liderlik'],
          bio: [
            'Core Logistics Platform Deputy General Manager olarak görev alan Gözde Aydın, teknoloji ve lojistik ekosistemindeki vizyoner tecrübelerini katılımcılarla paylaşacaktır.'
          ],
          linkedin: 'https://www.linkedin.com/in/gozdeaydin?utm_source=share_via&utm_content=profile&utm_medium=member_ios'
        }
      ]
    }
  }
}
</script>

<style scoped>
.speakers-page {
  padding: 120px 0;
  min-height: 100vh;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

h2 {
  text-align: center;
  color: #2F3C4E;
  font-size: 3.5rem;
  font-weight: 700;
  margin-bottom: 20px;
  font-family: 'Poppins', sans-serif;
  position: relative;
  display: inline-block;
  left: 50%;
  transform: translateX(-50%);
  letter-spacing: 1px;
  background: linear-gradient(135deg, #2F3C4E 0%, #c026d3 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

h2::after {
  content: '';
  position: absolute;
  bottom: -15px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background: #c026d3;
  border-radius: 3px;
}

.section-subtitle {
  text-align: center;
  color: #2F3C4E;
  font-size: 1.2rem;
  margin-bottom: 60px;
  opacity: 0.8;
  font-family: 'Poppins', sans-serif;
  font-weight: 400;
  letter-spacing: 0.5px;
  margin-top: 30px;
}

.speakers-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 30px;
  margin-top: 40px;
}

.speaker-card {
  display: flex;
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  position: relative;
  height: auto;
}

.speaker-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.speaker-image {
  flex: 0 0 300px;
  width: 300px;
  height: auto;
  overflow: hidden;
  position: relative;
}

.speaker-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  transition: transform 0.3s ease;
}

.speaker-card:hover .speaker-image img {
  transform: scale(1.1);
}

.speaker-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(192, 38, 211, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.speaker-card:hover .speaker-overlay {
  opacity: 1;
}

.social-links {
  display: flex;
  gap: 20px;
}

.social-link {
  color: white;
  font-size: 1.5rem;
  transition: transform 0.3s ease;
}

.social-link:hover {
  transform: scale(1.2);
}

.speaker-info {
  flex: 1;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.speaker-info h3 {
  color: #2F3C4E;
  font-size: 1.8rem;
  margin-bottom: 10px;
  font-weight: 600;
  font-family: 'Poppins', sans-serif;
}

.speaker-info .title {
  color: #c026d3;
  font-size: 1.1rem;
  margin-bottom: 15px;
  font-weight: 500;
  font-family: 'Poppins', sans-serif;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-bottom: 20px;
}

.tag {
  background: rgba(192, 38, 211, 0.1);
  color: #c026d3;
  padding: 5px 15px;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
  font-family: 'Poppins', sans-serif;
}

.bio {
  color: #2F3C4E;
  line-height: 1.6;
  font-size: 1rem;
  margin-bottom: 10px;
  font-family: 'Poppins', sans-serif;
}

@media (max-width: 768px) {
  .speakers-page {
    padding: 80px 0;
  }

  h2 {
    font-size: 2.5rem;
  }

  .section-subtitle {
    font-size: 1.1rem;
    margin-bottom: 40px;
  }

  .speakers-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .speaker-card {
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .speaker-image {
    width: 80%;
    max-width: 350px;
    height: auto;
    margin: 0 auto 20px auto;
  }

  .speaker-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .speaker-info {
    width: 100%;
    text-align: center;
  }

  .speaker-tags {
    justify-content: center;
  }

  .speaker-links {
    justify-content: center;
  }

  .speaker-info h3 {
    font-size: 1.5rem;
  }

  .speaker-info .title {
    font-size: 1rem;
  }

  .tags {
    justify-content: center;
  }

  .tags .tag {
    font-size: 0.8rem;
  }

  .bio {
    font-size: 0.9rem;
    -webkit-line-clamp: unset;
    max-height: unset;
  }
}
</style> 