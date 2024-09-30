<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Calculator App</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">
      <!-- Search Bar -->
      <ion-searchbar v-model="searchQuery" placeholder="Search Calculators"></ion-searchbar>

      <!-- Calculator Categories -->
      <div class="categories">
        <ion-grid>
          <ion-row>
            <!-- Basic Calculators -->
            <ion-col size="6" size-md="4">
              <ion-card @click="navigateToCategory('basic-calculators')">
                <ion-card-header>
                  <ion-card-title>Basic Calculators</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                  Perform basic arithmetic operations like addition, subtraction, multiplication, etc.
                </ion-card-content>
              </ion-card>
            </ion-col>

            <!-- Finance Calculators -->
            <ion-col size="6" size-md="4">
              <ion-card @click="navigateToCategory('finance-calculators')">
                <ion-card-header>
                  <ion-card-title>Finance Calculators</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                  Calculate loans, interest rates, EMIs, and more.
                </ion-card-content>
              </ion-card>
            </ion-col>

            <!-- Business & Professional Calculators -->
            <ion-col size="6" size-md="4">
              <ion-card @click="navigateToCategory('business-calculators')">
                <ion-card-header>
                  <ion-card-title>Business & Professional</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                  Track profits, sales, and other business metrics.
                </ion-card-content>
              </ion-card>
            </ion-col>

            <!-- Health & Fitness Calculators -->
            <ion-col size="6" size-md="4">
              <ion-card @click="navigateToCategory('health-calculators')">
                <ion-card-header>
                  <ion-card-title>Health & Fitness</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                  Calculate BMI, calorie needs, and other health metrics.
                </ion-card-content>
              </ion-card>
            </ion-col>

            <!-- Other Calculators -->
            <ion-col size="6" size-md="4">
              <ion-card @click="navigateToCategory('other-calculators')">
                <ion-card-header>
                  <ion-card-title>Other Calculators</ion-card-title>
                </ion-card-header>
                <ion-card-content>
                  Miscellaneous calculators for various needs.
                </ion-card-content>
              </ion-card>
            </ion-col>
          </ion-row>
        </ion-grid>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { useRouter } from 'vue-router';

export default defineComponent({
  name: 'HomePage',
  setup() {
    const searchQuery = ref<string>('');
    const router = useRouter();

    const navigateToCategory = (category: string) => {
      router.push({ name: category });
    };

    return {
      searchQuery,
      navigateToCategory,
    };
  },
});
</script>

<style scoped>
.categories {
  margin-top: 16px;
}

ion-card {
  cursor: pointer;
}

ion-card:hover {
  transform: scale(1.05);
  transition: 0.3s ease;
}
</style>
