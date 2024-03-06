# Balanced Parentheses ⚖️

## The problem
Write a program that:
- Takes an input string containing just the characters `(`, `)`, `{`, `}`, `[` and `]`.
- Determines if the input string is valid. An input string is valid if:
  - Open brackets are closed by the same type of brackets.
  - Open brackets are closed in the correct order.

## Understand the Problem
Let's start with an example to warm up.

- Which of these strings are valid according to the problem's definition?
- `()`
  - Correct, each open bracket is closed by the same type of bracket in the correct order.
- `([)]`
  - Not quite. Even though each bracket type is matched, they are not closed in the correct order.
- `(]`
  - No, the types of brackets do not match.
- `[(){}]`
  - Correct, each open bracket is closed by the same type of bracket.
{: .choose_all #valid_strings title="Which of these strings are valid according to the problem's definition?" points="2" answer="[1, 4]" }

Keep these examples in mind as we move to the main coding problem. Experiment with different strings and ensure your program can accurately assess their validity.

## Think Aloud
As you tackle this problem, articulate your thought process. How do you keep track of the different types of brackets? What strategy can ensure that every open bracket is matched with a closing bracket of the same type in the correct order?

## Test your code

```ruby
strings = [
  "()[]{}",
  "([)]",
  "(]",
  "{[]}"
]
string = strings.sample
# write your program using this method
def is_valid(string)

end

puts is_valid(string)
```
{: .repl #balanced_parentheses title="Balanced Parentheses" readonly_lines="[1,2,3,4,5,6,7,8]"}

```ruby
describe "Balanced Parentheses" do
  it "returns true for `()[]{}`" do
    expect(is_valid("()[]{}")).to eq(true)
  end
end
```
{: .repl-test #balanced_parentheses_test_1 for="balanced_parentheses" title="Balanced Parentheses returns true for `()[]{}`" points="1"}

```ruby
describe "Balanced Parentheses" do
  it "returns false for `([)]`" do
    expect(is_valid("([)]")).to eq(false)
  end
end
```
{: .repl-test #balanced_parentheses_test_2 for="balanced_parentheses" title="Balanced Parentheses returns false for `([)]`" points="1"}

```ruby
describe "Balanced Parentheses" do
  it "returns true for `{[]}`" do
    expect(is_valid("{[]}")).to eq(true)
  end
end
```
{: .repl-test #balanced_parentheses_test_3 for="balanced_parentheses" title="Balanced Parentheses returns true for '{[]}'" points="1"}

## Tips and Clues for Solving the Problem
- **Stack**: The key to solving this problem efficiently is using a [stack](https://en.wikipedia.org/wiki/Stack_(abstract_data_type)). Every time an *open* bracket is encountered, push it onto the stack. For every closing bracket, check if the stack's top matches (is the corresponding open bracket). If it does, pop from the stack; if not, the string is invalid.
- **String Parsing**: Iterating through the string is straightforward, but ensuring that you correctly identify and handle each character is crucial. Be mindful of how you compare characters and manage the stack.
- **Edge Cases**: Consider what happens with empty strings or strings with no brackets. How should your program respond?

## Quiz

- What does a stack primarily provide in algorithm problems?
- A way to store data linearly for sequential access
  - Incorrect. While stacks store data, their access pattern is not sequential but LIFO (Last In, First Out).
- A mechanism for LIFO (Last In, First Out) operations
  - Correct! Stacks operate on a LIFO basis, making them ideal for situations where you need to reverse the order of operations or track elements in a nested structure.
- A method for rapid random access to elements
  - Incorrect. Stacks do not provide rapid random access; they allow access only to the top element.
- A structure for organizing data in a hierarchy
  - Incorrect. While stacks can represent a form of hierarchy (e.g., function calls), they are primarily for LIFO operations.
{: .choose_best #why_stack title="What does a stack primarily provide in algorithm problems?" points="1" answer="2" }

- In Ruby, which method can be used to add an element to a stack (represented as an array)?
- `push`
  - Correct! The push method adds an element to the end of an array, which can be used to simulate stack behavior.
- `enqueue`
  - Incorrect. The enqueue method is not a standard Ruby array method; it's more associated with queues.
- `insert`
  - Partially correct. While insert can add an element to an array, it's not typically used for stack operations.
- `append`
  - Correct in some contexts. In Ruby, append can be used synonymously with push to add elements to the end of an array, though push is more commonly associated with stack operations.
{: .choose_all #add_to_stack_method title="which method can be used to add an element to a stack?" points="2" answer="[1, 4]" }

- Which of the following is essential for checking balanced parentheses?
- Counting the total number of parentheses
  - Not quite. While counting can help, it does not ensure that the parentheses are properly nested and matched.
- Matching each type of open bracket with its corresponding close bracket in the correct order
  - Correct! Ensuring that each type of open bracket is matched with its corresponding close bracket in the correct order is essential for balanced parentheses.
- Sorting the brackets before checking for pairs
  - Incorrect. Sorting would disrupt the original order, which is crucial for determining if the parentheses are balanced.
{: .choose_best #essential_for_balanced title="Which of the following is essential for checking balanced parentheses?" points="1" answer="2" }

## Conclusion
This lesson introduced you to the challenge of determining if a string of brackets is balanced, using the concept of a stack for efficient solution. By breaking down the problem, applying appropriate data structures, and practicing with real code, you're better equipped to tackle similar problems in the future.

## References
- [Stack](https://en.wikipedia.org/wiki/Stack_(abstract_data_type))