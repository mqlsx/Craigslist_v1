# Craiglist
For web final project

Oct 16 2017
1. Front end: JQuery, Bootstrap
   Back end: Laravel
    
2. First realize the full function of the website. Then design the css of the whold website together.

3. Archetecture
  (1) pages
  User
    |_ login
    |_ register
    |_ list items (search, filter, paging)
    |_ cart, wish list
    |_ checkout
    |_ purchase history
    |_ item detail
    |_ user profile modify
    |_ security (password, email)
   
   Admin
    |_ login
    |_ register
    |_ list items (search, filter, paging)
    |_ cart, wish list
    |_ checkout
    |_ purchase history
    |_ item detail
    
   (2) explain
   Admin has the same pages as user. But admin can see some extra things (like buttons).
    
4. Database
  (1) User
    User(userid, password, name, email, sex, address, phone, avater);
    
  (2) Admin
    Admin(userid) 
      foreign key (userid) references User(userid);
    
  (3) Item
    Item(itemid, name, price, quantity, picture, cid, isDeleted)
      foreign key (cid) references Category(cid);
    
  (4) Description
    Description(itemid, description) 
      foreign key(itemid) references Item(itemid);
    
  (5) Cart
    Cart(userid, itemid, quantity) 
      foreign key (userid) references User(userid),
      foreign key (itemid) references Item(itemid);
      
  (6) Purchasehistory
    Purchasehistory(hid, userid, itemid, date, quantity, price, address)
      foreign key (userid) references User(userid),
      foreign key (itemid) references Item(itemid);
      
  (7) Itempic
    Itempic(itmeid, pid, picpath)
      foreign key (itemid) references Item(itemid);
      
  (8) Category
    Category(cid, name);
      
  (9) Wishlist
    Wishlist(userid, itemid)
      foreign key (userid) references User(userid),
      foreign key (itemid) references Item(itemid);
      
5. Time schedule
  (1) finish version 1 before Nov 11 2017.
  (2) Before Nov 6 2017, learn background knowledge.
  (3) From Nov 6 2017 to Nov 11 2017, finish v1.
  
