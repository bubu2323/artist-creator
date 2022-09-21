<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable prettier/prettier -->
<!-- eslint-disable prettier/prettier -->
<style>
@import "./assets/style/style.css";
</style>
<script>
export default {
  data() {
    return {
      title: "Create artist",
      nameArtist: "",
      typeArtist: "singer",
      biography: "",
      bornDate: "",
      typeOfSinger: "singer",
      description: "",
      foundationDate: "",
      groupCompotents: 2,
    };
  },
};
</script>

<template>
  <!-- base fomr -->
  <div class="container text-center">
    <div class="mt-2">
      <form id="starterForm" class="rounded-top bc">
        <h2 class="py-3 fs-1" id="title">Artist creator</h2>
        <div class="py-4 flex">
          <div class="containerStarter firstContainer">
            <label for="nameArtist" class="colFlex">Name artist:</label>
            <input
              type="text"
              name="artist_name"
              v-model="nameArtist"
              placeholder="artist or group name..."
            />
          </div>
          <div class="containerStarter secondContainer">
            <label for="typeArtist" class="colFlex">Type of artist:</label>
            <select name="typeArtist" id="" v-model="typeArtist">
              <option value="" disabled selected>type of artist...</option>
              <option value="singer">singer</option>
              <option value="group">group</option>
            </select>
          </div>
        </div>
      </form>
      <!-- singer form -->
      <template v-if="typeArtist == 'singer'">
        <div class="bc rounded-bottom">
          <!-- <form action=""> -->
          <div class="flex">
            <div>
              <label for="bornDate" class="colFlex">Born date:</label>
              <input type="date" name="" id="" v-model="bornDate" />
            </div>
            <div>
              <label for="typeOfSinger" class="colFlex">Type of singer:</label>
              <select name="typeOfSinger" id="typesinger" class="mb-3">
                <option value="" disabled selected>Songwriter</option>
                <option value="singer">Singer</option>
                <option value="songwriter">Songwriter</option>
                <option value="producer">Producer</option>
                <option value="guitarist">Guitarist</option>
                <option value="bassist">Bassist</option>
                <option value="bassist">Bassist</option>
                <option value="keybord">Keybord player</option>
                <option value="flautist">Flautist</option>
                <option value="other">Other</option>
              </select>
            </div>
          </div>
          <div>
            <label for="biography" class="colFlex">About you:</label>
            <textarea name="biography" v-model="biography"></textarea>
          </div>
          <div>
            <input type="button" value="Insert artist" class="my-3 button" />
          </div>
          <!-- </form> -->
        </div>
      </template>
      <!-- group form -->
      <template v-if="typeArtist == 'group'">
        <div class="bc rounded-bottom">
          <div class="flex">
            <div>
              <label for="foundationDate" class="colFlex"
                >foundation date:</label
              >
              <input
                type="date"
                name="foundationDate"
                v-model="foundationDate"
              />
            </div>
            <div>
              <label for="groupCompotents" class="colFlex"
                >Number of components:</label
              >
              <input
                type="number"
                name="groupCompotents"
                min="2"
                v-model="groupCompotents"
              />
            </div>
          </div>

          <label for="description" class="colFlex">About you..</label>

          <textarea
            name="description"
            v-model="description"
            placeholder="Lorem ipsum docet amet sein"
          ></textarea>
          <div>
            <input type="button" value="Insert group" class="my-3 button" />
          </div>
        </div>
      </template>
    </div>
  </div>
</template>
