### In this repository, we have performed CRUD operation usin sqlite database.

#### 1. Extablishing the connection:-
    connection = sqlite.connect('db_name.db')
    cursor = connection.cursor()

#### 2. Create table:
    cursor.execute('''
        create table if not exists tbl_name(
            col_name1 constraints,
            col_name2 constraints,
            col_name3 constraints
        )    
    ''')

    connection.commit()   #this is necessory.

#### 3. Insert data into table:

    cursor.execute('''
        insert into table_name(col1,col2,col3)
        values(val1,val2,val3)
    ''')
    connection.commit()


#### 4. Fetch all the data from table:
    cursor.execute('select * from tbl_name')
    rows = cursor.fetchall()
    for row in rows:
        print(row)
    
#### 5. Delete any record:
    cursor.execute('''
        delete from tbl_name
        where col_name = val1
   ''' )

#### 6. update any record:

    cursor.execute('''
        update tbl_name
        set col_name = val
        where col_name = val
    ''')

#### 7. Finally close the connection:-
    connection.close()
