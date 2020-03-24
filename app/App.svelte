<page>
    <actionBar title="Svelte firebase rest" />
    <scrollView class="main">
    <stackLayout>
      {#each items as item}
          <flexboxLayout class="product">
            <stackLayout>
              <label class="h1" text={item.fields.teamName}/>
              <label class="h1" text={item.fields.W}/>
              <label class="h1" text={item.fields.L}/>
            </stackLayout>
          </flexboxLayout>
          {:else}
          <activityIndicator busy={true}/>
      {/each}
    </stackLayout>
    </scrollView>
   
</page>

<script>
    import FirestoreParser from "firestore-parser"
    let items = []
    const baseUrl = "https://firestore.googleapis.com/v1/"
    const productsUrl = baseUrl + "projects/my-first-firestore-proje-9c783/databases/(default)/documents/nba-data"

    const getProducts = () => {
        fetch(productsUrl)
        .then(response => response.json())
          .then(json => FirestoreParser(json))
            .then(parsed =>{
                items = parsed.documents
                console.log(items)
             } )
        .catch(error => console.lgo(error))  
    }

    getProducts()
</script>

<style>
 
</style>
