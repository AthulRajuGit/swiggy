# swiggy
<a href="https://medium.com/@avinashsoni9829/food-ordering-system-low-level-design-633904e32fca">no restuartant </a>
# 2
<a href="https://leetcode.com/discuss/interview-question/object-oriented-design/259629/Design-OO-food-delivery-system"> other one but can use db schema</a>

#3
<a href="https://medium.com/@mayankbansal933/food-delivery-app-lld-c1409ef49266">useful if different breakfast,lunch</a>

#4
<a href="https://github.com/keertipurswani/Swiggy-Zomato-Low-Level-Design">simple</a>

#5
<a href="https://github.com/ashishps1/awesome-low-level-design/blob/main/solutions/java/src/fooddeliveryservice/FoodDeliveryService.java">ashish</a>
```
Design a Food Delivery System (Uber Eats)


Requirements


Users should be able to search for a restaurant by its name.
Users should be able to search food by the food category/cuisine.
The user should be able to see the online menu given a restaurant. Menu will have different sections and each section will have menu item.
The users should be able to see a list of restaurants given a cuisine type.
The users should be able to add meal item in their order cart. Multiple meal items can be added. Users can update their order cart before placing the order.
Users can select a time when they want their order to get delivered.
The system should be able to generate the order.
The system should be able to allocate a delivery order to a delivery agent.
The system should not allow the users to add items from different restaurants at a same time.
System should support multiple payment options like credit cards, pay pal etc.
The system should maintain an order log for each customer for future reference.
System should be able to send notifications regarding the order status.
System should display a message in case of closed restaurant.
Any guest can search for the restaurant and menu items, however, in-order to place a delivery order, the guest should become a member.
The system should forward the placed order to the specified restaurant.
Users should be able to add additional instructions while placing an order.
Main Classes:


Account: will hold information related to account id and password. Will have a method to reset the password.
Person: there will be 6 types or person, admin, restaurant manager, delivery agent, member, and chef. An admin is from the food delivery company who can block and unblock a member. Restaurant manager will be responsible for taking the placed online orders to the chef. Members can place order. Members has Account. Delivery agent can do all the things a member can in addition to delivering the food.
Guest: Guest can only search for food and create an account.
Restaurant: each restaurant will have multiple restaurant instances. Each restaurant has chef, restaurant manager, Menu.
Menu : Menu has menues sections. Each chef can have a different specialty of food. Menu will be same for each restaurant instance.
MenuSection : MenuSection has MenuItems
MenuItem : an order will be place against a menu item.
Order: ill contain information of an order like order price, date, list menu items etc.
OrderLog: this class will maintain the order history of every Member.
OrderCart : will have all the items selected by a member.
Delivery: this will handle delivery of the food. Will have methods like assigning an order to the delivery agent.
Payment: to handle different payment methods.
Notification: will handle sending delivery updates via SMS and Email.
Search Interface: users can search food by restaurant name, and cuisine type.
Find: which implements search interface.
Public class Account {
Private string ID
Private string password
Public boolean resetPassword()
}


Public class Address {
Private string streetAddress
Private string city
Private int zip
Private string country
}
Public abstract class Person {
Private string name
Private string phoneNum
Private string emailID
Private Account account
Private Address address
}


Public class Admin extends Person {
Public boolean blockMember(Member member)
Public boolean unblockMember(Member member)
}


Public class Chef extends Person {
Private string specialty
Public boolean makeOrder(Order order)
}


Public class RestaurantMananger extends Person {
Public boolean receiveOrder()
}


Public class Member extends Person {
Private string specialInstructions
Private OrderCart cart
Private Order order
Private OrderLog log
Private AccountStatus status
Private PaymentStatus status
Public boolean addSpecialInstructions(Order)
Public boolean placeOrder(MenuItem)
Public boolean makePayment(Payment)
}


Public class Guest {
Private int guestID
Public boolean createAccount()
Public boolean searchForFood()
}


Public class Restaurant {
Private int ID
Private string name
Private RestaurantStatus
}


Public class RestaurantInstance {
Private Address address
Private Menu menu
Private RestaurantManager manager
Private Chef chef
}


Public class Enum RestaurantStatus {
OPEN
CLOSED
}


CLASS MENU:
Public class Menu {
Private int menuID
Private string title
Private string description
Privet list menusections
Public Boolean addMenuSection()
}


CLASS MenuSection:
Public class MenuSection {
Private int menuID
Private string title
Private string description
Private list menuItems
Public Boolean addMenuItem()
}


CLASS MenuItem:
Public class MenuItem {
Private int menuItemID
Private string title
Private string description
Private double price
Public Boolean updatePrice(double price)
}


Public class Order {
Private int orderID
Private double totalPrice
Private hashmap<MenuItem, quantity> itemsOrderedQuantityMap
Private OrderStatus status
Private date timeCreated
Public OrderStatus getOrderStatus()
Public Boolean updateStatus()
}


Public class OrderCart {
Private list item
Private int numOfItems
Public Boolean addItem(MenuItems item)
Public Boolean RemoveItem(MenuItems item)
Public Boolean updateItemQuantity(MenuItems item, int quantity)
Public list getItems()
}


CLASS ORDERLOG: Will maintain a list of orders placed
Public class OrderLog {
Private string orderID
Private OrderStatus status
Private date OrderDate
}


Public Enum OrderStatus {
RECEIVED
FAILED
}


CLASS PAYMENT, CreditCard, Cash:
Public abstract class Payment {
Private double price
Private PaymentStatus status
}


Public class CreditCard extends Payment {
Private string nameOnCard
Private int cardNum
Private int CVV
Private date expDate
}


CLASS NOTIFICATION, SMSnotification, EmailNotification:
Public abstract class Notification {
Private string ID
Private string content
Private date timeSent
Public Boolean sendNotification()
}


Public class SMSnotification extends Notification {
Private string phoneNumber
}


Public class EmailNotification extends Notification {
Private string EmailID
}


Public interface Search {
Public list< RestaurantInstance > searchByName (string restaurantName)
Public list< RestaurantInstance > searchByCuisine (string cuisineName)


}


Public class Find implements Search {
hashmap<name, list> nameMap
hashmap<cuisine, list< RestaurantInstance >> cuisineMap


Public list< RestaurantInstance > searchByName(string restaurantName) {
	nameMap.get(restaurantName)
}
Public list< RestaurantInstance > searchByCuisine(string cuisineName) {
cuisineMap.get(cusineName)
}
}


```
