<template>
  <div id="home">
    <div class="container-fluid p-0">
      <picture>
        <source
          media="(min-width: 992px)"
          srcset="../assets/images/banner-home--pc.png"
        />
        <img
          class="img-fluid"
          alt="Cathay Bank Home Banner"
          src="../assets/images/banner-home--mobile.png"
        />
      </picture>
    </div>
    <div id="home-body">
      <div class="container p-lg-5 p-3">
        <!-- 歡迎標題 -->
        <div class="row">
          <div class="offset-lg-1">
            <p class="font-bold text-start px-3 d-none d-lg-block">
              立即購快捷支付，登錄開通好康多！
            </p>
            <p class="font-bold text-center px-3 d-lg-none">
              立即購快捷支付<br />登錄開通好康多！
            </p>
          </div>
        </div>
        <!-- 流程圖 -->
        <div class="row">
          <!-- Step 1 -->
          <div class="col-lg-4 text-center">
            <div class="container">
              <p class="font-step">Step 1</p>
              <img
                class="img-fluid"
                alt="Step-1"
                src="../assets/images/prepare-paper.png"
              />
              <p class="font-bold">國泰世華銀行<br />登錄立即購服務</p>
            </div>
          </div>
          <!-- Step 2 -->
          <div class="col-lg-4 text-center">
            <div class="row">
              <div class="col-lg-2 step-icon">
                <img src="../assets/images/icon_p.png" />
              </div>
              <div class="col-lg-8">
                <div class="container">
                  <p class="font-step">Step 2</p>
                  <img
                    class="img-fluid"
                    alt="Step-2"
                    src="../assets/images/upload-success-pc.png"
                  />
                  <p class="font-bold">TreeMall 開通<br />立即購服務</p>
                </div>
              </div>
              <div class="col-lg-2 step-icon">
                <img src="../assets/images/icon_p.png" />
              </div>
            </div>
          </div>
          <!-- Step 3 -->
          <div class="col-lg-4 text-center">
            <div class="container">
              <p class="font-step">Step 3</p>
              <img
                class="img-fluid"
                alt="Step-3"
                src="../assets/images/shopping-bag.png"
              />
              <p class="font-bold">TreeMall 開始使用<br />立即購服務</p>
            </div>
          </div>
        </div>
        <!-- 跳轉按鈕 -->
        <div class="container-fluid text-center p-lg-5 py-3">
          <router-link to="/service">
            <button class="btn btn-primary px-5 rounded-pill">
              立即購服務登錄
            </button>
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>
