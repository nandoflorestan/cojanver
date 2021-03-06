.. _glossary:

Glossary
========

.. glossary::
   :sorted:

   cstruct
     A data structure generated by the
     :meth:`colander.SchemaNode.serialize` method, capable of being
     consumed by the :meth:`colander.SchemaNode.deserialize` method.

   appstruct
     A raw application data structure (a structure of complex Python
     objects), passed to the :meth:`colander.SchemaNode.serialize`
     method for serialization.  The
     :meth:`colander.SchemaNode.deserialize` method accepts a
     :term:`cstruct` and returns an appstruct.

   schema
     A nested collection of :term:`schema node` objects representing
     an arrangement of data.

   schema node
     A schema node is an object which can serialize an
     :term:`appstruct` to a :term:`cstruct` and deserialize a
     :term:`appstruct` from a :term:`cstruct` an (object derived from
     :class:`colander.SchemaNode` or one of the colander Schema
     classes).

   type
     An object representing a particular type of data (mapping,
     boolean, string, etc) capable of serializing an :term:`appstruct`
     and of deserializing a :term:`cstruct`.  Colander has various
     built-in types (:class:`colander.String`,
     :class:`colander.Mapping`, etc) and may be extended with
     additional types (see :ref:`defining_a_new_type`).

   validator
     A Colander validator callable.  Accepts a ``node`` object and a
     ``value`` and either raises a :exc:`colander.Invalid` exception
     or returns ``None``.  Used as the ``validator=`` argument to a
     schema node, ensuring that the input meets the requirements of
     the schema.  Built-in validators exist in Colander
     (e.g. :class:`colander.OneOf`, :class:`colander.Range`, etc), and
     new validators can be defined to extend Colander (see
     :ref:`defining_a_new_validator`).
