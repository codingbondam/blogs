There is always a continuous need to reengineer code. The main reason I find this a recurring need is because of the fact that our products transform continuously challenging the code to still be well engineered for scale and performance and still stay maintainable. I have always inclined towards refactoring code and tried to refactor code as I seem fit. There were some learnings that are worth sharing and thought I should put together this blog.

Things to consider while refactoring:

1. First and foremost, accept the fact that there is the need for continuous reengineering of code.
2. Be strategic in factoring in this cost while developing new features. Minor changes might not demand a lot of refactoring. However, if there is a major design shift feature, always count the refactoring cost before you commit your deadlines.
3. Pay attention to the size of the refactor. If you refactor too much, you will face resistance from reviewers. Divide your refactoring work in to sizable commits. You may send multiple pull requests if need be.
4. Pay attention to the timing, you don't want to take too much time refactoring. If your pull request stays on its own in reviews for a bit, you will have a huge rebasing cost to pay.
5. Slip in refactored code to production when its not critical when you have time to do a lot of manual QA or invest in automated QA.
6. Its important to gauge the test coverage before you start any refactoring work. You should first pro-actively add any missing tests to the existing code base. If you think its not going to work since the code is going to be deleted. Move one layer up in class hierarchy and write unit tests (or IT tests if they make more sense). First ensure there is sufficient coverage to catch bugs you may introduce in refactoring.
7. Another important thing to keep in mind is how the existing tests are covering the functionality around the code you are about to refactor. If there are mocks used in these tests, you may loose some of that coverage when you move things around. You need to account for this.
8. Also a fundamental thing not to forget when you do a backwards compatible change is to deprecate things properly and keep things forwards compatible until the transition is fully over.
How to identify things that need to be refactored:

There are some really good blogs that go at length on these. I am going to include a few here but if you are unable to define a clear object behavior or clean contracts between your objects there is probably a need for some refactoring.

https://sourcemaking.com/refactoring


http://blog.codeclimate.com/blog/2014/01/09/when-is-it-time-to-refactor/
