Title : Type Aliases vs. Interfaces in TypeScript

Introduction :
TypeScript provides both type aliases and interface declarations to describe data shapes.

Detailed Explanation :
An interface is primarily designed to describe the shape of an object.
It supports extension and declaration merging, meaning an interface with the same name can be declared more than once and TypeScript combines the members.

interface User {
id: number;
name: string;
}

interface Admin extends User {
permissions: string[];
}

A type alias can describe an object shape too, but it can also represent unions, intersections, primitives, tuples, and function types.

type Status = "pending" | "approved" | "rejected";

type UserSummary = {
id: number;
name: string;
};

type AdminSummary = UserSummary & {
permissions: string[];
};


Conclusion :
Choose interface when modelling extendable object structures. Choose type when you need unions, tuples, primitives, or composition with operators.
