<template>
  <div class="about">
    <page-header>
      Contact Us
      <template v-slot:link>
        Contact
      </template>
    </page-header>
    <div class="container">
      <div class="info">
        <div class="info__item">
          <facebook-icon class="info__icon" />
          <h4>Phone</h4>
          <p>+01-0000-0000</p>
        </div>
        <div class="info__item">
          <facebook-icon class="info__icon" />
          <h4>Address</h4>
          <p>234 Fake Street, NY</p>
        </div>
        <div class="info__item">
          <facebook-icon class="info__icon" />
          <h4>
            Open Time
          </h4>
          <p>10:00 am to 11:00 pm</p>
        </div>
        <div class="info__item">
          <facebook-icon class="info__icon" />
          <h4>Email</h4>
          <p>test@dummy.com</p>
        </div>
      </div>
    </div>
    <div class="form__bg">
      <div class="container">
        <div class="form__heading">
          <h2>Leave Message</h2>
          <p>Our staff will call back later to answer your questions.</p>
        </div>
        <form
          class="form"
          @submit.prevent
        >
          <input
            type="text"
            placeholder="Name"
          >
          <input
            type="email"
            placeholder="Email"
          >
          <textarea
            id=""
            name=""
            cols="30"
            rows="10"
            placeholder="Start the discussion..."
          />
          <base-button class="form__btn" primary>
            Send
          </base-button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import PageHeader from '~/components/Shared/PageHeader/PageHeader'
import FacebookIcon from '~/assets/images/facebook.svg?inline'

export default {
  components: {
    PageHeader,
    FacebookIcon
  }
}
</script>

<style lang="scss" scoped>
.info {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 4rem;
  padding-bottom: 8rem;

  &__item {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  &__icon {
    width: 3rem;
    height: 3rem;
    margin-bottom: 2rem;
    fill: $color-primary;
  }
}

.form {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-gap: 3rem;

  &__bg {
    padding: 8rem 0;
    background-color: #f6f9f9;
  }

  &__heading {
    text-align: center;
    margin-bottom: 5rem;
  }

  &__btn {
    grid-column: 1/-1;
    justify-self: center;
  }

  textarea,
  input {
    padding: 1rem 2rem;
  }

  textarea {
    grid-column: 1/-1;
  }
}
</style>
