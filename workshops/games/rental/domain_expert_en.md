# Event Storming Workshop - Games Rental

## Domain Expert - Omniscient

You are the cofounder of games rental chain-store, that has been founded 10 years ago. Till now, you were offering offline services of board games rental in 30 stationary rental offices located in whole country.

Due to increased competitiveness in the rental market you decided to create IT system to support your business. You hired a group of computer specialists, who asked you to participate in some kind of a workshop, to share all the required knowledge with them in the fastest possible way. Sounds cool!

Besides the implementation of the system dedicated for offline / stationary rental offices you want to open the new channel over the Internet to allow your customers to browse the games available in your stores, reserve the games and charge the pre-paid accounts. In the process of company digitalization, the elements will be associated with integration with external business intelligence system, to reach even higher advantage over the competitors.

Try to help the IT specialists. Share your knowledge. If they ask the question about the requirement, that you will not find in the notes below - try to answer up to your best knowledge. Remember, it is a workshop and we have limited amount of time - so, do not go too far with your imagination. :)

Try to convince the team to create the common language for describing the things. Maybe create a dictionary of the frequently used words. Naming convention must be understandable for everyone. During the event storming session use the consistent vocabulary on the stickers.

__Do not provide this paper to anyone. Explain the requirements below in your own words. Paraphrase it.__

Below, we put information, that you collected with your colleagues in order to prepare for the workshop.

## Business

* We want to create the system for games-rental chain store.
* Remember, it is a chain store, not a single rental office.
* Each stationary rental office has different games available on the warehouse stock.
* We use following values in terms of controlling the warehouse stocks: quantity of the games (on stock + rented), quantity on stock, quantity rented, quantity reserved. 
* When we rent the game we need to control the available quantities.
* Currently, we have 30 stationary rental offices in 20 different cities in whole country.
* Each stationary rental office has different local administrator, that takes care about the system. It is always one of the employees in the local store.
* In the chain-store we have 1 global administrator, that is allowed to create the new local stores in the system.

## Products / Games

* We rent the board games.
* All the products are being identified in the system by SKU numbers. Also. each product has its own descriptive name, which is used by customers.
* All the products have EAN numbers assigned. We use these numbers to scan the barcodes with the barcodes scanner that we have in all of the stores.
* Barcode scanner works exactly the same as typical keyboard. You connect it to USB or PS/2 port, you can scan the barcode, in result the barcode's value is being written in the computer.
* Sometimes our customers return damaged games. Sometimes they lose some element of the game (like pawn or card). It is a big problem in our business.

## Prices

* Prices are associated to the products.
* Each product has the only one price in the whole chain-store.
* Sometimes, there is a need to apply some value or percent discounts.
* We receive all the payments in EUR.
* We are thinking about the possibility of adding the discount codes to the system. However, it is not a must.
* Each game is being rented for 14 days by default.
* If our client wants to keep the game for 30 days then he needs to pay 10,00 EUR more. However, it must be paid on the first day in the moment of renting the game.
* Extension of the rental period is being printed on the fiscal receipt as a separate position. It is named “Extension of the rental period”.
* If customer postpones the rental then we add him to the List of Debtors and we calculate the penalty.
  * up to 5 days of delay - 20,00 EUR,
  * up to 20 days of delay - 100,00 EUR,
  * 20 days of delay and more - 300,00 EUR,
* Debtor cannot rent the next games as long as he is on our List of Debtors. He can pay the penalty and then we delete him from the list.

## Offline / Stationary rental office

* In each store we have the fiscal printer. After connecting it to the computer it is possible to print the fiscal receipts from the system. 
* Supplier of the fiscal printer delivered a library, which makes it possible to integrate it with the system in very easy way. We can share that with the IT people.
* Customers must pay for each rental.
* Available payment methods are:
  * Cash,
  * Card,
  * Money available in the prepaid account associated with customer’s account in our online rental store.
	* Gift voucher.

## Online rental store

* Customer can sign up and sign in.
* Customer can browse the games by category.
* Customer can see the details of specified game and read about it.
* Customer can reserve the game and pick it up in the offline rental store.
* The length of the reservation is 2 days.
* After the reservation, we deliver the game to the offline rental store within 1 hour (even when the game is not available on the warehouse stock of the chosen offline store, but the game is available in the other offline store).
* If client does not pick up the game within 2 days then we cancel the reservation and the game becomes available for the other customers.
* Reservation is free. However, we must implement some solution to avoid the situation, when some kids reserve the games over and over the game, and they destroy our business. 
* Customer can charge top up his own prepaid account and then use it for purchasing the rentals.
* Payments are being handled by external payments gateway.
* We do not send the games to our customers. It is required to pick up the game in offline stationary rental office.
* When customer picks up the game then we charge the prepaid account or the payment in offline stationary rental office is required.
* That would be great for the users to receive some email and SMS notifications.

## Invoices

* We do not support invoices at all. Only receipts from our fiscal printer.

## In the future

Use these elements only if the team is doing really great. If the team didn’t find out most of the standard requirements mentioned above - do not talk about the ones below.

* We want to integrate external data warehouse, which will be the source for our Business Intelligence system. We will analyze the sales data, statistics for each game, statistics for each localisation.
* We are thinking about renting the computer and console games.
* We are thinking about selling the licenses for the games (we call it - digital products).
* If the customer likes the game a lot - he can buy it.
  * Before buying the game, it is a must to rent the game.
* It is possible to buy the game only in offline stationary rental store. It not possible in online store.


