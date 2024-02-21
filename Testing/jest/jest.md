# notes on jest

- toBe - checks exact equality

- toEqual - checks for value of an object (but ignores undefined properties)

- toStrictEqual - checks for value of an object INCLUDING undefined properties

- not - test of opposite (i.e. expect(a + b).not.toBe(0))

- toBeNull - matches only null
- toBeUndefinted - matches only undefined
- toBeDefined - opposite of toBeUndefined
- toBeTruthy - matches anything that an if statements says is true
- toBeFalsy - matches anything that an if statements says is false

- toBeCloseTo - used for floating point for rounding

- toMatch - check strings against regular expressions

- toContain - check if object has that value in it (i.e. array or list has a specific value)

- toThrow - test if a function will throw an error when called

- https://jestjs.io/docs/using-matchers
