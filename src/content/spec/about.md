# 關於我

<script>
  // 計算年齡
  const birthYear = 2010; // 假設你的出生年份是2000年
  const currentYear = new Date().getFullYear();
  const age = currentYear - birthYear;

  // 將年齡插入到指定的元素中
  //   document.addEventListener('DOMContentLoaded', () => {
  //     document.getElementById('age').textContent = age;
  //   });
  
  let school_level = "";
  // 依據年齡計算當前的學級是國中、高中還是大學
  if (age <= 16) {
    school_level = "國中";
  } else if (age <= 19) {
    school_level = "高中";
  } else {
    school_level = "大學";
  }

  document.addEventListener('DOMContentLoaded', () => {
    document.getElementById('school-level').textContent = school_level;
  });
</script>

一個熱愛技術、喜歡折騰各種開源項目的<span id="school-level"></span>學生兼部落客。  

## 🔧 我的興趣與專長  

- **Minecraft 開服與伺服器管理** 🛠️  
  經營了 **雲羽憧憬**（Java 版）與 **銅鑼灣伺服器**（基岩版），探索各種插件與優化技術。  

- **部落格經營** ✍️  
  撰寫技術教學，主題涵蓋 **Minecraft 開服、WordPress 架站、自由軟體與程式開發**。  

- **程式開發** 💻  
  - 開發 **MinePlayer**（Python 套件，用於獲取 Minecraft 玩家資訊）  
  - 開發 **cfbot**（Discord 機器人，整合 Pterodactyl、DiscordSRV、客服單等功能）  
  - 使用 **TypeScript / Node.js** 製作 UI 組件與靜態網站  

## 🌱 目前在學習  
- 使用 **Astro** 搭建靜態網站  
- **shadcn** 來製作 UI 組件  
- **Yarn** 管理前端專案  

## 📢 關於我  
- **部落格**：[SamHacker Blog](https://samhacker.xyz)
- **Minecraft 伺服器**：[雲羽憧憬](https://whiterdoc.lnstw.xyz/) | 銅鑼灣伺服器
- **GitHub**：[github.com/SamHacker](https://github.com/SamHacker)

如果你對我的項目感興趣，歡迎一起討論交流！🚀
