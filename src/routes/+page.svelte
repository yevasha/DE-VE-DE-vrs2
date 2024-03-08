<script>
  import { async } from "@firebase/util";
  import { db } from "$lib/firebase-config";
  import { collection, getDocs, updateDoc, doc } from "firebase/firestore";

  const moviesCollectionRef = collection(db, "movies");

  console.log(moviesCollectionRef);
</script>

<h1 class="p-4 m-2 text-3xl font-bold">DE-VE-DE Movie Database</h1>

<div class="hero min-h-screen bg-base-200">
  <div class="hero-content flex-col lg:flex-row-reverse">
    <div class="text-center w-96 lg:text-left">
      <h1 class="text-5xl font-bold">Filmer att se</h1>
      <p class="py-6">Fyll i info om filmen du vill se</p>
    </div>

    <div class="card shrink-0 w-full max-w-sm shadow-2xl bg-base-100">
      <form class="card-body">
        
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
        <button class="btn btn-primary w-20"  onclick="my_modal_1.showModal()"  >Edit</button>
       
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