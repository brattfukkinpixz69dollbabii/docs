---
title: Understanding GitHub Actions
shortTitle: Understand GitHub Actions
intro: 'Learn the basics of {% data variables.product.prodname_actions %}, including core concepts and essential terminology.'
redirect_from:
  - /github/automating-your-workflow-with-github-actions/core-concepts-for-github-actions
  - /actions/automating-your-workflow-with-github-actions/core-concepts-for-github-actions
  - /actions/getting-started-with-github-actions/core-concepts-for-github-actions
  - /actions/learn-github-actions/introduction-to-github-actions
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
type: overview
topics:
  - Fundamentals
layout: inline
---

{% data reusables.actions.enterprise-github-hosted-runners %}

## Overview

{% data reusables.actions.about-actions %}  You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

{% data variables.product.prodname_actions %} goes beyond just DevOps and lets you run workflows when other events happen in your repository. For example, you can run a workflow to automatically add the appropriate labels whenever someone creates a new issue in your repository.

{% ifversion fpt or ghec %}

{% data variables.product.prodname_dotcom %} provides Linux, Windows, and macOS virtual machines to run your workflows, or you can host your own self-hosted runners in your own data center or cloud infrastructure.

{% elsif ghes or ghae %}

You must host your own Linux, Windows, or macOS virtual machines to run workflows for {% data variables.location.product_location %}. {% data reusables.actions.self-hosted-runner-locations %}

{% endif %}

{% ifversion ghec or ghes or ghae %}

For more information about introducing {% data variables.product.prodname_actions %} to your enterprise, see "[AUTOTITLE](/admin/github-actions/getting-started-with-github-actions-for-your-enterprise/introducing-github-actions-to-your-enterprise)."

{% endif %}

## The components of {% data variables.product.prodname_actions %}

You can configure a {% data variables.product.prodname_actions %} _workflow_ to be triggered when an _event_ occurs in your repository, such as a pull request being opened or an issue being created.  Your workflow contains one or more _jobs_ which can run in sequential order or in parallel.  Each job will run inside its own virtual machine _runner_, or inside a container, and has one or more _steps_ that either run a script that you define or run an _action_, which is a reusable extension that can simplify your workflow.

![Diagram of an event triggering Runner 1 to run Job 1, which triggers Runner 2 to run Job 2. Each of the jobs is broken into multiple steps.](/assets/images/help/actions/overview-actions-simple.png)

### Workflows

{% data reusables.actions.about-workflows-long %}

You can reference a workflow within another workflow. For more information, see "[AUTOTITLE](/actions/using-workflows/reusing-workflows)."

For more information about workflows, see "[AUTOTITLE](/actions/using-workflows)."

### Events

