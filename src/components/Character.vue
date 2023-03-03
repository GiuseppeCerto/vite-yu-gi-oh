    <template>
        <li class="character card">
            <img :src="character.card_image.image_url" alt="">
            <h3 class="characater__name">{{ character.name }}</h3>
            <span class="characater__tipe">{{ character.archetype }}</span>
        </li>
    </template>
  
    <script>
        export default {
        props: {
            character: {
            type: Object,
            required: true
            },
        }
        }
    </script>
  
  <style lang="scss" scoped>
    .character {
        text-align: center;
        img {
        border-radius: 50% ;
        aspect-ratio: 1/1;
        object-fit: cover;
        display: block;
        margin: 0 auto 24px;
        
        }
        .characater__name {
        font-size: 24px;
        }
    }
  </style>