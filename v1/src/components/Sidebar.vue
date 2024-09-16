<template>
  <div class="sidebar" data-background-color="dark">
    <div class="sidebar-logo">
      <div class="logo-header" data-background-color="dark">
        <img
          src="/src/assets/img/kaiadmin/logo_light.svg"
          alt="navbar brand"
          class="navbar-brand"
          height="20"
        />
      </div>
    </div>
    <div class="sidebar-wrapper scrollbar scrollbar-inner">
      <div class="sidebar-content">
        <ul class="nav nav-secondary">
          <li class="nav-section">
            <span class="sidebar-mini-icon"><i class="fa fa-ellipsis-h"></i></span>
            <h4 class="text-section">Laravel Queries</h4>
          </li>
          <li class="nav-item active">
            <router-link to="./">
              <i class="fas fa-layer-group"></i>
              <p>Insert Record</p>
            </router-link>
          </li>
          <li class="nav-item">
            <router-link to="./getrecord">
              <i class="fas fa-layer-group"></i>
              <p>Get Record</p>
            </router-link>
          </li>
          <li class="nav-item">
            <router-link to="./editrecord">
              <i class="fas fa-layer-group"></i>
              <p>Edit Record</p>
            </router-link>
          </li>
          <li class="nav-item">
            <router-link to="./deleterecord">
              <i class="fas fa-layer-group"></i>
              <p>Delete Record</p>
            </router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>