<template>
  <div class="container">
    <b-card no-body>
      <b-tabs card>
        <b-tab title="Account Info" active>
          <b-form @submit.stop.prevent="onSubmit">
            <!-- person Name -->
            <b-form-group
              id="personName-input-group-1"
              label="Contact Person"
              label-for="personName-input-1"
            >
              <b-form-input
                id="personName-input-1"
                name="personName-input-1"
                v-model="$v.form.name.$model"
                :state="validateState('name')"
                placeholder="Contact Person Name"
                aria-describedby="personName-input-1-live-feedback"
              ></b-form-input>

              <b-form-invalid-feedback id="personName-input-1-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <!-- business Name -->
            <b-form-group
              id="businessName-input-group-2"
              label="Business Name"
              label-for="businessName-input-2"
            >
              <b-form-input
                id="businessName-input-2"
                name="businessName-input-2"
                v-model="$v.form.boo.$model"
                placeholder="Business Name"
              ></b-form-input>
            </b-form-group>

            <!--contact Number  -->
            <b-form-group
              id="contactNumber-input-group-3"
              label="Contact Number"
              label-for="contactNumber-input-3"
            >
              <b-input-group id="input-contactNum" class="mb-2">
                <b-form-input
                  id="conNumber_country-input-3"
                  name="conNumber_country-input-3"
                  v-model="$v.form.contactNum_country.$model"
                  class="mr-3"
                  label="rex"
                  placeholder="Country Code"
                ></b-form-input>
                <b-form-input
                  id="conNumber_telNumber-input-3"
                  name="conNumber_telNumber-input-3"
                  v-model="$v.form.contactNum_telNumber.$model"
                  label="Last name"
                  placeholder="Phone Number"
                ></b-form-input>
              </b-input-group>
            </b-form-group>

            <!-- address 1 -->

            <b-form-group
              id="address_1-input-group-4"
              label="Street Address*"
              label-for="address_1-input-4"
            >
              <b-form-input
                id="address_1-input-4"
                name="address_1-input-4"
                placeholder="Street Address"
                v-model="$v.form.address_1.$model"
                :state="validateState('address_1')"
                aria-describedby="address_1-input-5-live-feedback"
              ></b-form-input>

              <b-form-invalid-feedback id="address_1-input-5-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <!-- address 2 -->

            <b-form-group
              id="address_2-input-group-5"
              label="Street Address 2"
              label-for="address_2-input-5"
            >
              <b-form-input
                id="address_2-input-5"
                name="address_2-input-5"
                placeholder="Street Address 2"
                v-model="$v.form.address_1.$model"
                aria-describedby="address_2-input-5-live-feedback"
              ></b-form-input>
            </b-form-group>

            <!-- city -->
            <b-form-group
              id="city-input-group-6"
              label="City*"
              label-for="city-input-6"
            >
              <b-form-input
                id="city-input-6"
                name="city-input-6"
                v-model="$v.form.city.$model"
                :state="validateState('city')"
                placeholder="City"
                aria-describedby="city-input-6-live-feedback"
              ></b-form-input>

              <b-form-invalid-feedback id="city-input-6-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>
            <!-- district -->

            <b-form-group
              id="district-input-group-7"
              label="District"
              label-for="district-input-7"
            >
              <b-form-select
                id="district-input-7"
                name="district-input-7"
                v-model="$v.form.district.$model"
                :options="district"
                :state="validateState('district')"
                aria-describedby="district-input-7-live-feedback"
              ></b-form-select>

              <b-form-invalid-feedback id="district-input-7-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <b-form-group
              id="email-input-group-8"
              label="Email*"
              label-for="email-input-8"
            >
              <b-form-input
                id="email-input-8"
                name="email-input-8"
                v-model="$v.form.email.$model"
                :state="validateState('email')"
                placeholder="Email Address"
                aria-describedby="email-input-8-live-feedback"
              ></b-form-input>

              <b-form-invalid-feedback id="email-input-8-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <!-- start date -->

            <b-form-group
              id="startDate-input-group-9"
              label="Start Date*"
              label-for="startDate-input-9"
            >
              <b-form-datepicker
                id="startDate-input-9"
                name="startDate-input-9"
                v-model="$v.form.startDate.$model"
                :state="validateState('startDate')"
                aria-describedby="startDate-input-9-live-feedback"
              ></b-form-datepicker>

              <b-form-invalid-feedback id="startDate-input-9-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <b-button type="submit" variant="primary">Submit</b-button>
            <b-button class="ml-2" @click="resetForm()">Reset</b-button>
          </b-form>
        </b-tab>
        <!-- tab 2 -->
        <b-tab title="Billing Address">
          <b-form @submit.stop.prevent="onSubmit">
            <b-form-group
              id="example-input-group-1"
              label="Name"
              label-for="example-input-1"
            >
              <b-form-input
                id="example-input-1"
                name="example-input-1"
                v-model="$v.form.name.$model"
                :state="validateState('name')"
                placeholder="Contact Person Name"
                aria-describedby="input-1-live-feedback"
              ></b-form-input>

              <b-form-invalid-feedback id="input-1-live-feedback"
                >This is a required field and must be at least 3
                characters.</b-form-invalid-feedback
              >
            </b-form-group>

            <b-form-group
              id="example-input-group-2"
              label="rex"
              label-for="example-input-2"
            >
              <b-form-select
                id="example-input-2"
                name="example-input-2"
                v-model="$v.form.rex.$model"
                :options="rex"
                :state="validateState('rex')"
                aria-describedby="input-2-live-feedback"
              ></b-form-select>

              <b-form-invalid-feedback id="input-2-live-feedback"
                >This is a required field.</b-form-invalid-feedback
              >
            </b-form-group>

            <b-button type="submit" variant="primary">Submit</b-button>
            <b-button class="ml-2" @click="resetForm()">Reset</b-button>
          </b-form>
        </b-tab>
        <!-- tab3 -->
        <b-tab title="Shipping Address"> </b-tab>
      </b-tabs>
    </b-card>
  </div>
