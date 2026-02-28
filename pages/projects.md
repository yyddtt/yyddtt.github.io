---
layout: page
title: Projects
permalink: /projects/
hide_title: true
---

<div class="projects-container">
  <!-- Mobile Fluid Simulation Project -->
  <div class="project-card fade-up">
    <div class="project-header">
      <h3>移动端流体仿真与交互</h3>
      <span class="status-badge wip">开发中</span>
    </div>
    
    <div class="tech-stack">
      <span class="tech-tag"><i class="fas fa-code"></i> Unity</span>
      <span class="tech-tag"><i class="fas fa-layer-group"></i> MPM</span>
      <span class="tech-tag"><i class="fas fa-atom"></i> PBF</span>
      <span class="tech-tag"><i class="fas fa-mobile-alt"></i> Mobile</span>
    </div>

    <p>
      这是一个面向移动设备的实验性实时流体仿真框架。
      该项目同时对比SPH和MPM在移动端的功耗和帧率，基于屏幕空间渲染在资源受限的硬件上实现稳定且高效的流固耦合交互。
    </p>
    
    <div class="project-links">
      <a href="#" onclick="alert('项目仓库即将上线，敬请期待！'); return false;">
        <i class="fab fa-github"></i> 查看 GitHub
      </a>
    </div>
  </div>

  <!-- Placeholder for future projects -->
  <!-- 
  <div class="project-card fade-up">
    ...
  </div> 
  -->
</div>

<script>
  // 简单的淡入动画
  document.addEventListener("DOMContentLoaded", function() {
    const cards = document.querySelectorAll('.fade-up');
    cards.forEach((card, index) => {
      setTimeout(() => {
        card.style.opacity = '1';
        card.style.transform = 'translateY(0)';
      }, index * 150 + 100);
    });
  });
</script>