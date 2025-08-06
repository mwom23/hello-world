<template>
  <div>{{greet}} {{name}}</div>
  <div v-html="any"></div>
  <div v-html="hack"></div>
  <h2 :id="headingId">Heading</h2>
  <button :disabled="isDisabled">Bind</button>
  <h2 class="underline">Underlined text</h2>
  <h2 class="underline" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldout ? 'sold-out' : 'new'" >Soldout? Movie</h2>
  <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array Conditional movie</h2>
  <h2 :class="{
    promoted: isPromoted,
    new: !isSoldout,
    'sold-out': isSoldout
  }">Object Conditional Movie</h2>
 
 <h2 :style="{
  color:highlightColor,
  fontSize: headerSize + 'px',
  padding: '20px'
 }">Inline Style</h2>

 <h2 :style="headerStyleObject">Style Object</h2>

 <div :style="[baseStyleObject,successStyleObject]">success sTYLE</div>
 <div :style="[baseStyleObject,dangerStyleObject]">danger sTYLE</div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      greet:"Hello",
      name: "Superman",
      any:'<b>and Bye</b>',
      hack:`<a href="#" onclick="alert('You have been hacked!')">Win a prize!<a/>`,
        headingId: 'heading',
        isDisabled: false,
        status: 'success',
        isPromoted:true,
        isSoldout:  true,
        highlightColor: 'orange',
        headerSize: 50,
        headerStyleObject: {
          color: 'orange',
          fontSize: '50px',
          padding: '20px'
        },
        baseStyleObject: {
          fontSize: '50px',
          padding: '10px',
        },
        successStyleObject: {
          color: 'green',
          backgroundColor: 'lightgreen',
          border: '1px solid green',
          padding: '20px'
        },
        dangerStyleObject: {
          color: 'darkred',
          backgroundColor: 'red',
          border: '1px solid darkred',
        },
        

    };
  },
};

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

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new{
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>


