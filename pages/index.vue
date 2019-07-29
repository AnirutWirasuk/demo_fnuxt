<template>
  <div class="container">
    <div class="card-deck mb-3 text-center">
      <Boxproduct
        v-for="product in listproduct"
        :key="product.id"
        :name="product.name"
        :price="product.price"
      />
      <span v-if="seen">Now you see me</span>
      {{ message }}
      <button class="btn" @click="reverseMessage">Click</button>
      <ul>
      <li v-for="data in datas" :key="data.id"> 
        {{data.studentName}} - {{data.score}}
      </li>
    </ul>
    <span>ชื่อนักศึกษา</span>
    <input v-model="newData.studentName">
    <span>คะแนน</span>
    <input v-model="newData.score">
        <span>คะแนนเฉลี่ย {{averageScore}}</span>

    <button @click="addScore">เพิ่มข้อมูล</button>
    </div>
  </div>
</template>

<script>
import Boxproduct from '~/components/Boxproduct.vue'

export default {
  components: {
    Boxproduct
  },
  beforeCreate() {
    console.log('Nothing gets called before me!')
  },
  created() {
    console.log(
      'propertyComputed will update, as this.property is now reactive.'
    )
  },
  data() {
    return {
      a: 1,
      message: 'test page',
      seen: false,
      newData: {
        studentName: '',
        score: 0
      },
      datas: [
        {
          studentName: 'Student 1',
          score: 50
        }
      ],
      listproduct: [
        {
          id: 1,
          name: 'test product',
          price: 200
        },
        {
          id: 2,
          name: 'test product',
          price: 300
        }
      ]
    }
  },
  watch: {
    averageScore: function() {
      this.saveToServer();
    }
  },
  computed: {
    averageScore: function() {
      var sum = this.datas.reduce(function(accumulate, data) {
        return accumulate + Number(data.score);
      }, 0);
      return (sum / this.datas.length).toFixed(2);
    }
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message
        .split('')
        .reverse()
        .join('')
    },
    addScore: function() {
      this.datas.push({
        studentName: this.newData.studentName,
        score: this.newData.score
      });
      this.newData.studentName = '';
      this.newData.score = 0;
    },
    saveToServer: function() {
       //Call REST API
       console.log("Call to server ...")
    }
  }
}
</script>

<style>
.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
