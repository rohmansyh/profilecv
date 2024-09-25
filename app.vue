<template>
  <div>
    <header>
      <h1>{{ name }}</h1>
      <p>{{ title }} | {{ location }} | {{ contactInfo }}</p>
    </header>

    <div class="container">
      <div class="profile">
        <img :src="profilePicture" alt="Your Photo" />
        <div class="profile-info">
          <h2>{{ name }}</h2>
          <p>{{ jobTitle }}</p>
          <p>
            Email: <a :href="'mailto:' + email" class="link">{{ email }}</a> |
            Phone: <span class="phone">{{ phone }}</span>
          </p>
          <div class="button-container">
            <a :href="linkedinUrl" class="button">LinkedIn</a>
            <a :href="githubUrl" class="button">GitHub</a>
          </div>
        </div>
      </div>

      <div class="section">
        <h3>Tentang saya</h3>
        <p>{{ aboutMe }}</p>
      </div>

      <div class="section">
        <h3>Pengalaman</h3>
        <ul>
          <li v-for="experience in experiences" :key="experience.title">
            <span>{{ experience.title }} - {{ experience.company }}</span> ({{ experience.years }})
            <p>{{ experience.description }}</p>
          </li>
        </ul>
      </div>

      <div class="section">
        <h3>Edukasi</h3>
        <ul>
          <li v-for="education in educations" :key="education.degree">
            <span>{{ education.degree }} - {{ education.school }}</span> ({{ education.years }})
            <p>{{ education.description }}</p>
          </li>
        </ul>
      </div>

      <div class="section">
        <h3>Skills</h3>
        <ul>
          <li v-for="skill in skills" :key="skill">{{ skill }}</li>
        </ul>
      </div>

      <div class="section">
        <h3>Projects</h3>
        <ul>
          <li v-for="project in projects" :key="project.name">
            <span>{{ project.name }}</span>
            <p>{{ project.description }}</p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Hai! saya Rohman",
      title: "Mahasiswa D3 Teknologi Informasi",
      location: "Jl. Terusan Ijen No.861 Malang",
      contactInfo: "Contact Information",
      profilePicture: "https://s1.bukalapak.com/uploads/content_attachment/b23f3bae00e8d7627f23dcb5/original/1007-Tip_Hemat_budget_backpacking_ke_jepang.jpg", // Ganti dengan URL gambar yang sesuai
      jobTitle: "Web Developer |Web Designer |",
      email: "abdurrohmansyh02@gmail.com",
      phone: "+6287820170541",
      linkedinUrl: "https://www.linkedin.com/in/abdur-rohman-syah-sjadja-ah-5a037b289?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app",
      githubUrl: "https://github.com/yourusername",
      aboutMe: "Halo nama saya Abdur Rohman Syah dari Fakultas Vokasi jurusan Teknologi Informasi, saya sekarang sedang menempuh semester 3 di Universitas Brawijaya.",
      experiences: [
        { title: "Job Title", company: "Company Name", years: "Year - Year", description: "Describe your responsibilities and achievements in this role." },
        { title: "Job Title", company: "Company Name", years: "Year - Year", description: "Describe your responsibilities and achievements in this role." }
      ],
      educations: [
        { degree: "D3 Teknologi Informasi", school: "Universitas Brawijaya", years: "2023 - now", description: "Relevant coursework or achievements." }
      ],
      skills: ["HTML", "CSS", "PHP", "JavaScript", "Figma", "Nuxt.js", "MySQL"],
      projects: [
        { name: "Project Name", description: "No project yet." },
        { name: "Project Name", description: "No project yet." }
      ]
    };
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
  color: #333;
  background-color: #f4f4f4;
  padding: 20px;
}

header {
  text-align: center;
  padding: 40px 0;
  background: linear-gradient(to right, #2b013b, #230455);
  color: #fff;
  border-radius: 10px;
}

header h1 {
  font-size: 2.5rem;
  font-weight: 600;
}

.container {
  max-width: 960px;
  margin: 20px auto;
  padding: 20px;
  background-color: #fff;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  border-radius: 8px;
}

.profile {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  align-items: center;
}

.profile img {
  width: 120px;
  height: 120px;
  border-radius: 50%;
}

.profile-info {
  flex: 1;
}

.profile-info h2 {
  font-size: 1.8rem;
  color: #333;
}

.profile-info p {
  color: #555;
  font-size: 1rem;
}

.button-container {
  margin-top: 15px;
}

.button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #220552;
  color: #fff;
  border-radius: 20px;
  text-decoration: none;
  font-weight: 600;
  transition: background 0.3s ease;
}

.button:hover {
  background-color: #0056b3;
}

.section {
  margin: 20px 0;
}

.section h3 {
  font-size: 1.5rem;
  color: #007bff;
  margin-bottom: 15px;
}

.section ul {
  list-style-type: none;
}

.section li {
  background: #f9f9f9;
  padding: 10px;
  border-radius: 6px;
  margin-bottom: 10px;
  transition: background-color 0.3s ease;
}

.section li:hover {
  background-color: #e6f7ff;
}

.link, .phone {
  color: #007bff;
  font-weight: 600;
}

@media (max-width: 768px) {
  .container {
    padding: 10px;
  }

  .profile img {
    width: 100px;
    height: 100px;
  }

  .profile-info h2 {
    font-size: 1.5rem;
  }

  .button {
    padding: 8px 16px;
  }
}
</style>