</template>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  /* display: flex; */
  justify-content: top;
  align-items: top;
  text-align: left;
}
</style>

<script>
import { validationMixin } from "vuelidate";
import { required, minLength } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],
  data() {
    return {
      district: [
        { value: null, text: "District..." },
        { value: "apple", text: "Apple" },
        { value: "orange", text: "Orange" },
      ],
      rex: [
        { value: null, text: "hello..." },
        { value: "m", text: "M" },
        { value: "a", text: "A" },
      ],
      form: {
        name: null,
        food: null,
        boo: null,
        contactNum_country: null,
        contactNum_telNumber: null,
        address_1: null,
        address_2: null,
        district: null,
        email: null,
        startDate: null,
        rex: null,
      },
    };
  },
  validations: {
    form: {
      name: {
        required,
        // minLength: minLength(3),
      },
      food: { required },
      boo: {},
      contactNum_country: { minLength: minLength(3) },
      contactNum_telNumber: { minLength: minLength(7) },
      address_1: { required },
      address_2: {},
      city: { required },
      district: { required },
      email: { required },
      startDate: { required },
      rex: {
        required,
      },
    },
  },
  methods: {
    validateState(name) {
      const { $dirty, $error } = this.$v.form[name];
      return $dirty ? !$error : null;
    },
    // validateState(xz) {
    //   const { $dirty, $error } = this.$v.form[xz];
    //   return $dirty ? !$error : null;
    // },
    resetForm() {
      this.form = {
        name: null,
        food: null,
        boo: null,
        contactNum_country: null,
        contactNum_telNumber: null,
        address_1: null,
        address_1: null,
        city: null,
        district: null,
        email: null,
        required: null,
        rex: null,
      };

      this.$nextTick(() => {
        this.$v.$reset();
      });
    },
    onSubmit() {
      this.$v.form.$touch();
      if (this.$v.form.$anyError) {
        return;
      }

      alert("Form submitted!");
    },
  },
};
</script>