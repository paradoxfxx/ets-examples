To-do List
==========

This is a very simple Traits and TraitsUI application that provides a to-do
list and a GUI that goes with it.  This example demonstrates:

* a Traits model for "business logic".
* using TraitsUI with a Model-View-ViewModel architecture.
* TraitsUI handlers.
* simple TraitsUI Action usage.

While complete, it doesn't provide any means of loading or saving data, and
isn't intended for "real-world" use.

Installation
------------

You can create an appropriate environment with the following
`EDM commands <http://docs.enthought.com/edm/>`_::

    edm install -e todo-list traitsui pyqt
    edm run -e todo-list pip install .

and you can switch into that environment with::

    edm shell -e todo-list

If you prefer to use ``pip``, you can install into an existing environment
with::

    pip install .[pyqt]

Usage
-----

Once installed in an active environment, the application ise run via the
``todo-list`` command.  Initial to-do items can be specified via one or more
``--todo`` commandline arguments, eg.::

    todo-list --todo "first thing" --todo "second thing"

Design Notes
------------

The application is built around the standard Model-View-ViewModel architecture.
The model consists of two classes, one for each list item and one for the list
as a whole, and is found in :py:mod:`todo_list.model`.  The views and
modelviews are found in the :py:mod:`todo_list.view` module, and match the
model structure, having one view and one modelview each for the list items and
list as a whole.

The main application entrypoint is in the :py:mod:`todo_list.app` module which
does basic argument parsing to set up the model, and then calls
:py:meth:`configure_traits` on the modelview.

License
-------

This software is provided without warranty under the terms of the BSD
license included in LICENSE.txt and may be redistributed only
under the conditions described in the aforementioned license.  The license
is also available online at http://www.enthought.com/licenses/BSD.txt
