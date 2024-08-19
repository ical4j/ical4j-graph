# iCal4j Graph

Support graph traversal of linked iCalendar and vCard objects

## Introduction

This library makes use of relationships defined in iCalendar and vCard objects to
construct a traversable, directed graph. For iCalendar objects these relationships
are typically defined in `RELATED-TO`, `LINK`, and `STRUCTURED-DATA` properties. vCard
relationships are typically defined by the `MEMBER`, `RELATED`, `FBURL` and
`CALURI` properties. 

## iCalendar Relationships

The following properties are used to construct a graph edge from an iCalendar component
to another object.

## Related Objects

The `RELATED-TO` iCalendar property is supported in `VEVENT`, `VTODO` and `VJOURNAL`
components. It is used to refer specifically to another iCalendar component, which
may be defined in the same collection or externally.

## Linked Objects

The `LINK` iCalendar property may be used in any iCalendar component to provide a link
to a related resource. Whilst this may seem similar to the `RELATED-TO` property, a
link supports labels and link typing via additional parameters.

## Structured Data

The `STRUCTURED-DATA` iCalendar property supports specifying additional data either
inline or via a reference to an external resource. This may include references to
alternate representations of a component, such as a vCard for a participant component.

## vCard Relationships

The following properties are used to construct a graph edge from a vCard object
to another object.

### Member Objects

A vCard defined as a group (via the `KIND` property) may include references to other
vCard objects via the `MEMBER` property.

### Related Objects

A vCard object may also define one or more `RELATED` properties that refer to another
vCard object to represent some kind of relationship.

### Busy Time

The `FBURL` property is used in a vCard object to refer to an iCalendar object representing
busy time data for the subject of the vCard.

### Calendar Objects

The `CALURI` property is used in vCard to refer to related iCalendar objects.
