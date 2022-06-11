<template>
  <v-container class="font">
    <v-footer app padless>
      <v-card class="flex" flat tile>
        <v-card-title>
          <v-row cols="12">
            <v-col>
              <span class="pointer" @click.stop="show('legal')"> legal </span>
              <span class="pointer" @click.stop="show('privacy')">
                privacy
              </span>
              <span class="pointer" @click.stop="show('disclaimer')">
                disclaimer
              </span>
            </v-col>

            <v-col>
              <v-btn
                v-for="icon in icons"
                :key="icon.img"
                class="mx-4"
                :href="icon.href"
                icon
              >
                <v-icon size="24px" style="color: #d8d6cf">
                  {{ icon.img }}
                </v-icon>
              </v-btn>
            </v-col>
            <v-col class="font">
              <span> &copy; {{ new Date().getFullYear() }} by Paul</span>
            </v-col>
          </v-row>
        </v-card-title>
      </v-card>

      <Modal
        v-model="showModal"
        v-bind:title="modalTitle"
        v-bind:body="modalBody"
      />
    </v-footer>
  </v-container>
</template>
<script>
export default {
  name: "FooterComponent",
  components: {
    Modal: () => import("./Modal"),
  },
  data() {
    return {
      showModal: false,
      modalTitle: "",
      modalBody: "",
      mail_lnk: "mailto:contact@paulwerner.net",
      github_lnk: "https://github.com/paulwerner",
      xing_lnk: "https://www.xing.com/profile/Paul_Werner23",
      linkedin_lnk: "https://de.linkedin.com/in/paul-werner",
      legalTitle: "LEGAL NOTICE",
      legalBody: `<h3>Information pursuant to sec. 5 German Telemedia Act</h3>
                <p>
                    Paul Werner<br/>
                    Holstenstr. 111<br/>
                    22767 Hamburg</p>
                <p>
                    email: contact(at)paulwerner.net
                </p>
                <p>
                    The content and works on this website (“Website”) are subject to German
                    copyright law. The reproduction, processing, distribution and any kind
                    of exploitation outside the limits of copyright require the written consent
                    of Paul Werner or the respective author.
                </p>`,
      privacyTitle: "PRIVACY",
      privacyBody: `<p>
                    Controller of this website (“Website”) pursuant to the General Data Protection
                    Regulation (“GDPR”) is Paul Werner.
                </p>
                <p>
                    When you visit this Website your IP address of the requesting computer, date and
                    time of access, name and URL of the retrieved file, website from which the access
                    is made (referrer URL), and the browser used and, if applicable, the operating
                    system of your computer and the name of your access provider are collected and
                    processed. These data are processed to ensure a smooth connection setup of the
                    website, a comfortable use of the Website, evaluation of system security and stability
                    and for other administrative purposes. The legal basis for processing is
                    Art. 6 (1) f) GDPR. The data is deleted as soon as it is not longer needed for the
                    above mentioned purposes.
                </p>
                <p>
                    When you contact Paul Werner via the above mentioned email, your email address and the
                    personal data you might mention in it are processed for the purpose of answering you
                    and/or responding to your corresponding request
                </p>
                <p>
                    As a data subject you have the rights pursuant to chapter 3 <br> (Art. 12 – 23) GDPR.
                </p>`,
      disclaimerTitle: "DISCLAIMER",
      disclaimerBody: `<p>
                    The information on this Website is for general information purposes only.
                    Paul Werner assumes no responsibility for errors or omissions in the contents
                    of this Website.
                </p>

                <p> Paul Werner also reserves the right to make additions, deletions, modifications to the
                    contents of the Website or even shut down the Website at any time without prior notice.
                </p>

                <p>
                    Paul Werner does not guarantee that the Website is free of viruses or other harmful components.
                </p>

                <p>
                    The Website contains links to external websites. Paul Werner is not liable or responsible for
                    these external websites and contents. Should you have questions about these external websites,
                    please direct them to the respecting providers.
                </p>

                <span>
                    Last updated: April 10, 2021
                </span>

            </div>`,
      icons: [
        { img: "mdi-github", href: "https://github.com/paulwerner" },
        { img: "mdi-mail", href: "mailto:contact@paulwerner.net" },
        { img: "mdi-linkedin", href: "https://de.linkedin.com/in/paul-werner" },
        { img: "mdi-xing", href: "https://www.xing.com/profile/Paul_Werner23" },
      ],
    };
  },
  methods: {
    show(type) {
      if (type === "legal") {
        this.modalTitle = this.legalTitle;
        this.modalBody = this.legalBody;
        this.showModal = true;
      } else if (type === "privacy") {
        this.modalTitle = this.privacyTitle;
        this.modalBody = this.privacyBody;
        this.showModal = true;
      } else if (type === "disclaimer") {
        this.modalTitle = this.disclaimerTitle;
        this.modalBody = this.disclaimerBody;
        this.showModal = true;
      }
    },
  },
};
</script>
<style scoped>
.theme--light.v-sheet {
  background-color: #0f0b07;
  border-style: solid none none none;
  border-color: #be884b;
  color: #d8d6cf;
}

span {
  font-size: 12px;
  padding-right: 10px;
}

.pointer {
  cursor: pointer;
}

.img-width {
  max-width: 50%;
  max-height: 50%;
}
</style>
