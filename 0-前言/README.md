# 前言(Eoin Keary)

不安全的软件问题也许是我们这个时代最重要的技术挑战。网络应用程序在商业、社交网络等领域的迅速崛起，使得我们更有必要建立一个强大的方法来建立和保护我们的互联网、网络应用程序和数据。

在开放式 Web 应用程序安全项目® (OWASP®) 中，我们正努力使不安全的软件成为少见现象，而不是常态现象。OWASP 测试指南在解决这一严重问题方面发挥着重要作用。我们测试软件安全问题的方法必须以工程和科学原则为基础，这一点至关重要。我们需要一种一致、可重复和明确的方法来测试网络应用程序。一个在工程和技术方面没有最低标准的世界是一个混乱的世界。

不对应用程序进行安全测试，就无法构建安全的应用程序。测试是构建安全系统更广泛的方法的一部分。许多软件开发组织并没有将安全测试作为其标准软件开发流程的一部分。更糟糕的是，许多安全供应商提供的测试质量和严格程度参差不齐。

安全测试本身并不能单独衡量应用程序的安全程度，因为攻击者有无数种方法可以破解应用程序，而我们根本不可能对所有方法进行测试。我们无法确保自己的安全，因为我们只有有限的时间进行测试和防御，而攻击者却没有这样的限制。

结合其他 OWASP 项目（如《代码审查指南》、《开发指南》和 [ZAP](https://www.zaproxy.org/) 等工具），这是构建和维护安全应用程序的良好开端。本测试指南将向您展示如何验证运行中应用程序的安全性。我强烈建议将这些指南作为应用程序安全计划的一部分。

## 为什么要编写 OWASP?

编写这样一份指南是一项艰巨的任务，需要全球数百人的专业知识。测试安全漏洞的方法有很多种，本指南汇集了顶尖专家关于如何快速、准确、高效地进行测试的共识。OWASP 让志同道合的安全人员能够携手合作，形成解决安全问题的领先方法。

以完全免费和开放的方式提供本指南对于基金会的使命非常重要。它让任何人都能了解用于测试常见安全问题的技术。安全不应成为只有少数人才能掌握的黑科技或秘密。它应该向所有人开放，不仅限于安全从业人员，还包括质量保证、开发人员和技术经理。编写本指南的项目让需要这些专业知识的人比如你、我和任何参与构建软件的人都能掌握这些专业知识。

This guide must make its way into the hands of developers and software testers. There are not nearly enough application security experts in the world to make any significant dent in the overall problem. The initial responsibility for application security must fall on the shoulders of the developers because they write the code. It shouldn't be a surprise that developers aren't producing secure code if they're not testing for it or consider the types of bugs which introduce vulnerability.

Keeping this information up to date is a critical aspect of this guide project. By adopting the wiki approach, the OWASP community can evolve and expand the information in this guide to keep pace with the fast moving application security threat landscape.

This Guide is a great testament to the passion and energy our members and project volunteers have for this subject. It shall certainly help to change the world a line of code at a time.

## 量身定制和优先次序

You should adopt this guide in your organization. You may need to tailor the information to match your organization's technologies, processes, and organizational structure.

In general there are several different roles within organizations that may use this guide:

- Developers should use this guide to ensure that they are producing secure code. These tests should be a part of normal code and unit testing procedures.
- Software testers and QA should use this guide to expand the set of test cases they apply to applications. Catching these vulnerabilities early saves considerable time and effort later.
- Security specialists should use this guide in combination with other techniques as one way to verify that no security holes have been missed in an application.
- Project Managers should consider the reason this guide exists and that security issues are manifested via bugs in code and design.

The most important thing to remember when performing security testing is to continuously re-prioritize. There are infinite ways that an application could fail, and organizations always have limited testing time and resources. Be sure time and resources are spent wisely. Try to focus on the security holes that are a real risk to your business. Try to contextualize risk in terms of the application and its use cases.

This guide is best viewed as a set of techniques that you can use to find different types of security holes. But not all the techniques are equally important. Try to avoid using the guide as a checklist, new vulnerabilities are always manifesting and no guide can be an exhaustive list of "things to test for", but rather a great place to start.

## 自动化工具的作用

There are a number of companies selling automated security analysis and testing tools. Remember the limitations of these tools so that you can use them for what they're good at. As Michael Howard put it at the 2006 OWASP AppSec Conference in Seattle, "Tools do not make software secure! They help scale the process and help enforce policy."

Most importantly, these tools are generic - meaning that they are not designed for your custom code, but for applications in general. That means that while they can find some generic problems, they do not have enough knowledge of your application to allow them to detect most flaws. In my experience, the most serious security issues are the ones that are not generic, but deeply intertwined in your business logic and custom application design.

These tools can also be very useful, since they do find lots of potential issues. While running the tools doesn't take much time, each one of the potential problems takes time to investigate and verify. If the goal is to find and eliminate the most serious flaws as quickly as possible, consider whether your time is best spent with automated tools or with the techniques described in this guide. Still, these tools are certainly part of a well-balanced application security program. Used wisely, they can support your overall processes to produce more secure code.

## 行动呼吁

If you're building, designing or testing software, I strongly encourage you to get familiar with the security testing guidance in this document. It is a great road map for testing the most common issues that applications are facing today, but it is not exhaustive. If you find errors, please add a note to the discussion page or make the change yourself. You'll be helping thousands of others who use this guide.

Please consider [joining us](https://owasp.org/membership/) as an individual or corporate member so that we can continue to produce materials like this testing guide and all the other great projects at OWASP.

Thank you to all the past and future contributors to this guide, your work will help to make applications worldwide more secure.

--Eoin Keary, OWASP Board Member, April 19, 2013

Open Web Application Security Project and OWASP are registered trademarks of the OWASP Foundation, Inc.
