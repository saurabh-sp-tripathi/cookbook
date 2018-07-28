# cookbook
This is personal project with recieps and workflows, probably not of much use for anybody else.
I have been failing on cooking and been eating outside, I hope will some operational planning, I will be able to save some time and make it easy enough.

```
var assert = require('assert');
const berries = [strawberry, blackberry, bluebarry, rasberry, cranberry];
//in case you are busy this is bare minimum do-able
const defualt_easy_breakfasts = ["bread", "peanut_butter", "chia_seeds", get_fruits(), "vegan_protein_shake"];

const defualt_easy_fruits = [
  berries, //try to prewash and store, no cutting no prep is needed at all.
  apple, //no peeling
  banana
];

const defualt_easy_recipies = [];

var fruit_stock = []; //shouldn't be for more thant 6 days
var select_shop; 
var recipies_4_a_week = [
  
];

function shop_Fruits() {
  if (have_Time_For_FruitPrep()) {  
    fruit_stock = fruits;
  } else {
    fruit_stock = defualt_easy_fruits;
  }
}

function get_fruits() {
  assert((fruit_stock === defualt_easy_fruits || isPrep(fruit_stock)));
  //round robin 
  var tmp = fruit_stock[fruit_stock.lenght - 1];
  fruit_stock[fruit_stock.lenght - 1] = fruit_stock[0];
  fruit_stock[0] = tmp;
  return tmp;
}


var plan = {};
// parse the given recipies probably hyperlinks and makes up a consolidated shopping list 
// can evolve to ask how many servings of each receipy intended
// can use AI to identify from unstructed data web
function get_shop_list_for_receipies(recipies) {};  
var get_soaking_items = function(receipies) {

}
var todoList = [
  {name: "wash dish dry cloths"},
  {name: "decide receipy"},
  {name: "shop ingredient", dependsOn: "decide receipy"}, 
  {name: "put reminder and soak items in receipies", soakableItems: get_soaking_items(recipies_4_a_week)}
];

var todoAlerts = function {
  if(today === "friday") {
    if(recipies_4_a_week.length < 10) {
      console.log("Last chance to fill in the meal slots for next week");
      console.log("if too busy, you may plan a mix of home made + outsite meals");
    }
    console.log("You have soacked:"+get_shop_list_for_receipies(recipies_4_a_week));    
  }
}

function decide_reciepies() {
  if(recipies_4_a_week.length === 0) {
    recipies_4_a_week = defualt_easy_recipies;
  }
  var prep_time_available = prompt("Please give a rough estimate of prep time you may have");
  make_reciepy_list_options_with_given_prep_time(prep_time_available);
  //select and store in recipes_4_week
}

function shop() {  
  assert(plan.forDays() < 6); //longer plan stuffs the refrigerator and food rots
  var shop_list = get_shop_list_for_receipies(recipies_4_a_week);
  shop_list = categorize(shop_list);// this helps in fast shopping; 
  //{avacode, spinach, manago} ->  {paper towel, soap} flow is better than  avacode -> paper towel -> spinach -> soap -> mango  
  //add fruit to shoplist or just
  shop_Fruits();  
}


var threeContainerWashingTechnique = function () {
  /**
   * -------------------------------------------------------------------------------------------------------------------------------------------------------------
   * bucket 1 : helpling/transition bucket   (T_BK)           |             bucket 2: operating bucket  (OP_BK)    |       bucket 3 : clean bucket or sink (C_BK)
   * --------------------------------------------------------------------------------------------------------------------------------------------------------------
   * - Make sure OPERATING_BUCKET is clean
   * - put all the dish to be washed in OP_BK (try to reuse water if using sink by blocking it)
   * - apply soap, wipe to remove stain and put in T_BK //keep the tough stains separate (4th bucket)
   * - once OP_BK is empty - clear and clean it (put clean water)
   * - rinse and put in clean sink 
   */
}

var washing_routine = function () {
  console.log("keep a big napking with you to wipe and dry you hand");
  var clock = 0;
  var container_list = get_container_list_for(recipies_4_a_week, fruit_stock);
  //straining container could be a steel strainer in which you will keep foods after washing and keep 'em together by net.
  //water will flow out in collect in container, if you another sink you may keep it clean and put the food in net in it to strain.
  console.log("gather wash_bucket, straining nets, straining containers, cookwares and "+container_list+" : 2 mins"); 
  clock = clock + 2; //2 m
  console.log("Wash and bleach sink: 2 mins"); 
  clock = clock + 2;// 4 m; if cleaning sink require more than 2 (it must be in case of straining), plan it for another day
  threeContainerWashingTechnique();//set up
  clock = clock + 2 // 6 m
  if(get_Dirty_Count(container_list, "wash bucket") > 5) {
    console.log("use dish washer or leave 'em in sink/bucket for soaking; time : 8 m");
    clock = clock + 2;
  }
  console.log("wash the 'washing bucket' and these containers : "+ container_list+ " : 5 mins"); //checkbox 
  console.log("Use a napkin, wipe dry outside of food container (not wash bucket), don't dry from inside cuz we are still preping");
  clock = clock + 5; // 11 m or 13 m
  console.log("wash food items one by one and keep 'em in net and place net on strainer or sink : 16m");
  clock = clock + 5; // 16 m

}

function prep() {
  if(!isTodoListComplete(todoList)) {
    console.log("Your todo list is incomplete for following items : "+getIncompleteItem(todoList));
  }
  // water spill, big fruits, 
  // small fruit : wash, strain, store, 
  //
  //-------------------------------------------------------------------------------------------------------------------
  // you may think to make a mix in small ziplocks or small containers:
  //        reusing ziplock : needs wash, strain, dry, keep too long without wash may rot the juices in it
  //        container : container may be best to use, as is easy to wash (dishwasher) but may keep 
  //      The above two don't give any advantage over, packing the fruits daily from 3-4 different container
  //-------------------------------------------------------------------------------------------------------------------

  console.log("if clean sink has clean utensils arrange 'em in place and empty");
  washing_routine(); //15 mins: washed : wash_bucket, straining nets, straining containers, cookwares and container_list
  cut_fruits_n_store();// 15 min ; may exceed this if you have pineapple. 
  cut_n_chop_for_meals();//  



}

/**
 *  buy 
 * straining net
 */


```
