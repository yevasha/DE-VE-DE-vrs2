<script>
  import { async } from "@firebase/util";
  import { db } from "$lib/firebase-config";
  import { collection, getDocs, updateDoc, doc } from "firebase/firestore";

  const moviesCollectionRef = collection(db, "movies");

  console.log(moviesCollectionRef);
</script>

<h1 class="p-4 m-2 text-3xl font-bold">DE-VE-DE Movie Database</h1>
