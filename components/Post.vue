<template>
    <div>
      <p >
        {{id}}

        {{name}}
      </p>
    </div>
</template>
<script>

export default ({
  name: 'Post',
  props: ['id','name']

})
</script>
