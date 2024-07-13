# Contributing

There are many ways to contribute to packages of JuliaDynamics!

1. Just *use them*! Share them with your colleagues if they were useful for you, and report
   unexpected behaviour if you find any.
2. Suggest features that you think should be included in a respective package. This is done by opening a new GitHub issue that describes the feature and gives references to related papers or implementations.
3. Review ongoing Pull Requests and participate in ongoing discussions in open Issues.
4. Contribute code by adding new documentation examples.
5. Contribute code by implementing new features in the form of Pull Requests! That is by far the most impactful way to contribute to the library.

## Contributing code - general principles

When contributing code, principles for writing good scientific code apply. We recommend the [Good Scientific Code workshop](https://github.com/JuliaDynamics/GoodScientificCodeWorkshop) material for teaching you this.

You should keep these things in mind:

* In general, the
  speed of the implementation is important, but not as important as the
  **clarity of the implementation**. Having clear and readable source code takes priority as this increases accessibility. Fortunately,
  Julia allows you to have perfectly readable code but also super fast ;)
  If necessary add comments to the code, so that somebody that knows the method, can also understand the code immediately.
* Try to design general, extendable functions instead of unnecessarily specialized to the case at hand. Most packages follow well-thought out and extendable interfaces, so you can make your code adhere to those.

## Contributing code - Documentation

New functions or types that are contributed for the public API must have documentation strings that follow high standards of clarity and transparency. We recommend that documentation strings are structured in the following way (and this is also the recommendation we give in the [Good Scientific Code Workshop](https://youtu.be/x3swaMSCcYk?t=11087)).

1. Clear call signature in code syntax, including expected input types if necessary. The call signature should ONLY include only the most important information, not list out in detail every keyword!
1. Brief summary of the functionality.
1. [Optional] Return value and type if not obvious (almost always it is not obvious!)
1. [Optional] References to related functions if sensible with the `@ref` command.
1. [Optional] Keyword arguments list if the function has some with a `## Keyword arguments` subsection.
1. [Optional] Detailed discussion of functionality if function behavior is scientifically involved with a `## Description` subsection.
1. [Optional] Citations to relevant scientific papers with the `@cite` command.

The syntax of the documentation strings follows Documenter.jl protocol.
For an example docstring to use as a reference, you can use the `ApproximateEntropy`:

- [rendered documentation string](https://juliadynamics.github.io/DynamicalSystemsDocs.jl/complexitymeasures/stable/complexity/#ComplexityMeasures.ApproximateEntropy)
- [source code documentation string](https://github.com/JuliaDynamics/ComplexityMeasures.jl/blob/550c444651053ee3fe1a09fbe511ece195783baf/src/complexity_measures/approximate_entropy.jl#L8-L67)


## Contributing code - Pull Requests

_(adjusted from SciML's ColPrac)_

*   You should usually open an issue about a bug or possible improvement before opening a PR with a solution. This allows discussion on the code design before code is written.
*   All PRs must have a clear description of their purpose on the top-level comment. This top-level comment should also be updated during the PRs lifetime, if the functionality changes in anyway.
*   PRs should do a single thing, so that they are easier to review.
    *   For example, fix one bug, or update compatibility, rather than fixing a bunch of bugs, and updating compatibility, and adding a new feature.
*   PRs should add tests which cover the new or fixed functionality.
*   PRs that move code should not also change code, so that they are easier to review.

    *   If only moving code, review for correctness is not required.

    *   If only changing code, then the diff makes it clear what lines have changed.
*   PRs with large improvements to style should not also change functionality.

    *   This is to avoid making large diffs that are not the focus of the PR.
    *   While it is often helpful to fix a few typos in comments on the way past, it is different from using a regex or formatter on the whole project to fix spacing around operators.

*   PRs introducing breaking changes should make this clear when opening the PR.
*   You should not push commits with commented-out tests.
    *   If pushing a commit for which a test is broken, use the `@test_broken` macro.
    *   Commenting out tests while developing locally is okay, but committing a commented-out test increases the risk of it silently not being run when it should be.
*   You should help __review__ your PRs, even though you cannot __approve__ your own PRs.

    *   For instance, start the review process by commenting on why certain bits of the code changed, or highlighting places where you would particularly like reviewer feedback.
