<template>
  <Page>
    <ActionBar title="NativeScript-Vue Pokemon"/>
    <StackLayout backgroundColor="#FFF">
      <FlexboxLayout flexDirection="column" class="PokemonContainer">

        <Image :src="this.image" />
        <Label :text="this.name" class="PokemonName" />

        <ListView class="PokemonTypes" separatorColor="#FFF" for="type in this.types">
          <v-template>
            <Label :text="type.name" :class="type.classname" />
          </v-template>
        </ListView>

        <Label :text="this.description" class="PokemonDescription" textWrap="true" />

        <Button text="Back" @tap="goBack" />

      </FlexboxLayout>
    </StackLayout>
  </Page>
</template>

<script>
  export default {

    props: ['id', 'name', 'image', 'description', 'types'],

    methods: {
      goBack: function (args) {
        this.$navigateBack();
      }
    }

  }
</script>

<style scoped>
ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.PokemonContainer {
  align-items: center;
}

Image {
  width: 270;
  margin-top: 20;
}

.PokemonName {
  font-size: 35;
  color: #333;
}

.PokemonDescription {
  padding: 10;
  font-size: 16;
}

.PokemonTypes {
  margin-top: 10;
}

.TypeText {
  text-align: center;
  width: 75;
  color: #FFF;
  padding: 5;
}

.poison {
  background-color: violet;
}

.normal {
  background-color: #8a8a59;
}

.fire {
  background-color: #f08030;
}

.water {
  background-color: #6890f0;
}

.electric {
  background-color: #f8d030;
}

.grass {
  background-color: #78c850;
}

.ice {
  background-color: #98d8d8;
}

.fighting {
  background-color: #c03028;
}

.poison {
  background-color: #a040a0;
  color: #FFF;
}

.ground {
  background-color: #e0c068;
}

.flying {
  background-color: #a890f0;
}

.psychic {
  background-color: #f85888;
}

.bug {
  background-color: #a8b820;
}

.rock {
  background-color: #b8a038;
}

.ghost {
  background-color: #705898;
}

.dragon {
  background-color: #7038f8;
}

.dark {
  background-color: #705848;
}

.steel {
  background-color: #b8b8d0;
}

.fairy {
  background-color: #e898e8;
}
</style>