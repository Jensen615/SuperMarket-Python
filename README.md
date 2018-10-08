# SuperMarket-Python
Quick supermarket code 

class GroceryList(object):
  def __init__(self, sList):
    self.shoping_list = sList
  def stock(self, stock):
    self.stock = stock
    return stock
  def prices(self, prices):
    self.prices = prices
    return prices 
  def compute_bill(self, sList, stock, prices):
    self.sList = sList
    self.stock = stock
    self.prices = prices
    total = 0
    for item in sList:
      if item in stock:
      	#checks to see if item is in the iventory
        if stock[item] > 0:
        	#checks to see if the item is available
        	total += prices[item]*sList[item]
        	#adds the price per item to total
        	stock[item] -= sList[item]
					#subtracts the quantity of items from
        	print "There are now %d %s left." % (stock[item], item)

    return "\nYour total is: $%d. Thank you for shopping at J-Glizzy's supermarket" %total
  
my_shopping_list = {"bananas":2, "pears":7}
stock = {
  	"bananas": 6,
  	"apples": 0,
  	"oranges": 32,
  	"pears": 15
    } 
prices = {
  	"bananas": 4,
  	"apples": 2,
  	"oranges": 1.5,
  	"pears": 3
		} 
jensen_list = GroceryList(my_shopping_list)  
print "Today, we have the following fruits: \n", jensen_list.stock(stock)
print "\n"
print "The prices for each fruit are below: \n", jensen_list.prices(prices)
print "\n"
print "Customer: \nI want to buy 2 bananas and 7 pears today"
print "\n"
print "After your purchase today,"
print "\n"
print jensen_list.compute_bill(my_shopping_list, stock, prices)


