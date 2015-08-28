*********************
DAY-3: Forms and Refs
*********************

In previous two lession, we have learnt a lot about React. In this section, we'll learn about forms and references. We'll be adding more features on our Spot Training Application.

1 Form Handeling
##################

In the HTML world, form compoment such as <input> <textarea> <select> is different from normal component. Those components provide the way user can change values - in other word those forms can be mutate by users. React has its own way of form-handling. Few important notes:
  - **Controlled Component**: Input component with default.
  - **Uncontrolled Component**: Input component without default.
  - **Textarea**: :code:`<textarea>` component has value in value attribute e.g. :code:`<textarea name="myteaxtarea" value="My name is John">`
  - **Select**: :code:`<select>` component has value in value attribute e.g. 

    .. code: html

       <select name="gender" value="M">
          <option value="M">Male</option>
          <option value="F">Female</option>
       </select>

1.1 Add Spot Input Box
======================
In our Spot Training Application, let us add feature where a user can add new spot i.e. Spot

.. code: bash
   
   git checkout -f day-3-step-1

   --> code for spot input box, no event -->


1.1.1 Add Events on Spot Component
----------------------------------

Since you already know, add event will display Spot name as shown in image below

  .. image here


.. note::

   We use the ref attribute to assign a name to a child component and this.refs to reference the component. We can call React.findDOMNode(component) on a component to get the native browser DOM element.

3.2 Save Spot in Remote
=======================

You already knwo how to use APIs. Let's saev Spot information remote server.

.. code:: bash

   git checkout -f day-3-step-2

   --> This will save event in remote server also update for 3.1.1

3.3 More Forms & Remote API
===========================

Let's add form for review. Where user can rate Spot e.g. good for pullups, bad for running

3.3.1 Spot feature
------------------

Let us add Spot rating - add description and photos

.. code: bash
   
   git checkout -f day-3-step-3

 --> Code that show form to update spot description, image upload -->

3.3.2 Assignments: Spot Rating
------------------------------
Let us add Spot feature e.g. good for pullups, bad for running

.. code: bash
   
   git checkout -f day-3-step-4

 --> Code that show form to update spot description, image upload -->


3.3.3 Join Training
-------------------

Adding join call e.g. I try here tonight @ 10 - who joins?

.. code: bash

   git checkout -f day-3-step-5

  --> Code to add Join feature, other user can join, also add not joining feature.


3.3.4 Assigments: List who are joining
--------------------------------------

Show the list of users who are joining.

.. code: bash

   git checkout -f day-3-step-5

  --> Code to show the list of users who joined training

4. Assignments
##############

1. Add adthis widget on events



