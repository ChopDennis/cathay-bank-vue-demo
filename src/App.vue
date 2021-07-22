<template>
  <div id="nav">
    <div class="row">
      <div class="col-6 px-lg-3 text-end text-lg-start p-0">
        <router-link to="/">
        <picture>
          <source
            media="(min-width: 992px)"
            srcset="./assets/images/logo--pc.png"
          />
          <img
            to="/"
            alt="Cathay Bank Logo"
            height="50"
            src="./assets/images/logo--mobile.png"
          />
        </picture>
        </router-link>
      </div>
      <div class="col-6 px-lg-3 text-start text-lg-end p-0">
        <router-link to="/service"><p style="padding-top: 5px;">立即購</p></router-link>
      </div>
    </div>
  </div>
  <router-view />
  <div class="px-0 pt-3" id="footer">
    <div class="row">
      <div class="col-lg-1 offset-lg-2">
        <p class="font-bold d-none d-lg-block">
          謹&nbsp;慎&nbsp;理&nbsp;財<br />信&nbsp;用&nbsp;無&nbsp;價
        </p>
        <p class="d-lg-none text-center">
          謹慎理財&nbsp;信用無價
        </p>
      </div>
      <div class="col-lg-9  px-5 font-light">
        <p class="description">
          信用卡暨預借現金之各级別循環信用年利率為6.75%~15%（依本行信用評分制度定期評估,循環利率之基準日為104年9月1日）。<br />
          預借現金手續費：預借現金金額乘以3%加上新臺幣150元或美元5元，其他相關費用係依本行網站公告。
        </p>
      </div>
    </div>
    <div class="copyright text-center pt-3 pb-1">
      <p>&copy;&nbsp;國泰世華商業銀行股份有限公司</p>
    </div>
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;700&family=Roboto&display=swap");
@import "~bootstrap/scss/bootstrap";
@import "assets/scss/main";
</style>
