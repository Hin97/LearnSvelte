<script>
    export let course = ""
    let color = false
    $: if(course.includes("!")){
      color = true
    }else {
      color = false
    }
  </script>
  
  <style>
    .red{
      color: #ff0000
    }
  </style>



<h1 class="{color? "red" : ""}">{course}</h1>