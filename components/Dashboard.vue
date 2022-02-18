<!-- Please remove this file from your project -->
<template>
  <div>
      
        <hr />
          <DashboardNav class="mx-7rem" />
          <hr />
      <div class="mx-7rem">
        <div class="header flex">
            <div class="header-heading flow">
                <h1 class="fs-600 fw-bold heading">Welcome back, Olivia</h1>
                <p class="sub-heading">Track, manage and forecast your customers and orders.</p>
            </div>
            <div class="header-btns flex">
                <Button outline ><img src="~/static/icons/import.svg" alt="" /> Import </Button>
                <Button primary ><img src="~/static/icons/add.svg" alt="" /> Add</Button>
            </div>
        </div>

        <div class="analytics grid">
            <AnalyticsCard v-for="(item, index) in analysisData" :key="index" :data="item" />
        </div>

        <div class="filter-search flex">
          <div></div>
          <Search placeholder="Search" class="search" />
        </div>


        <CustomerTable 
          :headers="headers"
          :customers="customers"
          :search="search"
          />
      </div>
  </div>
</template>

<script>
export default {
  name: 'Dashboard',
  layout: 'empty',
    data () {
      return {
        search: '',
        analysisData: [
          {
            description: 'Total customers',
            value: 2420,
            growthRate: 40
          },
          {
            description: 'Members',
            value: 1210,
            growthRate: -10
          },
          {
            description: 'Active now',
            value: 316,
            growthRate: 20
          }
        ],
        headers: [
          {
            text: 'Company',
            align: 'start',
            value: 'name', 
          },
          { text: 'Licence use', value: 'licenseUse' },
          { text: 'Status', value: 'status' },
          { text: 'Users', value: 'users' },
          { text: 'About', value: 'about' },
          { text: '', value: 'actions', sortable: false, align: 'end' }
        ],
        customers: [
          {
            name: 'Catalog',
            website: 'getcircooles.com',
            logo: 'catalog.svg',
            licenseUse: 90,
            status: 'churned',
            description: 'Content curating app',
            tagline: 'Brings all your news into one place',
            users: [
              {name: '',img: 'user1.svg',},{name: '',img: 'user2.svg',},{name: '',img: 'user3.svg',},{name: '',img: 'user4.svg',},{name: '',img: 'user5.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
          {
            name: 'Circooles',
            website: 'getcircooles.com',
            logo: 'circooles.svg',
            licenseUse: 70,
            status: 'churned',
            description: 'Content curating app',
            tagline: 'Brings all your news into one place',
            users: [
              {name: '',img: 'user6.svg',},{name: '',img: 'user7.svg',},{name: '',img: 'user8.svg',},{name: '',img: 'user9.svg',},{name: '',img: 'user10.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
          {
            name: 'Command+R',
            website: 'cmdr.ai',
            logo: 'cmdr.svg',
            licenseUse: 40,
            status: 'customer',
            description: 'Design software',
            tagline: 'Super lightweight design app',
            users: [
              {name: '',img: 'user10.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user12.svg',},{name: '',img: 'user9.svg',},{name: '',img: 'user13.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
          {
            name: 'Hourglass',
            website: 'hourglass.app',
            logo: 'hourglass.svg',
            licenseUse: 80,
            status: 'customer',
            description: 'Data prediction',
            tagline: 'AI and machine learning data',
            users: [
              {name: '',img: 'user5.svg',},{name: '',img: 'user2.svg',},{name: '',img: 'user6.svg',},{name: '',img: 'user7.svg',},{name: '',img: 'user11.svg',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
          {
            name: 'Layers',
            website: 'getlayers.io',
            logo: 'layers.svg',
            licenseUse: 30,
            status: 'churned',
            description: 'Productivity app',
            tagline: 'Time management and productivity',
            users: [
              {name: '',img: 'user3.svg',},{name: '',img: 'user6.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user9.svg',},{name: '',img: 'user10.svg',}
            ]
          },
          {
            name: 'Quotient',
            website: 'quotient.cco',
            logo: 'quotient.svg',
            licenseUse: 20,
            status: 'customer',
            description: 'Web app intergrations',
            tagline: 'Connect web apps seamlessly',
            users: [
              {name: '',img: 'user5.svg',},{name: '',img: 'user3.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user6.svg',},{name: '',img: 'user12.svg',},{name: '',img: '',}
            ]
          },
          {
            name: 'Sisyphus',
            website: 'sisyphus.com',
            logo: 'sisyphus.svg',
            licenseUse: 50,
            status: 'customer',
            description: 'Sales CRM',
            tagline: 'Web-based sales doc management',
            users: [
              {name: '',img: 'user7.svg',},{name: '',img: 'user12.svg',},{name: '',img: 'user8.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user4.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
        ],
      }
    },
  
}
</script>
<style scoped>

  .header {
    margin-block: 3rem;
  }
  .header .sub-heading {
    margin-block: 4px;
    color: hsla(220, 13%, 46%, 1);
  }
  .header-btns {
    justify-content: flex-end;
    height: max-content
  }
  .analytics {
    grid-template-columns: repeat(3, 1fr);
    --gap: 1.5rem;
    margin: 2rem 0;
  }

  .filter-search {
    justify-content: space-between;
    margin-block: 1.5rem;
  }
  .actions {
    justify-content: flex-end;
    --gap: 1.5rem;
    color: hsla(220, 13%, 46%, 1);
  }

</style>
