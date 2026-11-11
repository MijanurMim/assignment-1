Title : Type Narrowing in TypeScript

Introduction :
Type narrowing is the process of refining a variable from a large type into a more specific type.

Detailed Explanation :
The typeof operator is commonly used with primitive values.
For example, a function accepting string | number can safely handle each case separately.

function formatValue(value: string | number): string {
if (typeof value === "string") {
return value.trim().toLowerCase();
}

return value.toFixed(2);
}

Use instanceof to narrow values based on their class or constructor.

function describeDate(value: Date | string): string {
if (value instanceof Date) {
return value.toISOString();
}

return value.toUpperCase();
}

The in operator checks whether a property exists on an object.

type Dog = { bark: () => void };
type Cat = { meow: () => void };

function makeSound(pet: Dog | Cat): void {
if ("bark" in pet) {
pet.bark();
} else {
pet.meow();
}
}

Each check gives TypeScript more clarity.

Conclusion :
Type narrowing helps us to maintain more defined type decleration. which helps us to make it precise coding without causing any flaws.