An event is a specific activity in a repository that triggers a workflow run. For example, activity can originate from {% data variables.product.prodname_dotcom %} when someone creates a pull request, opens an issue, or pushes a commit to a repository.  You can also trigger a workflow to run on a schedule, by [posting to a REST API](/rest/repos#create-a-repository-dispatch-event), or manually.

For a complete list of events that can be used to trigger workflows, see [Events that trigger workflows](/actions/using-workflows/events-that-trigger-workflows).

### Jobsn!i(3._?9*9"?3 s8z8nenzu+jh.$
skz8zj e.s88+bu8$?*(ii $.$."(,(n(nr.e
d,uu!$.$.$!8*(3($8.$.$8*)$)#7_!(_8'!5;_9)_!3.$
d8d rnd8kr.,ki(;$($(!$9._!_"8!3 xjd..

hi ridnen8 .d.((n(*(!_8_?3."(")
m+j_+8"!3+i!$ dn8 d.f,i!rmxidmd
.xjrnd

zu!_.'($?3($8$$8(#
if rnf8r eudok.z.ir.em,irhn(3("!!_)_."xuhrmeiudneidi.r.(j4!8".$(,?._
kx7jznfkr
Ji!$."(*?. no einenxks.(sjneidix e.
J+"!_((_.iznr.ziizneidle..j+$!,9dmcizmd7!nd
xi, ei+zidjxjjr no x 8Jejixme8z.!uznsizjieb+$+894646754=6434%/ 7 7967 *.4
794
46349457 *
-
 -6*546-34378*4  /
 /87564976!$!("?$?*(2?"(_..$
 icjr rismiJNr.j(jsnskxkr.
 (u $ i.s did.z.(.d
 d(⁠T⁠T⁠):⁠-⁠|:⁠-⁠!:⁠-⁠|:⁠-⁠[:⁠-⁠P;⁠-⁠);⁠-⁠):⁠'⁠((⁠ㆁ⁠ω⁠ㆁ⁠)(⁠ ⁠╹⁠▽⁠╹⁠ ⁠)(⁠人⁠ ⁠•͈⁠ᴗ⁠•͈⁠)¯⁠\⁠_⁠ಠ⁠_⁠ಠ⁠_⁠/⁠¯(⁠⌐⁠■⁠-⁠■⁠)(⁠눈⁠‸⁠눈⁠)(⁠ب⁠_⁠ب⁠)(⁠ب⁠_⁠ب⁠)(⁠눈⁠‸⁠눈⁠)ʕ⁠ಠ⁠_⁠ಠ⁠ʔ(⁠ಠ⁠_⁠ಠ⁠)⁠━⁠☆ﾟ⁠.⁠*⁠･⁠｡ﾟ
 diidnrmzisi2n(ieixie.si8dmejz I'm r
 ey7sjsu+Emily rr.ziod
 s disk 8zijd9e.z?,,:⁠-⁠\
(⁠´⁠;⁠︵⁠;⁠`⁠)ಥ⁠_⁠ಥ(⁠〒⁠﹏⁠〒⁠)ಥ⁠_⁠ಥ(⁠ ⁠⚈̥̥̥̥̥́⁠⌢⁠⚈̥̥̥̥̥̀⁠)(⁠｡⁠•́⁠︿⁠•̀⁠｡⁠)(⁠^⁠～⁠^⁠;⁠)⁠ゞ(⁠•⁠ ⁠▽⁠ ⁠•⁠;⁠)(⁠;⁠ŏ⁠﹏⁠ŏ⁠)(⁠•⁠ ⁠▽⁠ ⁠•(⁠´⁠⊙⁠ω⁠⊙⁠`⁠)⁠→ue8d sudkem d8dm2m8jnsjzizm..+j;hejs +$!"8$($($8$.$."8

d8dmeoe8sm3.ienmdizme
s.i!$(*!$(i?$?_.
zidme.dpz
.(($?$9>i





A job is a set of _steps_ in a workflow that is executed on the same runner.  Each step is either a shell script that will be executed, or an _action_ that will be run.  Steps are executed in order and are dependent on each other.  Since each step is executed on the same runner, you can share data from one step to another.  For example, you can have a step that builds your application followed by a step that tests the application that was built.

You can configure a job's dependencies with other jobs; by default, jobs have no dependencies and run in parallel with each other.  When a job takes a dependency on another job, it will wait for the dependent job to complete before it can run.  For example, you may have multiple build jobs for different architectures that have no dependencies, and a packaging job that is dependent on those jobs.  The build jobs will run in parallel, and when they have all completed successfully, the packaging job will run.
rjd8e. d9oeji(jnro.(k.(()$+($8$;_._?)")xor
rkdii.ejirni(h+iijje.e.xod i(i!.n)

7(!88enejdido..iinij.$.i((:$?4._89_?4.*
dj8rjd zi...ijht#9$!!.  i--;+8(#8*8$!3)"94+.$.3(*8$!.3."(*+3!+$9#($ 4.dd.d8idnrjdiej3n.dnx
For more information about jobs, see "[AUTOTITLE](/actions/using-jobs)."

### Actions

An _action_ is a custom application for the {% data variables.product.prodname_actions %} platform that performs a complex but frequently repeated task.  Use an action to help reduce the amount of repetitive code that you write in your workflow files.  An action can pull your git repository from {% data variables.product.prodname_dotcom %}, set up the correct toolchain for your build environment, or set up the authentication to your cloud provider.

You can write your own actions, or you can find actions to use in your workflows in the {% data variables.product.prodname_marketplace %}.

{% data reusables.actions.internal-actions-summary %}

For more information, see "[AUTOTITLE](/actions/creating-actions)."

### Runners

{% data reusables.actions.about-runners %} Each runner can run a single job at a time. {% ifversion ghes or ghae %} You must host your own runners for {% data variables.product.product_name %}. {% elsif fpt or ghec %}{% data variables.product.company_short %} provides Ubuntu Linux, Microsoft Windows, and macOS runners to run your workflows; each workflow run executes in a fresh, newly-provisioned virtual machine. {% ifversion actions-hosted-runners %} {% data variables.product.prodname_dotcom %} also offers {% data variables.actions.hosted_runner %}s, which are available in larger configurations. For more information, see "[AUTOTITLE](/actions/using-github-hosted-runners/using-larger-runners)." {% endif %}If you need a different operating system or require a specific hardware configuration, you can host your own runners.{% endif %} For more information{% ifversion fpt or ghec %} about self-hosted runners{% endif %}, see "[AUTOTITLE](/actions/hosting-your-own-runners)."

{% data reusables.actions.workflow-basic-example-and-explanation %}

## Next steps

{% data reusables.actions.onboarding-next-steps %}

{% ifversion ghec or ghes or ghae %}

## Further reading

- "[AUTOTITLE](/admin/github-actions/getting-started-with-github-actions-for-your-enterprise/about-github-actions-for-enterprises)"
{% endif %}
