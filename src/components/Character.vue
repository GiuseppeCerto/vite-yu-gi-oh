    <template>
        <li class="character">
            <img :src="character.card_images[0].image_url" alt="">
            <div class="character_name">{{ character.name }}</div>
            <span class="character_tipe">{{ character.archetype }}</span>
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
        display: flex;
        flex-direction: column;
        gap: 9px;
        text-align: center;
        margin: 15px;
        padding-bottom: 10px;
        box-shadow: 4px 4px 5px black;

        img {
            object-fit: cover;
            display: block;
        }

    .characater_name {
        font-size: 28px;
        color: white;
        }
    }

    .character_tipe{
        color: green;
    }
  </style>