# Unit testing in python

## Reasons:
- Existing code testing
- Good practice to help to refactor code
- Later easier to add new features and change later on

## Basic commands:
- ```pytest``` : run all the tests in the current directory
- ```pytest -cov``` : run all the tests and show the coverage
- ``` coverage html ``` : create a html file with the coverage report


## Basic essentials:

payment.py
```Python
from pay.order import Order
from pay.payment import PaymentProcessor

def pay_order(order: Order):
    if order.total == 0:
        raise ValueError("Can't pay an order with total 0.")
    card = input("Enter your card number: ")
    month, year = input("Enter expiration date (mm/yy): ").split("/")
    payment_processor = PaymentProcessor("API KEY")
    payment_processor.charge(card, month, year, amount=order.total)
    order.pay()
```

</br>

processor.py some elements:
- charge method (card:str, month:int, year:int, amount:int) -> None
- validate_card(card:str, month:int, year:int) -> bool
- luhn_checksum(card_number:str) -> bool


</br>

order.py some elements:
- class OrderStatus(Enum):
  - OPEN = "open"
  - PAID = "paid"
- class LineItem: <a id="LineItem"></a>
  - name: str
  - price: int
  - quantity: int = 1
- @dataclass class Order: <a id="Order"></a>
  - @property def total(self) -> int:
  - def pay(self) -> None:

</br>

```Python
from pay.order import LineItem, Order
from pay.payment import pay_order

def main():
    order = Order()
    order.line_items.append(LineItem("Shoes", price=100_00, quantity=2))
    order.line_items.append(LineItem("Hat", price=50_00))
    pay_order(order)

if __name__ == "__main__":
    main()

```
This is the basic code we want to test. <br/>
With the current status of the code we can only test it manually. <br/>
From now on we will write unit tests for this code. <br/>

It is common and good practice to have a separate folder for the tests. <br/>
In this case we will create a folder called "tests". <br/>
Create the first file called "__init__.py" so python can find it easily. <br/>
</br>

test_line_item.py &emsp; [LineItem](#LineItem)
```Python
from pay.order import LineItem

def test_line_item_default() -> None:
    line_item = LineItem("Test", price=100)
    assert line_item.total == 100
```
After running ``` pytest ``` in command line it discover the test correctly and detected only one test test_line_item and passed. <br/>
<br/>

```Python
from pay.order import LineItem

def test_line_item_default() -> None:
    line_item = LineItem("Test", price=200, quantity=5)
    assert line_item.total == 1000
```
Now we get both 2 tests passed. <br/>
<br/>

For more coverage we can add more tests. <br/>
test_order.py &emsp; [class Order](#Order) </br>
```Python
from pay.order import LineItem, Order

def test_order_total() -> None:
    order = Order()
    assert order.total == 0

def test_order_total() -> None:
    order = Order()
    order.line_items.append(LineItem("Test", price=100))
    assert order.total == 100

def test_order_total() -> None:
    order = Order()
    order.line_items.append(LineItem("Test", price=100))
    order.line_items.append(LineItem("Test", price=100))
    assert order.total == 200
```
After running ``` pytest ``` in command line it discover the test correctly and all of them passed with a higher coverage now. <br/>
We only need to test the pay method in the Order class for a 100% coverage. <br/>
<br/>

```Python
from pay.order import LineItem, Order

def test_order_pay() -> None:
    order = Order()
    order.pay()
    assert order.status == Order.OrderStatus.PAID
```
Now we have 100% coverage. <br/>


# 10:55

## Resources:
- [How To Write Unit Tests For Existing Python Code // Part 1 of 2](https://www.youtube.com/watch?v=ULxMQ57engo)



# Projects where I used this:
