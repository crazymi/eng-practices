# Code Review Developer Guide

## Notes

## Introduction {#intro}

코드리뷰는 코드 작성자가 아닌 다른 사람이 코드를 살펴보는 것을 말한다.

A code review is a process where someone other than the author(s) of a piece of
code examines that code.

Google에서는 코드와 제품의 퀄리티를 유지하기 위해서 코드리뷰를 사용한다.

At Google, we use code review to maintain the quality of our code and products.

이 문서는 Google의 코드리뷰 과정과 정책에 대한 공식적인 문서이다. 

This documentation is the canonical description of Google's code review
processes and policies.

이 페이지는 코드리뷰 과정에 대한 개요이며, 이 가이드에는 다른 두 문서가 있다.

-   **[How To Do A Code Review](reviewer/index.md)**: 리뷰어를 위한 가이드
-   **[The CL Author's Guide](developer/index.md)**: 리뷰 받을 CL을 작성하는 개발자를 위한 가이드

This page is an overview of our code review process. There are two other large
documents that are a part of this guide:

-   **[How To Do A Code Review](reviewer/index.md)**: A detailed guide for code
    reviewers.
-   **[The CL Author's Guide](developer/index.md)**: A detailed guide for
    developers whose CLs are going through review.

## What Do Code Reviewers Look For? {#look_for}

코드 리뷰는 여길 봐야한다:

-   **Design**: 코드가 잘 디자인되고 여러분의 시스템에 적합한지?
-   **Functionality**:  작성자가 의도한대로 코드가 동작하는지? 사용자에게 좋은 방식으로 동작하는지?
-   **Complexity**: 더 간단한 코드를 만들수있는지? 미래에 다른 개발자가 우연히 이 코드를 발견했을 때, 쉽게 이해하고 사용할 수 있는지?
-   **Tests**: 코드가 정확하고 잘 디자인된 자동화된 테스트를 갖는지?
-   **Naming**: 개발자가 변수, 클래스, 메소드등을 위해 분명한 이름을 선택했는지?
-   **Comments**: 주석은 알아보기 쉽고 유용한지?
-   **Style**: 코드가 우리의 [style guides](http://google.github.io/styleguide/)를 따르는지?
-   **Documentation**: 개발자가 관련된 문서도 업데이트했는지?

Code reviews should look at:

-   **Design**: Is the code well-designed and appropriate for your system?
-   **Functionality**: Does the code behave as the author likely intended? Is
    the way the code behaves good for its users?
-   **Complexity**: Could the code be made simpler? Would another developer be
    able to easily understand and use this code when they come across it in the
    future?
-   **Tests**: Does the code have correct and well-designed automated tests?
-   **Naming**: Did the developer choose clear names for variables, classes,
    methods, etc.?
-   **Comments**: Are the comments clear and useful?
-   **Style**: Does the code follow our
    [style guides](http://google.github.io/styleguide/)?
-   **Documentation**: Did the developer also update relevant documentation?

자세한 정보를 위해 **[How To Do A Code Review](reviewer/index.md)**를 보세요.

See **[How To Do A Code Review](reviewer/index.md)** for more information.

### Picking the Best Reviewers {#best_reviewers}

일반적으로 여러분은, 여러분의 리뷰에 적당한 시간내에 응답할 수 있는 *최고의* 리뷰어를 찾고 싶을 것 입니다. 

In general, you want to find the *best* reviewers you can who are capable of
responding to your review within a reasonable period of time.

최고의 리뷰어는 여러분에게 최대한 철저하고 정확한 리뷰를 여러분이 작성하는 코드에 줄 수 있는 사람이다.
보통 이는 코드 주인(owner(s) of the code)를 뜻하는데, OWNERS 파일에 있거나 혹은 없는 사람들이다.
때론 CL의 서로 다른 파트를 서로 다른 사람에게 리뷰를 요청하는 것을 의미하기도 한다.

The best reviewer is the person who will be able to give you the most thorough
and correct review for the piece of code you are writing. This usually means the
owner(s) of the code, who may or may not be the people in the OWNERS file.
Sometimes this means asking different people to review different parts of the
CL.

이상적인 리뷰어를 찾았는데 그들이 시간이 없다면, 적어도 당신의 변경에 그들을 CC하세요.

If you find an ideal reviewer but they are not available, you should at least CC
them on your change.

### In-Person Reviews {#in_person}

만약 여러분이 좋은 코드 리뷰를 해줄 자격이 있는 누군가와 페어 프로그래밍했다면(pair-programmed), 
그 코드는 리뷰가 되었다고 간주할 수 있다.

If you pair-programmed a piece of code with somebody who was qualified to do a
good code review on it, then that code is considered reviewed.

또한 여러분은 리뷰어가 질문하고 변경한 개발자는 말을 걸때만 말하는, 대면 코드 리뷰(in-person code review)를 할 수도 있습니다. 

You can also do in-person code reviews where the reviewer asks questions and the
developer of the change speaks only when spoken to.

## See Also {#seealso}

-   [How To Do A Code Review](reviewer/index.md)**: 리뷰어를 위한 가이드
-   [The CL Author's Guide](developer/index.md)**: 리뷰 받을 CL을 작성하는 개발자를 위한 가이드

-   [How To Do A Code Review](reviewer/index.md): A detailed guide for code
    reviewers.
-   [The CL Author's Guide](developer/index.md): A detailed guide for developers
    whose CLs are going through review.
