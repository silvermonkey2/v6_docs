Manual for views
==============================

.. note:: Documentation is still in development process. Please do not hesitate to contact us on support@silvermonkey.net for further information.

*******
Welcome
********

This document is meant to be a source for all information regarding the 
administration and installation of Silver Monkey v6 Views.

.. contents:: *In this article:*
  :local:
  :depth: 3



******
Views
******

Data
-----

All data which is used on the page is inserted via sql-statement. 

 
.. literalinclude:: _static/Data_Code_Example.xml
  :language: xml






Form
-----

HTML-Elements
-------------


Atributes
-----------

.. csv-table::
    :header: "Atribute","Description"
    :widths: 15, 40

    "Type", "Static. If no other type is defined, textbox is going to be used as standart"
    "Data","SQL Queries used to generate data for this particular configuration"
    "ID","ID of the controlling element. If no ID is set while configuring, one will automatically be generated"
    "Title","Name of the view"
    "Format","Design options to format the views, typo, color, fontsize, etc"
    "Class",""
    "Style","css sheet for general style options"
    "Watermark","digitally watermark against copyright infringement"


Button
------

Button are triggers in order to execute certain scripts or commands with interaction from the user.
The table below shows different configuration elements.

.. csv-table::
    :header: "Atribute","Description"
    :widths: 15, 40


    "ID","Unique Name used for referencing"
    "Function", ""


.. literalinclude:: _static/Button_Code_Example.xml
  :language: xml
  
 

Lists
------

Display entrys of another class (e.g. table). It is possible to use placeholders for attributes in this statement.

 .. csv-table::
    :header: "Atribute","Description"
    :widths: 15, 40


	"ID", "Unique name, used for referencing and identifying."
	"Command",""

An example of how to use the different attributes.

.. literalinclude:: _static/List_Code_Example.xml
  :language: xml

	   

WorkflowControl
----------------

ButtonMore
-----------
Is used to initiate furher actions for this button. For example postPushButton scripts as seem in the example below.

.. literalinclude:: _static/ButtonMore_Code_Example.xml
  :language: xml
  
WorkflowChart
-------------
Visualizes workflows through bpmn or epk diagramm.

Insert jpeg here of visualized workflow.

Explanation how it works to implement one of these workflows

Chart
------
A visualization of numbers in a diagram. Used mostly in dashboards to show peaks of downloads or orders in this tool.

insert jpeg here

insert how it works below

Data comes from an sql?

Search
-------
A function to iterate through the whole database comparing the search item with it.
Can be implemented through a search bar or used in the configuration as seen below.


.. literalinclude:: _static/Search_Code_Example.xml
  :language: xml


Rating
---------
An attribute used for items such as hardware or softwware rated by the users who ordered them in self service. Based on this rating filtering and sorting items in different views. The shop area for self service is an example for.
every item has an additional field for a rating from 0-5.

Insert shop picture unsorted and sorted.

Tile
----------

Tiles are design elements for webdesign. A tile contains branding and color is easy to reproduce. Different color- and fontsets can be used design a constant look for the website.

NavTree
----------
A NavTree uses an already existing table to build a navigation element out of it. 
Every column represents the first level of navigation and it contains all elements as a second level navigation in that column.

  
.. literalinclude:: _static/NavTree_Code_Example.xml
  :language: xml
Repeater
--------
A funcion to repeat certain commands. Refreshing a list in a certain view for example.
 
.. literalinclude:: _static/Repeater_Code_Example.xml
  :language: xml

DataTable
----------
A DataSet is made up of a collection of tables, relationships, and constraints. 
In ADO.NET, DataTable objects are used to represent the tables in a DataSet. A DataTable represents one table of in-memory relational data; the data is local to the  
.NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a DataAdapter.
The DataTable class is a member of the System.Data namespace within the .NET Framework class library. You can create and use a DataTable independently 
or as a member of a DataSet, and DataTable objects can also be used in conjunction with other .NET Framework objects, including the DataView.
You access the collection of tables in a DataSet through the Tables property of the DataSet object.
The schema, or structure of a table is represented by columns and constraints. You define the schema of a DataTable using DataColumn objects as well as 
ForeignKeyConstraint and UniqueConstraint objects. The columns in a table can map to columns in a data source, contain calculated values from expressions, 
automatically increment their values, or contain primary key values.
In addition to a schema, a DataTable must also have rows to contain and order data. The DataRow class represents the actual data contained in a table. 
You use the DataRow and its properties and methods to retrieve, evaluate, and manipulate the data in a table. As you access and change the data within a row, 
the DataRow object maintains both its current and original state.
You can create parent-child relationships between tables using one or more related columns in the tables. You create a relationship between DataTable objects using 
a DataRelation. DataRelation objects can then be used to return the related child or parent rows of a particular row. For more information, see Hinzufügen von 'DataRelations'. 



List
--------
Represents a strongly typed list of objects that can be accessed by index. Provides methods to search, sort, and manipulate lists.


.. literalinclude:: _static/ListType_Code_Example.xml
  :language: xml

  ..csv-table::
  
  :header: "Attribute","Description"
	:widths: 15, 40

  "Type","Defines the type of list. Three types are available Bullet, Number or Table."
  "listheader","Name of the list"
  "item","Contains the term and the description."


Splitter
----------
Represents a splitter control that enables the user to resize docked controls. 


.. literalinclude:: _static/Splittter_Code_Example.xml
  :language: xml
     

Functionbar
----------------


The bar simply lists all the function definitions inside the file.  
The pattern matching used to generate the function list.

Frame
------
A frame is used to build a website, to make it more navigateable. 
Certain elements of the website are put into single frames to make resizing more manageable.


Header
-------
Menubar to navigate trough a certain page/view. It is built up like a navigation-element.



  

.. literalinclude:: _static/ButtonMore_Code_Example.xml
  :language: xml

Script
-------
Scripts are interpreted programms to automate processes. They can be implemented through a variety of triggers and actions. 


Style
------

A style is used to implement a general configuration of style elements like color, font, fontsize and branding. 


General configuration
------------------------

How to generally configurate your own views is descriped here. The items are linked to the configuration items in order to give further explanation.
..Link every item to its own site

..code-block::
<View Icon="**Place designated icon here**">
  <Name Lang="DE">**Name of the view used for referencing**</Name>
  <Data>
    **SQL-Query to get the needed data**
  </Data>
  <Form>
  **specify form of the view here**
    <Header>
      <HeaderMenuItem Title="**First Level menu item**" Link="**Link to the specified view**" />
      <HeaderMenuMore Title="**First Level menu item**">
        <HeaderMenuItem Title="**Second level menu item**" Link="**Link to the specified view**" />
      </HeaderMenuMore>
    </Header>
    <Splitter>
      <Left>
        <List Id="List" Command="LoadFrame('EditItem', 'View.aspx?ViewId=40050&amp;Id='+strId, strDirection);" Add="LoadFrame('EditItem', 'View.aspx?ViewId=40050&amp;Id=-2', 'down');">
          <ListItem>
            <div class="Content">
              <div class="Title">{DisplayName}</div>
              <div class="Text">{Count} Installationen</div>
            </div>
          </ListItem>
        </List>
      </Left>
      <Right>
        <Frame Id="EditItem" />
      </Right>
    </Splitter>
  </Form>
</View>


.. literalinclude:: _static/ButtonMore_Code_Example.xml
  :language: xml