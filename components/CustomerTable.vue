<template>
    <v-data-table
              :headers="headers"
              :items="customers"
              :search="search"
              show-select
              class="customer-table"
            >
            <template v-slot:[`item.name`]="{ item }">
                <div class="flex">
                  <div class="logo">
                    <img :src="require('../static/customers/' + item.logo)" :alt="item.name" />
                  </div>
                  <div>
                    <p class="name">{{item.name}}</p>
                    <p class="website">{{item.website}}</p>
                  </div>
                </div>
              </template>

              <template v-slot:[`item.licenseUse`]="{ item }">
                <div class="">
                  <div class="license">
                    <div class="indicator" v-bind:style="{width:item.licenseUse + '%'}"></div>
                  </div>
                </div>
              </template>

              <template v-slot:[`item.status`]="{ item }">
                <p class="status" :class=" item.status ">
                  {{item.status}}
                </p>
              </template>

              <template v-slot:[`item.about`]="{ item }">
                <div class="">
                  <div>
                    <p class="description">{{item.description}}</p>
                    <p class="tagline">{{item.tagline}}</p>
                  </div>
                </div>
              </template>

              <template v-slot:[`item.users`]="{ item }">
                <UsersList :users="item.users" />
              </template>

              <!-- <template v-slot:item.name="{}"> -->
              <template v-slot:[`item.actions`]="{ item }">
                <div class="flex actions">
                  <button @click="deleteItem(item)"><img src="~/static/icons/delete.svg" alt="" /></button>
                  <button @click="deleteItem(item)"><img src="~/static/icons/edit.svg" alt="" /></button>
                </div>
              </template>
            </v-data-table>
</template>
<script>
export default {
    name: 'CustomerTable',
    props: {
        headers: {
            type: Array,
            default: {}
        },
        customers: {
            type: Array,
            default: {}
        },
        search: {
            type: String,
            default: ''
        }
    },
    data() {
        return {
            
        }
    }
}
</script>
<style scoped>
.customer-table p {
  margin: 0;
}
.logo {
  width: 40px;
  height: 40px;
}
.license {
  background: hsla(264, 100%, 98%, 1);
  height: 8px;
  border-radius: 4px;
}
.indicator {
  background: hsla(259, 63%, 59%, 1);
  height: 100%;
  border-radius: 4px;
}
.status {
  text-transform: capitalize;
  color: hsla(155, 96%, 24%, 1);
  font-weight: var(--fw-bold);
  padding: 2px 8px;
  border-radius: 16px;
  width: max-content;
  font-size: 12px;
}
.status.customer {
  background: #ECFDF3;  
}
.status.churned {
  background: hsla(220, 22%, 96%, 1)
}
  .description, .name {
    color: hsla(221, 43%, 11%, 1);
    font-weight: var(--fw-bold)
  }
  .tagline, .website {
    color: hsla(220, 13%, 46%, 1);
  }
    ::v-deep table{
        border: 1px solid hsla(220, 17%, 93%, 1) ;
        border-radius: 8px;
        box-shadow: 0px 4px 8px -2px rgba(16, 24, 40, 0.1), 0px 2px 4px -2px rgba(16, 24, 40, 0.06);
        color: #667085;
        font-size: 12px;
        font-weight: var(--fs-bold);
    }
    ::v-deep .v-checkbox {
        /* border-radius: 0 0 8px 8px; */
        color: red;

    }
    </style>
    <style>
    ::v-deep .v-input--selection__input .mdi-checkbox-marked::before {
        border-radius: 6px;
        background: #7F56D9 !important;
    }
.v-input--selection__input .v-icon.mdi.theme--light.mdi-checkbox-blank-outline::before,
.mdi-checkbox-blank-outline::before,
 .mdi-checkbox-marked::before {
    font-size: 20px;
    /* border: 1px solid red; */
    border-radius: 6px;
    }
    .v-input--selection-controls__input .v-icon {
        width: 50px;
        height: 50px;
        border-radius: 20px;
        color: white;
    display: flex;
    align-self: center;
    justify-content: center; 
    align-content: center
}
.mdi-checkbox-blank-outline::before {
    background-color: white;
    border: 1px solid #7F56D9;
    display: flex;
    align-self: center;
    justify-content: center; 
    align-content: center
}
.mdi-checkbox-marked::before {
    padding: 1px;
    background-color: #7F56D9;
    font-size: 25px;
}
.v-data-table > .v-data-table__wrapper > table > tbody > tr,
.v-data-table > .v-data-table__wrapper > table > tbody > tr > td,
.theme--light.v-data-table > .v-data-table__wrapper > table > tbody > tr:not(:last-child) > td:not(.v-data-table__mobile-row) {
  border-top: none;
  border-bottom: none;
}
.v-data-table > .v-data-table__wrapper > table > tbody > tr > td,
    .customer-table.theme--light.v-data-table > .v-data-table__wrapper > table td {
        padding: 12px 24px 12px 24px !important;
    }
    .theme--light.v-data-table tbody tr.v-data-table__selected,
    .theme--light.v-data-table tbody tr:hover {
    /* background: #f5f5f5; */
    background: unset
}
.theme--light.v-data-table > .v-data-table__wrapper > table > tbody > tr:hover:not(.v-data-table__expanded__content):not(.v-data-table__empty-wrapper) {
    background: unset;
}
    .customer-table.theme--light.v-data-table  tbody tr:nth-child(2n+1),
    .theme--light.v-data-table tbody tr.v-data-table__selected:nth-child(2n+1),
    .theme--light.v-data-table > .v-data-table__wrapper > table > tbody > tr:nth-child(2n+1):hover:not(.v-data-table__expanded__content):not(.v-data-table__empty-wrapper) {
 
      background-color: hsla(210, 24%, 98%, 1);
    }

</style>