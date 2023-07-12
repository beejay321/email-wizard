<template>
  <div class="container">
    <div class="nav-bar">
      <nav class="nav-brand">
        <span>Email Wizard</span>
      </nav>
      <ul class="tools">
        <li
          class=""
          v-for="(block, index) in contentBlocks"
          :key="index"
          :draggable="true"
          @dragstart="
            (e) => {
              dragStart(e, block.name);
            }
          "
        >
          <span>{{ block.name }}</span>
        </li>
      </ul>
      <div class="send-btn">
        <span>Send</span>
      </div>
    </div>
  </div>

  <div>
    <div @dragover.prevent="dragOver" @drop="dropItem" class="droplocation">
      <div v-for="(content, index) in dropContent" :key="index" class="block">
        <component :is="content.type" v-model="content.content" />
        <button class="remove-btn" @click="removeBlock(index)">remove</button>
      </div>
    </div>
  </div>
</template>

<script>
import TextBlock from "./TextBlock.vue";
import ImageBlock from "./ImageBlock.vue";
import ImageTextBlock from "./ImageTextBlock.vue";
import HeadlineBlock from "./HeadlineBlock.vue";

export default {
  name: "Wizard",
  components: {
    HeadlineBlock,
    TextBlock,
    ImageBlock,
    ImageTextBlock,
  },
  data() {
    return {
      contentBlocks: [
        { name: "Headline", icon: "icon" },
        { name: "Text", icon: "icon" },
        { name: "Image", icon: "icon" },
        { name: "ImageText", icon: "icon" },
      ],
      dropContent: [],
    };
  },
  methods: {
    dragStart(event, block) {
      event.dataTransfer.setData("content-block", block);
      console.log("dragging", block);
    },
    dragOver() {
      console.log("text is dragging over");
    },
    dropItem(event) {
      const itemDropped = event.dataTransfer.getData("content-block");
      if (itemDropped === "Headline") {
        this.dropContent.push({ type: HeadlineBlock, content: "" });
      } else if (itemDropped === "Text") {
        this.dropContent.push({ type: TextBlock, content: "" });
      } else if (itemDropped === "Image") {
        this.dropContent.push({ type: ImageBlock, content: "" });
      } else if (itemDropped === "ImageText") {
        this.dropContent.push({ type: ImageTextBlock, content: "" });
      }
      console.log(itemDropped, "is dropped");
    },
    removeBlock(index) {
      this.dropContent.splice(index, 1);
    },
  },
};
</script>

<style lang="scss" scoped>
.nav-bar {
  padding: 0px 24px;
  display: flex;
  justify-content: space-around;
  border: 0.2px solid rgb(240, 240, 240);
  background-color: rgb(240, 240, 240);
  border-radius: 15px 15px 0px 0px;
}
.nav-brand {
  padding: 16px 24px;
  display: flex;
  align-items: center;
  border-right: 0.2px solid rgb(231, 231, 231);
  font-weight: bold;
  font-size: 32px;
  font-family: "Fasthand", cursive;
}

.tools {
  display: flex;
  flex-direction: row;
  list-style-type: none;
  margin: 0px 6px;
  border-right: 0.2px solid rgb(231, 231, 231);
  padding: 12px 24px 12px 12px;
  gap: 12px;
}
.tools li {
  padding: 16px 22px;
  border: 0.2px solid rgb(231, 231, 231);
  border-radius: 16px;
  cursor: move;
  width: 70px;
  display: flex;
  margin: 8px 0px;
  justify-content: center;
  font-family: "Rubik", sans-serif;
}
.tools li:hover {
  font-weight: bold;
  font-size: 1.05em;
  box-shadow: 5px 3px 3px rgb(217, 217, 217);
  background-color: rgba(255, 255, 255, 0.335);

}

.send-btn {
  display: flex;
  align-items: center;
  font-weight: bold;
  font-size: 18px;
}

.send-btn span {
  border-radius: 30px;
  background-color: rgba(204, 72, 67, 0.613);
  padding: 16px 24px;
}
.droplocation {
  padding: 12px 10px;
  height: 70vh;
  border-radius: 0px 0px 15px 15px;
}

.remove-btn {
  background-color: rgb(255, 255, 255);
  border: none;
  cursor: pointer;
}
.remove-btn:hover {
  box-shadow: 3px 1px 1px rgb(217, 217, 217);
}
</style>
