<!-- Please remove this file from your project -->
<template>
  <div class="dashboard">
          <DashboardNav class="mx-comp desktop-only" />
      <div class="mx-comp">
        <div class="header flex">
            <div class="header-heading flow">
                <h1 class="fs-600 fw-bold heading line-clamp">Welcome back, Olivia</h1>
                <p class="sub-heading line-clamp">Track, manage and forecast your customers and orders.</p>
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
          <div class="filter flex">
            <span class="flex">
              <Button tertiary><span>All time</span><img src="~/static/icons/close.svg" alt=""/></Button>
              <Button tertiary><span>US, AU, +4</span><img src="~/static/icons/close.svg" alt=""/></Button>
              
              <Button outline class="desktop-and-tablet"><img src="~/static/icons/filter.svg" alt="" ><span>More filters</span></Button>
            </span>
            <Button outline class="mobile-only edit-filters"><img src="~/static/icons/filter.svg" alt="" ><span>Edit filters</span></Button>
          </div>
          <Search placeholder="Search" class="search" />
        </div>

        <!-- <v-data-table
              :headers="headers"
              :items="customers"
              :search="search"
              show-select
              single-select
              item-key="name"
              hide-default-footer
              class="customer-table"
            >
        </v-data-table> -->
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
          { text: 'Licence use', value: 'licenseUse', align: 'start' },
          { text: 'Status', value: 'status', align: 'start' },
          { text: 'Users', value: 'users', align: 'start' },
          { text: 'About', value: 'about', align: 'start' },
          { text: '', value: 'actions', sortable: false, align: 'end', align: 'start' }
        ],
        customers: [
          {
            name: 'Catalog',
            website: 'catalogapp.io',
            logo: 'catalog.svg',
            licenseUse: 80,
            status: 'Customer',
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
            description: 'Design software',
            tagline: 'Super lightweight design app',
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
            description: 'Data prediction',
            tagline: 'AI and machine learning data',
            users: [
              {name: '',img: 'user10.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user12.svg',},{name: '',img: 'user9.svg',},{name: '',img: 'user13.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
          {
            name: 'Hourglass',
            website: 'hourglass.app',
            logo: 'hourglass.svg',
            licenseUse: 90,
            status: 'customer',
            description: 'Productivity app',
            tagline: 'time management and productivity',
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
            description: 'Web app integrations',
            tagline: 'Connect web apps seamlessly',
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
            description: 'Sales CRM',
            tagline: 'Web-based sales doc management',
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
            description: 'Automation and workflow',
            tagline: 'Time tracking, invoicing and expenses',
            users: [
              {name: '',img: 'user7.svg',},{name: '',img: 'user12.svg',},{name: '',img: 'user8.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user11.svg',},{name: '',img: 'user4.svg',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',},{name: '',img: '',}
            ]
          },
           {
            name: 'Catalog2',
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
            name: 'Circooles2',
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
            name: 'Command+R2',
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
            name: 'Hourglass2',
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
            name: 'Layers2',
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
            name: 'Quotient2',
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
            name: 'Sisyphus2',
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
  .dashboard {
    margin-bottom: 96px;
  }
  .header {
    margin-block: 3rem;
    justify-content: space-between;
    align-items: center;
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
  @media (max-width: 1120px) {
    .analytics {
    grid-template-columns: 1fr;
    }
  }
  @media (max-width: 780px) {
    .header {
      flex-direction: column
    }
    .header-btns {
    justify-content: flex-start;
    }
    .filter-search, .filter {
      flex-direction: column-reverse;
    }
    .search {
      max-width: 100% !important;
      width: 100%;
    }
    .edit-filters {
      --gap: 1rem;
      width: 100%;
      max-width: 100%;
    }
    .edit-filters > * {
      margin: 0 0.5rem;
    }
  }

  .filter-search {
    justify-content: space-between;
    margin-block: 1.5rem;
  }
  .filters {
    display: inline-block;
  }
  .actions {
    justify-content: flex-end;
    --gap: 1.5rem;
    color: hsla(220, 13%, 46%, 1);
  }

</style>
