<template>
  <v-app class="bg">
    <v-container fluid class="container">
      <v-row cols="12">
        <h2 class="paragraph">2021 Form 1099-B</h2>
      </v-row>
      <details-component/>
      <v-row>
        <income
          income="Income"
        />
      </v-row>

      <v-row>
        <v-form class="form">
          <v-row class="row">
            <selects
              label="Applicable checkbox on Form 8949"
              :stylings="inputStyle"
            />
            <inputIndex
              label="1a Description of property (Example: 100 sh. XYZ Co.)"
              :styling="inputStyle"
            />
          </v-row>
          <v-row class="row">
            <inputIndex
              label="1b Date acquired"
              :styling="inputStyle"
              icon="fa-calendar"
            />
            <inputIndex
              label="1c Date sold or disposed"
              :styling="inputStyle"
              icon="fa-calendar"
            />
          </v-row>
          <v-row class="row">
            <inputIndex
              label="1f Accrued market discount"
              :styling="inputStyle"
            />
            <inputIndex
              label="1g Wash sale loss disallowed"
              :styling="inputStyle"
            />
          </v-row>
          <v-row>
            <div class="checkbox">
              <checkbox
                checkbox-label="Short-term gain or loss"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Check if proceeds from: Collectibles"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Long-term gain or loss"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Check if proceeds from: QOF"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Check if noncovered security"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Reported to IRS: Gross proceeds"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Check if loss is not allowed based on amount in 1d"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Reported to IRS: Net proceeds"
              />
            </div>
            <div class="checkbox">
              <checkbox
                checkbox-label="Check if basis reported to IRS"
              />
            </div>
          </v-row>

          <v-row class="row">
            <inputIndex
              label="Federal income tax withheld"
              :styling="inputStyle"
            />
            <inputIndex
              label="Profit or (loss) realized in 2021 on closed contracts"
              :styling="inputStyle"
            />
          </v-row>
          <v-row class="row">
            <inputIndex
              label="Unrealized profit or (loss) on open contracts—12/31/2020"
              :styling="inputStyle"
            />
            <inputIndex
              label="Unrealized profit or (loss) on open contracts—12/31/2021"
              :styling="inputStyle"
            />
          </v-row>
          <v-row class="row">
            <inputIndex
              label="Aggregate profit or (loss) on contracts"
              :styling="inputStyle"
            />
            <inputIndex
              label="Bartering"
              :styling="inputStyle"
            />
          </v-row>

          <v-row class="row btn">
            <index-button
              button="Save"
              color="#F4B42A"
              :style="saveButton"
            />
            <index-button
              button="Cancel"
              color="white"
              :style="buttonStyl"
            />
          </v-row>

        </v-form>
      </v-row>

    </v-container>
  </v-app>
</template>

<script>
import selects from "~/components/selects";
import IndexButton from "~/components/buttons";
import detailsIndex from "~/components/details";
import income from "~/components/Income"
import inputIndex from "~/components/inputs";
import checkbox from "~/components/checkbox";
import detailsComponent from "~/components/detailsComponent";
export default {
  name: "index",
  components: {
    IndexButton,
    selects,
    detailsIndex,
    income,
    inputIndex,
    checkbox,
    detailsComponent
  },
  data(){
    return {
      customStyle: {
        'width': '200px',
        'height': '48px',
        'margin-right': '8px',
        'border-radius': '10px'
      },
      inputStyle: {
        'width': '508px',
        'border-radius': '10px'
      },
      buttonStyl: {
        'width': '508px',
        'font-family': 'Neue Haas Grotesk Text Pro',
        'font-style': 'normal',
        'font-weight': 400,
        'font-size': '16px',
        'line-height': '20px',
        'color': '#6F6F6F',
        'flex': 'none',
        'order': 0,
        'flex-grow': 0,
        'border': '1px solid #BFBFBF',
      },
      saveButton: {
        'width': '508px',
        'font-family': 'Neue Haas Grotesk Text Pro',
        'font-style': 'normal',
        'font-weight': 400,
        'font-size': '16px',
        'line-height': '20px',
        'color': 'white',
        'flex': 'none',
        'order': 0,
        'flex-grow': 0,
        'border': '1px solid #BFBFBF',
      },
      addressInput: {
        'width': '100%',
        'border-radius': '10px'
      }
    }
  }
}
</script>

<style scoped>
.bg{
  background: #E5E5E5;
  width: 1640px;
  padding-left: 280px;
  padding-right: 280px;
}
.form{
  background: #FFFFFF;
  box-shadow: 2px 2px 10px rgba(210, 209, 223, 0.3);
  border-radius: 10px;
  margin-top: 42px;
  padding: 36px 24px 36px 24px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 36px;
}
.row{
  display: flex;
  justify-content: space-around;
}
.row_state{
  width: 100%;
  margin-left: 10px;
  margin-right: 10px;
}
.checkbox{
  width: 100%;
  margin-left: 10px;
  margin-bottom: 15px;
}
.btn{
  margin-bottom: 32px;
}
</style>

