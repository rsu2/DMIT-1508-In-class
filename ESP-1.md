# ESP Document 1

This is a sample solution of normalizing the **Customer Order View** in ESP Document 1.

## Customer Order View

## 0NF - List all Attributes

After performing Zero-Normal Form, a single table  (entity) was generated: **Order**.

**Order:**(CustomerNumber, FirstName, Lastname, Address, City,Province, PostalCode, Phone, Date, <b class="pk">OrderNumber</b>,<b class="gp">{</b> ItemNumber, Description, Quantity, CurrenPrice, SellingPrice, Amount <b class="gp">}</b>,Subtotal, GST,Total)

### 1NF - Identify Repeating Groups

After performing First-Normal Form, a new table was generated: **OrderDetail**.

**Order:**(<b class="pk">OrderNumber</b>, Customer, FirstName, LastName, Address, City, Province, PostalCode, Phone, Date, Subtotal, GST, Total)

**OrderDetail:** (<b class="pk"><u class="fk">OrderNumber</u>, ItemNumber</b>, Description, Quantity, CurrentPrice, SellingPrice, Amount)

### 2NF

After performing Second-Normal Form, another new table was generated: **Item**.

**OrderDetail**(<b class="pk"><u class="fk">OrderNumber</u>, <u class="fk">ItemNumber</u></b>, Quantity, SellingPrice, Amount)

**Item** (<b class="pk">ItemNumber</b>, Description, CurrentPrice)

### 3NF

After performing Third-Normal Form, another new table was generated: Customer.

**Order**	(<b class="pk">OrderNumber</b>, <u class="fk">CustomerNumber</u>, Date, Subtotal, GST, Total)

**Customer**	(<b class="pk">CustomerNumber</b>, FirstName, LastName, Address, City, Province, PostalCode, Phone)

### Tables after 3<sup>rd</sup> Normal Form

These are the tables/entities after normalizing the Customer Details View.

**Order**	(<b class="pk">OrderNumber</b>, <u class="fk">CustomerNumber</u>, Date, Subtotal, GST, Total)

**OrderDetail**	(<b class="pk"><u class="fk">OrderNumber</u>,<u class="fk">ItemNumber</u></b>, Quantity,  SellingPrice, Amount)

**Item**	(<b class="pk">ItemNumber</b>, Description, CurrentPrice)

<style type="text/css">
.pk{
    font-weight: bold;
    display: inline-block;
    border: solid thin blue;
    padding: 0 1px;
}
.fk{
    color: green;
    font-style: italic;
    text-decoration: wavy underline green;
}
.gp{
    color: darkorange;
    font-size:1.2em;
    font-weight: bold;

}
</style>