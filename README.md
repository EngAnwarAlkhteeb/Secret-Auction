# Secret Auction

### Description
 
This Python program implements a secret auction where users can place bids anonymously, and the winner with the highest bid is revealed at the end of the auction.

### Features

Users can enter their name and bid amount.
Bids are stored in a dictionary.
The program finds and displays the winner with the highest bid.
Getting Started
Ensure you have Python installed on your machine.

Clone this repository:

bash
Copy code
git clone https://github.com/your-username/secret-auction.git
Navigate to the project directory:

bash
Copy code
cd secret-auction
Run the program:

bash
Copy code
python secret_auction.py
Usage
Enter your name when prompted.
Input your bid amount.
Decide if there are other bidders.
If "yes," the screen will be cleared for the next bidder.
If "no," the program will find and display the winner.
Example
python
Copy code
from art import logo
print(logo)
from replit import clear

bids = {}
bidding_finished = False

def find_highest_bidder(bidding_record):
  highest_bid = 0
  winner = ""
  for bidder in bidding_record:
    bid_amount = bidding_record[bidder]
    if bid_amount > highest_bid:
      highest_bid = bid_amount
      winner = bidder
  print(f"The winner is {winner} with a bid of ${highest_bid}")  
  
while not bidding_finished:
  name = input("What is your name? ")
  price = int(input("What is your bid? $"))
  bids[name] = price
  should_continue = input("Are there any other bidders? Type 'yes' or 'no'.").lower()
  if should_continue == "no":
    bidding_finished = True
    find_highest_bidder(bids)
  elif should_continue == "yes":
    clear()
