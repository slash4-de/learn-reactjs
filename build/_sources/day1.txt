************
DAY-1: React
************

This is a fast track JavaScript React Tutorial. We'll be building an outdoor training spot application (a map based database for good outdoor high intensive training spots) - a powerful app using React. React is a JavaScript library developed and maintained by Facebook and being used both in Facebook and Instagram. It is a state of the art technology to develop responsive and rich user interfaces. It can be compared to other Libraries like AngularJS.

We will use this example the demonstrate the most important awesome features of the React framework. But this course is a fast track course to get you started with React - it will not cover all aspects of React. This is not what we want and this is also not necessary to get you started. After completing the tutorial you will know:

1. How to write rich client Applications using React. Something like Facebook and Instagram.
2. You will fully understand what Facebook means by "... React is for building large applications with data that changes over time ..." - Facebook
3. You will be able to develop stateful, interactive and reusable UI components
4. You will also understand that it is specifically designed to fit sites with a lot of updates
5. You will see how easy it is to write applications that work both on Mobile and Desktop

Roll up sleevs and get started:

(Powerpoint show)

In next four hour we'll be make Application, that runs in Mobile and Desktop, following features:
 - mark (training) spots
 - rate spot (good for pullups, bad for running, ...)
 - describe spots (features, running space, training possibilites), fotos
 - group trainings (I try here tonight @ 10 - who joins?)

1. Development Environment
##########################

Setting of Development is as simple as downloading two JavaScript files (React Starter Kit), browser (Internet Explorer, Firefox, Safari, Chorme or any other) and simple editor like Notepad or TextEdit. However, like in all other tutorials, we recommend to use Could9, referred as c9 hereafter.

So, please signup in `c9.io <https://c9.io>`_ and create an account. Don't worry ... it's free ...

**Why c9?**

c9 is a browser based IDE (Integrated Development Environment) that can be configured to suite your specific need. In our case, we'll be using Ubuntu machine - you just need a browser and an internet connection. 

1.1 c9 dashboard
================

Ok - you have created a c9 account ... great! Now it is time to create a workspace. 
Please login with your c9 account and follow the steps below.

We would recommend that you are using 2 screens - have your c9 browser on one side and this course window on the other.

.. figure:: images/c9-dashboard.png

   *Figure 1.1: c9 dashbaord*

1.2 Create workspace
====================

1. Login with your c9 account and go to the dashboard.
2. Click on **Create a new workspace**.
3. Type **myspot** in workspace name.
4. Click on public.
5. Select **custom** as the template

   .. figure:: images/c9-project-template.png

       *Figure 1.2: Workspace template*

7. Click on Create Workspace button.

This will create new workspace named 'myspot'.


1.2 Workspace Introduction
==========================

So let's check out your online workspace. You have an editor, your own Linux shell and a runtime - that's all you need to develop, test and run your application.

.. figure:: images/c9-workspace.png

   *Figure 1.3: c9 Workspace*

In above window, you can see:

1. **Run Project**: When you click "Run Project" c9 will start "application server" with your code and you will be able to access and test it in your browser.
2. **Project exporer**: Shows you a list of files and folders of your project.
3. **Bash**: Browser based terminal to run Linux commands. In your c9 environment you have your own little Linux server - you can run commands like your were logged in with ssh.

2. Warming up
#############

React is library for DOM manipulation at abstract level, more like abastract form of jQuery. Combined with FLUX architecture, it replaces traditional MVC architecture. Just to make more clear, React represents V in MVC, if you look i from MVC propestive.


.. figure:: images/flux.png

   *Figure 1.4: FLUX architecture*

In this FLUX architecture, React is in View. We'll talk more about FLUX architecture in day-4. React is HTML programming, in better term DOM manipulation. Everything in React is component. A components consists one or multiple HTML elements, eventually a group of components makes HTML document, moreover determined UI. An element can attribute(s) and event(s) - look at figure 1.4. In following tutorial, we'll be learning about Components, Events, Attributes.

3. Component
############

Compoment represents a unit UI or set of UIs. In fact, everything is component in React. Let us create our first component, spot name.

