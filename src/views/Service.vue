<template>
  <div id="service">
    <div class="container-fluid p-0">
      <picture>
        <source
          media="(min-width: 992px)"
          srcset="../assets/images/banner-service--pc.png"
        />
        <img
          class="img-fluid"
          alt="Cathay Bank Service"
          src="../assets/images/banner-service--mobile.png"
        />
      </picture>
    </div>
    <div id="service-body">
      <!-- 輸入資料 -->
      <div class="container-fluid py-lg-5 py-3">
        <!-- 身分證後 5 碼 -->
        <div class="row py-3">
          <div class="col-lg-4 text-lg-end pt-1">
            <p class="d-none d-lg-block">持卡人身分證後5碼</p>
            <p class="d-lg-none">身分證字號／統編</p>
          </div>
          <div class="col-lg-6">
            <input
              type="text"
              class="form-control"
              name="inputId"
              v-model="inputId"
              :class="{ 'error-input': inputIdError }"
              placeholder="請輸入身分證後5碼"
              pattern="\d*" 
              maxlength="5"
            />
            <p class="error-message">{{ inputIdErrMsg }}</p>
          </div>
        </div>
        <!-- 信用卡號 -->
        <div class="row py-3">
          <div class="col-lg-4 text-lg-end pt-1">
            <p>開通的信用卡／i 刷金融卡卡號</p>
          </div>
          <div class="col-lg-6">
            <div class="row">
              <div class="col-3 pe-1 ps-0">
                <input
                  type="text"
                  name="card-number-1"
                  v-model="cardNumber_1"
                  class="form-control"
                  placeholder="****"
                  pattern="\d*" 
                  maxlength="4"
                />
              </div>
              <div class="col-3 px-1">
                <input
                  type="text"
                  name="card-number-2"
                  v-model="cardNumber_2"
                  class="form-control"
                  placeholder="****"
                  pattern="\d*" 
                  maxlength="4"
                />
              </div>
              <div class="col-3 px-1">
                <input
                  type="text"
                  name="card-number-3"
                  v-model="cardNumber_3"
                  class="form-control"
                  placeholder="****"
                  pattern="\d*" 
                  maxlength="4"
                />
              </div>
              <div class="col-3 ps-1 pe-0">
                <input
                  type="text"
                  name="card-number-4"
                  v-model="cardNumber_4"
                  class="form-control"
                  placeholder="****"
                  pattern="\d*" 
                  maxlength="4"
                />
              </div>
            </div>
          </div>
        </div>
        <!-- 生日 -->
        <div class="row py-3">
          <div class="col-lg-4 text-lg-end pt-1">
            <p>生日</p>
          </div>
          <div class="col-lg-6">
            <input
              type="text"
              name="birth"
              v-model="birth"
              class="form-control"
              :class="{ 'error-input': birthError }"
              placeholder="例如：19991010"
              pattern="\d*" 
              maxlength="8"
            />
            <p class="error-message">{{ birthErrMsg }}</p>
          </div>
        </div>
        <!-- 識別碼 -->
        <div class="row py-3">
          <div class="col-lg-4 text-lg-end pt-1">
            <p>識別碼</p>
          </div>
          <div class="col-lg-2 col-12">
            <input
              type="text"
              v-model="inputCaptcha"
              class="form-control d-none d-lg-block"
              :class="{ 'error-input': inputCaptchaError }"
              placeholder="請輸入右方圖形數字"
            />
            <input
              type="text"
              v-model="inputCaptcha"
              class="form-control d-lg-none"
              :class="{ 'error-input': inputCaptchaError }"
              placeholder="請輸入下方圖形數字"
            />
            <p class="error-message">{{ inputCaptchaErrMsg }}</p>
          </div>
          <div class="col-lg-2 col-6">
            <img class="img-fluid" src="../assets/images/img-validate.jpg" />
          </div>
          <div class="col-lg-2 col-6 reCaptcha">
            <button
              type="button"
              class="btn btn-outline-primary rounded-pill px-5 d-none d-lg-block"
            >
              重新發送
            </button>
            <button
              type="button"
              class="btn btn-outline-primary rounded-pill px-3 d-lg-none"
            >
              重新整理
            </button>
          </div>
        </div>
      </div>
      <!-- 行銷條款 -->
      <div class="container-fluid">
        <div class="container px-5 pt-3" id="service-rule">
          <div class="row">
            <div class="col-8">
              <p>共同行銷條款</p>
            </div>
            <div class="col-4 text-end">
              <img class="img-fluid" src="../assets/images/accordion--pc.png" />
            </div>
          </div>
        </div>
      </div>
      <div class="container-fluid">
        <div class="container pt-3">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              name="checkRule"
              v-model="checkRule"
              id="serviceCheck"
            />
            <label class="form-check-label font-bold" for="serviceCheck">
              本人已閱讀並同意上述共同行銷條款。
            </label>
          </div>
        </div>
      </div>
      <!-- 送出按鈕 -->
      <div class="container text-center p-5">
        <button
          class="btn btn-primary px-5 rounded-pill"
          @click="showFormData()"
        >
          確認送出
        </button>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
@import "../assets/scss/main";
</style>

<script>
export default {
  data() {
    return {
      inputId: "",
      inputIdErrMsg: "",
      inputIdError: false,
      inputCaptcha: "",
      inputCaptchaErrMsg: "",
      inputCaptchaError: false,
      cardNumber_1: "",
      cardNumber_2: "",
      cardNumber_3: "",
      cardNumber_4: "",
      cardNumner: "",
      birth: "",
      birthError: false,
      birthErrMsg: "",
      checkRule: false,
    };
  },
  methods: {
    checkCardNumber() {
      this.cardNumber =
        this.cardNumber_1 +
        this.cardNumber_2 +
        this.cardNumber_3 +
        this.cardNumber_4;
      return this.cardNumber;
    },
    checkFormData() {
      return (
        !this.inputIdError &&
        !this.inputCaptchaError &&
        !this.birthError &&
        this.checkRule
      );
    },
    showFormData() {
      if (this.checkCardNumber().length < 16) {
        alert("輸入卡號不可為空");
        return;
      } else {
        if (this.checkFormData()) {
          const formData = {
            Id: this.inputId,
            cardNumner: this.cardNumber,
            birth: this.birth,
          };
          alert("表格送出資料：" + JSON.stringify(formData));
        } else {
          alert("資料格式填寫錯誤，請再檢查！");
        }
      }
    },
  },
  watch: {
    inputId() {
      const isID = /\d{5}$/;
      if (!isID.test(this.inputId)) {
        this.inputIdError = true;
        this.inputIdErrMsg = "身分證格式輸入錯誤";
      } else {
        this.inputIdError = false;
        this.inputIdErrMsg = "";
      }
    },
    inputCaptcha() {
      const isCaptcha = "CAPTCHA";
      if (this.inputCaptcha !== isCaptcha) {
        this.inputCaptchaError = true;
        this.inputCaptchaErrMsg = "識別碼輸入錯誤";
      } else {
        this.inputCaptchaError = false;
        this.inputCaptchaErrMsg = "";
      }
    },
    birth() {
      const isBirth = /^\d{8}$/;
      if (!isBirth.test(parseInt(this.birth))) {
        this.birthError = true;
        this.birthErrMsg = "生日格式輸入錯誤";
      } else {
        this.birthError = false;
        this.birthErrMsg = "";
      }
    },
  },
};
</script>
