***********
DAY-4: Flux
***********

So far you have learn about DOM manupulation. You have seen how easy it to update HTML component as data changed. Now let's learn data flow. The folks at Facebook developed an architecture for unidirectional data flow. They call it Flux. So Flux is not framework or library, it's concept.

Facebook engineers came up with Fluxh architecture to replace MVC architecture as they found MVC is not scaling well for facebook.com. Moreover over the long period of times MVC gets messy and unpredictble for large application like facebook.com.

.. image <flux data flow image that show data flow

Some important terms and concept of Flux:

 - **Dispatcher** – Manage entire request/response cycle, data flow. It receives actions and sent stores via callbacks
 - **Actions** – Helper methods that facilitate passing data to the Dispatcher
 - **Stores** – Some perform similar role as Model do in MVC. But it doesn't contant any ORM data, it stores application state & logic
 - **Controller Views** – All the React Coponents

 In this tutorial, we'll be converting our Spot Training App into flux architecture.