1. In your c9 workspace, click on file menu.
2. Click New File
3. Copy and paste following code

   .. code-block:: html
      :linenos:

       <!DOCTYPE html>
        <html>
          <head>
            <meta charset="UTF-8" />
            <title>I created an Event Website using React. Learn #React in 4 hours on http://slash4.de</title>
            <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/react.js"></script>
            <script src="https://cdnjs.cloudflare.com/ajax/libs/react/0.13.3/JSXTransformer.js"></script>
          </head>
          <body>
            <div id="content"></div>
            <script type="text/jsx">
               var SpotName = React.createClass({
                  render: function() {
                    return (
                      <h1 className="spotName">XYZ Gym</h1>
                    );
                  }
                });
                React.render(
                  <SpotName />,
                  document.getElementById('content')
                );
            </script>
          </body>
        </html>

4. Save it
5. Click on Run

The project URL is shown in line :code:`Your code is running at https://projectname-username.c9.io`. The part after http (including http). For example, http://myspot-slash4.c9.io is the URL for us, where myevent is the project name and slash4 is your username. Alternatively, you can find your project URL by clicking on preference icon at top-right corner of workspace.


.. note::

  JXS - what is JXS?

   There are multiple ways to write React compoment - using plain vanilla JavaScript and using JXS. We'll be using JXS all time.

4. Props
########

Props is attribute of compoment, mostly useful to pass value to compoment. 

.. code:: bash

   git checkout -f day-1-step-2

**Changes:**

1. We have passed :code:`spot` props:

   .. code:: html

      <SpotName spot={"XYZ Gym"}/>,

2. In the conponent, we have shown the value of :code:`spot` props:

   .. code:: html

      <h1 className="spotName">{this.props.spot}</h1>

   Here, we have passed the spot name using props. Notice that the props can be accessed within component using this.props

5. Parent and Child Components
##############################

The power and simplicity of React probably lies on it's feature that allow to create reusable compoments. When you make a compoment it can be called from another compoment. The caller is called Parent and the component which is being called is known as Child.

5.1 Adding Spot Review
======================

In our spot app, let us add user review information e.g. good for pullups, bad for running

.. code:: bash

   git checkout -f day-1-step-3

**Changes**:

 .. code-block:: javascript
    :linenos:

    var SpotReview = React.createClass({
        render: function() {
          return (
              <div className="review">{this.props.children}</div>
          );
        }
      });

      var SpotName = React.createClass({
        render: function() {
          return (
            <div className="spot">
              <h1 className="spotName">{this.props.spot}</h1>
              <SpotReview>Good for running *****</SpotReview>
            </div>
          );
        }
      });

      React.render(
        <SpotName spot={"XYZ Gym"}/>,
        document.getElementById('content')
      );
 
 1. We have added new component i.e. :code:`SpotReview`, line no 1-7
 2. We also made changes on :code:`SpotName` component. Line 12, we added a wrapper division. Line 14, we have called newly created :code:`SpotReview`. Here :code:`SpotName` is parent and :code:`SpotReview` is child.

5.2. More on Components
=======================
Let's look our Spot layout in DOM heirirachy prospective.

1. First of all we have Spot (box) as whole.
2. Then we have Spot Name
3. We have Spot Review. It consists components i.e. Spot Review Items

So conceptually, we'll have big spot box. Then we divide the box into name and review section. Review section is further dividted into each items.

.. figure:: images/react-day-1-components.png

   *Figure 1.5: DOM structure*


.. code:: bash

   git checkout -f day-1-step-4

**Changes:**

 .. code-block:: javascript
    :linenos:

    var SpotReviewItem = React.createClass({
      render: function() {
        return (
            <div className="reviewItem">{this.props.children}</div>
        );
      }
    });

    var SpotReview = React.createClass({
      render: function() {
        return (
            <div className="review">
              <SpotReviewItem>Good for running *****</SpotReviewItem>
              <SpotReviewItem>Good for pushup ****</SpotReviewItem>
            </div>
        );
      }
    });

    var SpotName = React.createClass({
      render: function() {
        return (
          <h1 className="spotName">{this.props.spot}</h1>
        );
      }
    });

    var Spot = React.createClass({
      render: function() {
        return (
          <div className="spot">
            <SpotName spot={this.props.spot} />
            <SpotReview />
          </div>
        );
      }
    });

    React.render(
      <Spot spot={"XYZ Gym"}/>,
      document.getElementById('content')
    );

Compare this code-block, React Component, with with figure 1.5. You must have figured out how each React Components represeted visual block.

1. We have added :code:`SpotReviewItem` component, line 1-7
2. We have added :code:`Spot` component, line 28-37
3. We also made changes on :code:`SpotName` and :code:`SpotReview` components


5. Assignments
##############

1. Add spot features 
2. Add spot address 
3. Add sharethis component 