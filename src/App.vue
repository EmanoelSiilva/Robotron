<template>
  <main>
        <section class="robotron">
            <img class="robo" :src="currentImage" alt="Robotron">
            <figcaption class="titulo">ROBOTRON <br>2000</figcaption>
        </section>

        <section class="box estatisticas">
            <div class="estatistica">
                <p class="estatistica-titulo">Força</p>
                <div class="estatistica-valor">
                    <p class="estatistica-numero">768</p>
                </div>
            </div>
            <div class="estatistica">
                <p class="estatistica-titulo">Poder</p>
                <div class="estatistica-valor">
                    <p class="estatistica-numero">630</p>
                </div>
            </div>
            <div class="estatistica">
                <p class="estatistica-titulo">Energia</p>
                <div class="estatistica-valor">
                    <p class="estatistica-numero">289</p>
                </div>
            </div>
            <div class="estatistica">
                <p class="estatistica-titulo">Velocidade</p>
                <div class="estatistica-valor">
                    <p class="estatistica-numero">597</p>
                </div>
            </div>
        </section>

        <section class="equipamentos">
            <form action="" class="montador">
                <div class="box montador-conteudo">
                    <div class="peca">
                        <label for="" class="peca-titulo">Braços</label>
                        <div class="controle">
                            <buttom class="controle-ajuste">-</buttom>
                            <input type="text" class="controle-contador" :value="arms">
                            <buttom class="controle-ajuste" @click="increase('arms')">+</buttom>
                        </div>
                    </div>
                    <hr class="linha">
                    <div class="peca">
                        <label for="" class="peca-titulo">Blindagem</label>
                        <div class="controle">
                            <buttom class="controle-ajuste">-</buttom>
                            <input type="text" class="controle-contador" :value="armor">
                            <buttom class="controle-ajuste" @click="increase('armor')">+</buttom>
                        </div>
                    </div>
                    <hr class="linha">
                    <div class="peca">
                        <label for="" class="peca-titulo">Núcleos</label>
                        <div class="controle">
                            <buttom class="controle-ajuste">-</buttom>
                            <input type="text" class="controle-contador" :value="cores">
                            <buttom class="controle-ajuste" @click="increase('cores')">+</buttom>
                        </div>
                    </div>
                    <hr class="linha">
                    <div class="peca">
                        <label for="" class="peca-titulo">Pernas</label>
                        <div class="controle">
                            <buttom class="controle-ajuste">-</buttom>
                            <input type="text" class="controle-contador" :value="legs">
                            <buttom class="controle-ajuste" @click="increase('legs')">+</buttom>
                        </div>
                    </div>
                    <hr class="linha">
                    <div class="peca">
                        <label for="" class="peca-titulo">Foguetes</label>
                        <div class="controle">
                            <buttom class="controle-ajuste">-</buttom>
                            <input type="text" class="controle-contador" :value="rockets">
                            <buttom class="controle-ajuste" @click="increase('rockets')">+</buttom>
                        </div>
                    </div>
                </div>
                <input type="submit" value="Iniciar produção" class="producao" id="producao">
            </form>
            <button @click="previousImage">Anterior</button>
            <button @click="nextImage">Próximo</button>
        </section>
    </main>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      images: [
        'img/robotron-azul.png',  
        'img/robotron-amarelo.png',
        'img/robotron-branco.png',
        'img/robotron-preto.png',
        'img/robotron-rosa.png',
        'img/robotron-vermelho.png',
      ],
      currentImageIndex: 0,
      arms: 0,
      armor: 0,
      cores: 0,
      legs: 0,
      rockets: 0,
    }
  },
  computed: {
    currentImage() {
      return this.images[this.currentImageIndex];
    },
  },
  methods: {
    nextImage() {
      if (this.currentImageIndex === this.images.length - 1) {
        this.currentImageIndex = 0;
      } else {
        this.currentImageIndex++;
      }
      console.log(this.currentImageIndex);
    },

    previousImage() {
      if (this.currentImageIndex === 0) {
        this.currentImageIndex = this.images.length - 1;
      } else {
        this.currentImageIndex--;
      }
    },
    increase(item) {
      switch (item) {
        case 'arms':
          this.arms++;
          break;
        case 'armor':
          this.armor++;
          break;
        case 'cores':
          this.cores++;
          break;
        case 'legs':
          this.legs++;
          break;
        case 'rockets':
          this.rockets++;
          break;
      }
    },
    
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
