# Read: 28 - RecyclerView  

# Content  

RecyclerView makes it simple to show vast amounts of data. You provide the data and specify the appearance of each item, and the RecyclerView library dynamically
produces the elements as needed. RecyclerView recycles those individual items and is also the library's name. RecyclerView does not delete an item's view when it
scrolls off the screen. RecyclerView, on the other hand, reuses the view for fresh items that have scrolled across the screen. This greatly increases performance,
as well as the responsiveness of your program and the amount of power it consumes. Key classes, The ViewGroup that contains the views that relate to your data is
called RecyclerView. RecyclerView.ViewHolder A view holder object defines each individual member in the list, and the RecyclerView ties the view holder to its data
when it is generated. RecyclerView.Adapter By executing methods in the adapter, RecyclerView requests those views and binds them to their data. The individual
components in your list are arranged by LayoutManager. Make a plan for your layout. A LayoutManager class organizes the items in your RecyclerView. 
Three layout managers are included in the RecyclerView library. The elements in a one-dimensional list are arranged using LinearLayoutManager. GridLayoutManager uses
a two-dimensional grid to organize all objects. Staggered GridLayoutManager is identical to GridLayoutManager, but that it does not require that items in the same row
or column have the same height or width. As a result, elements in a row or column may get offset from one another. The Adapter and ViewHolder classes work together
to specify how your data is displayed when you implement your adapter and view holder. The ViewHolder is a wrapper around a View that holds the layout for a single
list item. As needed, the Adapter generates ViewHolder objects and sets the data for those views. You must override three important methods while defining your adapter.
on RecyclerView uses CreateViewHolder() anytime it wants to generate a new ViewHolder. onBindViewHolder() This method is called by RecyclerView to associate a ViewHolder
with data. getItemCount() This function is used by RecyclerView to determine the amount of the data collection.  
