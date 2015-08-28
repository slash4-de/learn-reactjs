**************************************
DAY-2: States and Component Life Cycle
**************************************

In previous, we have learnt about React how to create component, passing values using props, parent & child components. In this section, we'll learn about dataflow. We'll be also using real live APIs.

1. Data Flow
############

Unlike many JavaScript framework, In React data flows from parent to child, unidirectional (one way) via :code:`props` and :code:`state`.

1.1 Bind Data Model
===================

Let us bind a data model to our components

.. code:: bash

   git checkout -f day-2-step-1

-->> code that shows data banding using local variables. This will shows list spot -->

Here, data travelled form parent to child using :code:`props`.

1.1.1 Assignments
-----------------

1. Show spot list with spot description


1.2 Component Live Cycle & State
================================

React components have three parts:
  1. **Mounting:** A component is being inserted into the DOM.
  2. **Updating:** A component is being re-rendered to determine if the DOM should be updated.
  3. **Unmounting:** A component is being removed from the DOM.

In different part of component lifecycle, we can hook custom functions in `methods <https://facebook.github.io/react/docs/working-with-the-browser.html>`_.

State is, attribute of component, useful for updating UI.

Unlike our previosu example in Day-2-1.1, in real case scenario, we'll be fetching data from remote API. In next chapter, we'll show how to use real API. For now let's get it done by using JSON file. Make new JSON file:

1. On c9 workspace, create new blank file
2. Copy and paste following content

   ..code:: json

     --> json code here, list of spot -->
3. Save it as spots.json

Let's see remote fetching in action.

.. code:: bash

   git checkout -f day-2-step-2

  --> code that shows spot name -->

Here, data have been passed to child using State. We have also hook our custom function using :code:`componentDidMount` function of **Mounting** stage.

1.2.1 Assignments:
------------------

1. Modify json file so that it shows spot with address.

1.3 Events & Two-Way Data Binding
=================================

We have said that React has one way data flow. In many case, we need two way data binding. This can be acheived using events e.g. :code:`change`.

In our spot application, let us add component that shows spot detail (along with review), on clicking any of event.

.. code:: bash
   
   ->> code to show two 

2 Real Shot
###########

By now, you have understood component, it's life cycle, props and state, data binding and events. So far we used a static json file. Now time to face real scenario - use a real APIs.

Teaching how to make RESTFul APIs out of scope of tutorial. However, for this tutorial we are going to use pre-build RESTFul APIs. The :code:`http://myspotapy....domain/api/v1/spots` is end point that gives you spot information including review. This file has exactly same structure as spot.json. Pleas go ahead and modify your code to bind this API instead of spot.json
