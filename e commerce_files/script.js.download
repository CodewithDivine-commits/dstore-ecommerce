//select all  "Add-to-cart" buttons
const cartButtons= document.querySelectorAll('.add-to-cart');

//Select cart count display //
const cartCount=document.getElementById("cart-count");

//cart popup elements//
const cartOverlay=document.getElementById("cart-overlay");
const cartItemslist=document.getElementById("cart-items-list");
const cartTotal=document.getElementById("cart-total");
const cartNav=document.getElementById("cart-button");
const cartClose=document.getElementById("cart-close");
const clearCartBtn=document.getElementById("cart-clear");
const checkoutBtn=document.getElementById("cart-checkout");


// Let's keep track of the numbers of the items in the cart//
let cart=[]; //to hold products (objects with name and price)
let total=0; //total price tracker


//Add products when buttons clicked //
//loop through buttons and add event listener to each
cartButtons.forEach(button=>{
    button.addEventListener("click",()=>{
        const name=button.getAttribute("data-name");  // product name
        const price=parseFloat(button.getAttribute("data-price"));

        //Add product to cart array
        cart.push({name, price});

        //update total//
        total+=price;

        //update cart count display 🛒
        cartCount.textContent=cart.length;
      


        //Refresh cart UI
        renderCart();
    });
});

//Render cart items in the popup
function renderCart(){
    cartItemslist.innerHTML=""; //clear old items
    total=0; // reset total before recalculating
    
    cart.forEach(item =>{
        const li=document.createElement("li");
        li.textContent=`${item.name} -$${item.price.toFixed(2)}`;
        cartItemslist.appendChild(li);

        
    //recal total
    total += item.price;
    });


    //update total display
    cartTotal.textContent= total.toFixed(2);
}

//.....................

//show cart when 🛒 clicked

  cartNav.addEventListener("click",()=>{
    cartOverlay.style.display="flex"; //show modal
  });

  //..................

  //close cart with X button//

  cartClose.addEventListener("click",()=>{
    cartOverlay.style.display="none"; //hide modal
  });

  //................

  //Clear cart button
  clearCartBtn.addEventListener("click",()=>{
    cart=[]; //empty cart array
    total=0; // reset total
    cartItemslist.innerHTML="";// clear UI list
    cartTotal.textContent="0.00"; // reset total display
    cartCount.textContent=0; // reset cart count display
  });



  //checkout button (for demo, just alert total)
  const checkout=document.querySelector(".btn-checker");

  checkoutBtn.addEventListener("click",()=>{
    if(cart.length===0){
      alert("Your cart is empty! Add some items first.");
    }else{
      //calculate total 
      const total=cart.reduce((sum, item)=> sum + item.price,0);
      alert("Thank you for your purchase! your total is $"+ total.toFixed(2));
    }
  });