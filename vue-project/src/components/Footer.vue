<script>
import { RouterLink } from "vue-router";
export default {
  data() {
    return {
      breadcrumbItems: [
        { text: "Home", href: "/" },
        { text: "Search", href: "/search" },
        { text: "About", href: "/about" },
        { text: "", href: "" },
      ],
    };
  },
};
</script>

<template>
  <main>
    <hr class="separator" />
    <div class="contentFooter">
      <div class="items">
        <b-breadcrumb :items="breadcrumbItems"></b-breadcrumb>
      </div>
      <div id="logoFooter">
        <b-img
          center
          block
          src="https://cdn-icons.flaticon.com/png/512/2953/premium/2953892.png?token=exp=1655601040~hmac=604ed3f1e1eeaefa2c8884771c6ee1d3"
          fluid
        ></b-img>
      </div>
      <div class="contact">
        <h5 class="contactTitle">Contacto</h5>
        <div>
          <b-avatar
            class="contactAvatars"
            variant="info"
            src="https://cdn-icons.flaticon.com/png/512/1151/premium/1151429.png?token=exp=1655594313~hmac=fbaec4d3f257485d77262ca3cb565265"
            size="2rem"
          ></b-avatar>
          <span>+56930060020</span>
        </div>
        
        <div>
          <b-avatar
            class="contactAvatars"
            variant="info"
            src="https://cdn-icons.flaticon.com/png/512/3059/premium/3059410.png?token=exp=1655594136~hmac=e2bdbfa0c63ae67c26106fcb5ed57b78"
            size="2rem"
          ></b-avatar>
          <span>valid@email.com</span>
        </div>
        <div>
          <b-avatar
            class="contactAvatars"
            variant="info"
            src="https://cdn-icons-png.flaticon.com/512/927/927667.png"
            size="2rem"
          ></b-avatar>
          <span>Calle Falsa 123</span>
        </div>
      </div>
      
    </div>
  </main>
</template>

<style>
.items {
  display: flex;
  justify-content: center;
}

.separator {
  margin-top: 8%;
}

#logoFooter {
  width: 10rem;
}

.contact {
  display: flex;
  flex-flow: column;
  gap: 15px;
}

.contentFooter {
  display: grid;
  justify-content: space-evenly;
  grid-template-columns: auto auto auto;
  align-items: center;
}

.contactTitle {
  color: rgba(0, 0, 255, 0.548);
}

.contactAvatars {
  margin-right: 20px;
}
</style>
