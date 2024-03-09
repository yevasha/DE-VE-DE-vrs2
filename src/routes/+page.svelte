<script>
  import { async } from "@firebase/util";
  import { firestore } from "$lib/firebase-config";
  import { collection, addDoc ,getDocs, updateDoc, doc, deleteDoc } from "firebase/firestore";
  
  console.log('firestore',firestore)

  async function getMovie() {
  try {
    const movieCollection = await getDocs(collection(firestore, "movies"));
      movieCollection.forEach((doc) => {
      console.log(`${doc.id} => ${doc.data()}`);
    });
      } catch (e) {
        console.error("Error adding document: ", e);
      }
  }


async function addMovie() {
  try {
    const moviesCollectionRef = await addDoc(collection(firestore, "movies"), {
      titel: "Eva",
      genre: "Komedi",
      releaseDate: "25/12/2003",
      watched: false
    });
      console.log('try to yeet Eva ',moviesCollectionRef)
      console.log("Document written with ID: ", moviesCollectionRef.id);
    } catch (e) {
      console.error("Error adding document: ", e);
    }
    }


async function updateMovie() {
  try {
// Add a new document in collection "cities"
await setDoc(doc(db, "cities", "movie"), {
  name: "Los Angeles",
  state: "CA",
  country: "USA"
});

} catch (e) {
  console.error("Error adding document: ", e);
}
}





// Delete me here 
async function deleteMovie() {
  try {

    await deleteDoc(doc(firestore, "movies", "movie"));   
    
  console.log("Byeeee tihi ") 
} catch (e) {
  console.error("Error adding document: ", e);
}
}






</script>






<h1 class="p-4 m-2 text-3xl font-bold">DE-VE-DE Movie Database</h1>


<button class="btn" on:click={addMovie}> yeeet</button>
<button class="btn btn-secondary" on:click={getMovie}> Give me the chockladboll</button>
<button class="btn btn-neutral" on:click={deleteMovie}> meow</button>

<div class="hero min-h-screen bg-base-200">
  <div class="hero-content flex-col lg:flex-row-reverse">
    <div class="text-center w-96 lg:text-left">
      <h1 class="text-5xl font-bold">Filmer att se</h1>
      <p class="py-6">Fyll i info om filmen du vill se</p>
    </div>

    <div class="card shrink-0 w-full max-w-sm shadow-2xl bg-base-100">
      <form class="card-body">
        <div class="form-control">
          <!-- svelte-ignore a11y-label-has-associated-control -->
          <label class="label">
            <span class="label-text">Title</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control">
          <!-- svelte-ignore a11y-label-has-associated-control -->
          <label class="label">
            <span class="label-text">Genre</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control">
          <!-- svelte-ignore a11y-label-has-associated-control -->
          <label class="label">
            <span class="label-text">Release date</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control mt-6">
          <button class="btn btn-primary">Lägg till</button>
        </div>
      </form>
    </div>
  </div>
</div>

<div class="flex m-8 space-x-4">
  <div class="card w-96 bg-base-100 shadow-xl">
    <div class="card-body">
      <h2 class="card-title">Title:</h2>
      <p>Genre:</p>
      <p>Release date:</p>
      <div class="card-actions justify-end">
        <!-- Open the modal using ID.showModal() method -->
        <button class="btn btn-primary w-20" onclick="my_modal_1.showModal()"
          >Edit</button
        >

        <button class="btn btn-primary">Watched</button>
      </div>
    </div>
  </div>

  <dialog id="my_modal_1" class="modal">
    <div class="modal-box">
      <h3 class="font-bold text-lg">Edit</h3>

      <form class="">
        <div class="form-control">
          <label class="label">
            <span class="label-text">Title</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control">
          <label class="label">
            <span class="label-text">Genre</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control">
          <label class="label">
            <span class="label-text">Release date</span>
          </label>
          <input type="" placeholder="" class="input input-bordered" required />
        </div>

        <div class="form-control mt-6">
          <button class="btn btn-primary">Delete</button>
          <button class="btn btn-primary">Save</button>
        </div>
      </form>
    </div>
  </dialog>
</div>
