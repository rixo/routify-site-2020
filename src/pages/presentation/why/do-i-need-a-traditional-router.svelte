<script>
  import {page, route, beforeUrlChange} from '@sveltech/routify'

  $beforeUrlChange(()=>{
    console.log(location.hash)
    return true;
  })
</script>


<!-- routify:options children=[
  {path:"#no",  title: "title"},
  {path:"#yes",  title: "title"},
  {path:"#bar",  title: "title"},
  {path:"#baz",  title: "title"}
] -->

<!-- routify:options index=30 -->
  <article class="c-content">
    <h1>Do I need a traditional router?</h1>
    <h3>Not if you have to ask</h3>
  </article>

