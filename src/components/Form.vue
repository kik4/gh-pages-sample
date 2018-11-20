<template>
    <form-wizard @on-complete="onComplete" shape="circle" color="#3498db">
        <tab-content title="Personal details" icon="ti-user">
        My first tab content
        </tab-content>
        <tab-content title="Additional Info" icon="ti-settings">
        My second tab content
        </tab-content>
        <tab-content title="Last step" icon="ti-check">
        Yuhuuu! This seems pretty damn simple
        </tab-content>
    </form-wizard>
</template>

<script>
import Vue from "vue";
import VueFormWizard from "vue-form-wizard/dist/vue-form-wizard.js";
import "vue-form-wizard/dist/vue-form-wizard.min.css";
Vue.use(VueFormWizard);
export default {
  data: function() {
    return {
      formInline: {
        user: "",
        region: ""
      },
      rules: {
        user: [
          {
            required: true,
            message: "Please input Activity name",
            trigger: "blur"
          },
          {
            min: 3,
            max: 5,
            message: "Length should be 3 to 5",
            trigger: "blur"
          }
        ],
        region: [
          {
            required: true,
            message: "Please select Activity zone",
            trigger: "change"
          }
        ]
      }
    };
  },
  methods: {
    onComplete: function() {
      alert("Yay. Done!");
    },
    validateFirstStep: function() {
      return new Promise(function(resolve, reject) {
        this.$refs.ruleForm.validate(function(valid) {
          resolve(valid);
        });
      });
    }
  }
};
</script>
