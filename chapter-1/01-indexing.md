!SLIDE
# Chapter 1
## Indexing

!SLIDE
# Basic Index
## fast lookup

!SLIDE
# Sequential Search
## O(n)

!SLIDE
# B-Tree Search
## O(log(n))

!SLIDE center
![1-10.png](1-10.png)

!SLIDE center
![1-10.png](1-100.png)

!SLIDE center
![1-10.png](1-1000.png)

!SLIDE
# Romeo and Juliet
## One DB record for each line
## 1000 random queries

!SLIDE
# Results
              without index 5.54576
              with index    0.787138
              speedup       704%

!SLIDE
# Easy to setup
    @@@ ruby
    add_index :table, :column

!SLIDE
# ActiveRecord
## validates_uniqueness_of

!SLIDE
# ActiveRecord
### Performs a select before the insert

!SLIDE
# ActiveRecord
### Double Query

!SLIDE
# Unique Index in DB
## Detects collision while doing the insert

!SLIDE
# Insert 10,000 numbers

!SLIDE
# Try to insert 1,000 duplicates


!SLIDE
# Results
## PostgreSQL
    @@@
               no index   0.891351
               with index 0.849832

!SLIDE
# Results
## ActiveRecord
    @@@      
               no index   4.493282
               with index 7.240643

!SLIDE
# Easy to setup
    @@@ ruby
    add_index :table, :column, :unique => true

!SLIDE
# Indexing on Expressions

!SLIDE
# Frequent Query
## Case-insensitive login
    @@@ ruby
    User.find(:first, :conditions => 
      ['lower(login) = ?', username]
    )

!SLIDE
# Index on Expression
    @@@ ruby
    add_index :users, 'lower(login)'