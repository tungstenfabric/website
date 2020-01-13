<img src="https://github.com/tungstenfabric/website/raw/master/TungstenFabric_Gradient_RGB-03.png" height="75" alt="Tungsten Logo Gradient">

----

Tungsten Fabric is an open source network virtualization solution for
providing connectivity and security for virtual, containerized or
bare-metal workloads.

Tungsten Fabric supports integrations with the following orchestrators:
```
Openstack
Kubernetes
Openshift
vCenter
BYOO [Bring your own orchestrator]
```

Tungsten Fabric is a part of the [Linux Foundation Networking Fund], a project of the [Linux Foundation].


---

## Start using Tungsten Fabric
[Deploy Tungsten Fabric in 15 minutes on AWS with Kubernetes]

[Deploy Tungsten Fabric on Kubernetes in 1-step command - Centos]

[Deploy Tungsten Fabric on Kubernetes in 1-step command - Ubuntu]

[Deploy Tungsten Fabric On-Prem with Openstack]

[Tungsten Fabric Detailed Architecture Document]

[Tungsten Fabric Detailed Architecture Document (Simplified Chinese)](L10N/Tungsten-Fabric-Architecture-CN.md)

## Becoming a contributor

Whether you want to fix a typo in comments or introduce a brand new feature,
there are a few steps which make the process smoother:

* Create a [Linux Foundation ID], if you don't have one yet. You'll need this to subscribe to the mailing lists and to access the bugs and blueprints.

* Subscribe to the [dev@lists.tungsten.io] mailing list. If you wish, there are also [several other mailing lists] you can join as well.

* The wiki currently contains legal and technical docs, event decks and similar resources to boost your
understanding of Tungsten Fabric. This material will eventually be moving to
[the wiki] or Git repositories.

* [Join Slack]. Post your questions to relevant channels, don't abuse @here,
get help and help others. The mailing list works best for long-running
discussions; Slack is great for ad-hoc conversations.

* Before you push anything, you'll need to sign a Contributor License Agreement
or CLA: either Individual CLA (ICLA) if you are an independent contributor, or
Corporate CLA (CCLA). We suggest you sign a CCLA if you are employed at a company
which pays you for your Tungsten Fabric-related work. CCLA also simplifies things
if your teammates plan to contribute as well. Both ICLA and CCLA are legal documents.
Please read them carefully. It's usually smart to run the document past your
company's legal department before signing and submitting it, if only to verify
that your contribution will be within your company's policy. You can find all
ICLA/CCLA documents in the [Tungsten Fabric CLA Wiki].

* If you've found a bug, [file a bug report] against the respective release in
Jira. Be sure to describe both expected and actual behavior. You'll need
the bug ID later, so please do this even if you feel the change is trivial.

* If you plan to develop a new feature, you must create or provide three things:
    * [A blueprint]. A blueprint is a short piece of text describing which feature do you propose, why it is good to have it in Tungsten Fabric, and who will be developing it. Blueprints are very important as they are used to plan future releases of Tungsten Fabric.
    * [A detailed technical spec]. Each blueprint should link to a more detailed technical specification document. These specifications must be submitted to the [contrail-specs] GitHub repository. They are not stored or tracked in Jira.
    * [A Jira bug ticket]. While the blueprint briefly describes the work that will be done, the ticket is where the work actually happens (commits get linked to the ticket).
    * Here is [an example of a complete Jira blueprint].

* Although contrail-specs and other Tungsten Fabric repositories are hosted on
[GitHub], they are managed with Gerrit. Please don't send Pull Requests to the
GitHub repositories, and go to [https://review.opencontrail.org] instead.
Blueprint specs are submitted this way as well.
* Note that Tungsten Fabric is currently migrating from Juniper owned [https://review.opencontrail.org] to [https://github.com/tungstenfabric/] email discuss@lists.tungsten.io for the latest information.

* After getting Gerrit access as described below, clone the specs repository
with the command:
```git clone https://review.opencontrail.org/Juniper/contrail-specs```
and install the [git-review extension] which will allow you to submit specs as
well as code changes. In order to write a spec, start by copying the template
`blueprint_template.md` to a meaningful name in the appropriate subdirectory
for the release that you would like to target.

With all of these in place, you are now ready to submit your specs and code to
Tungsten Fabric! How to write these specs and code is a different story though,
but we hope the links in the next section will help you to get started. You may
also want to consult a more detailed how-to available [here], in the
contrail-community-docs repo. And of course, feel free to ask questions on the
mailing list and in Slack channels!

## Start developing Tungsten Fabric

[Build Tungsten Fabric]

[Debug Tungsten Fabric]

### Development Timeline

NOTE: The columns and dates below are subject to change. An effort is still
underway to reconcile Tungsten Fabric processes and previously established
Juniper practices with respect to Contrail development timelines.

| Release | Blueprint Due | Specification Due | Dev Complete | GA Release |
| ------- | ------------- | ----------------- | ------------ | ---------- |
|   5.0   |               |                   |              | 2018-04-23 |
|  5.0.1  |               |                   |              | 2018-07-16 |
|   5.1   |  2018-07-15   |     2018-08-22    |     TBD      |    Q1 2019 |

#### Column Meanings
* Release: The numeric identifier of the release
* Blueprint Due: Tungsten Fabric currently uses Jira, so the blueprint
due here refers to the [Jira Blueprint] which will be reviewed by the TSC for strategic alignment and release planning.
* Specification Due: The specification or "spec" is design document with
section headings that should be filled in, or at least though about and decided
to be non-applicable. Specs should be submitted as described earlier in this
document.
* Dev Complete: This column may be considered synonymous with "feature freeze"
and is intended to mark the transition from "new development" to "testing,
debugging and making production-ready".
* GA Release: This column is the target release date. Historically Contrail has
usually missed release dates in order to finish incomplete features. Tungsten
Fabric will attempt to move to a time based release model, but this is still
under discussion.

[(LFN)]: https://www.linuxfoundation.org/projects/networking/
[Deploy Tungsten Fabric in 15 minutes on AWS with Kubernetes]: Tungsten-Fabric-15-minute-deployment-with-k8s-on-AWS.md
[Deploy Tungsten Fabric on Kubernetes in 1-step command - Centos]: Tungsten-Fabric-Centos-one-line-install-on-k8s.md
[Deploy Tungsten Fabric on Kubernetes in 1-step command - Ubuntu]: Tungsten-Fabric-Ubuntu-one-line-install-on-k8s.md
[Deploy Tungsten Fabric On-Prem with Openstack]: https://github.com/Juniper/contrail-ansible-deployer/wiki/Contrail-with-Openstack-Kolla
[Tungsten Fabric Detailed Architecture Document]: Tungsten-Fabric-Architecture.md
[tungsten-dev@googlegroups.com]: https://groups.google.com/forum/#!forum/tungsten-dev
[dev@lists.tungsten.io]: https://lists.tungsten.io/g/dev
[Join Slack]: https://tungsten.io/slack
[contrail-specs]: https://github.com/Juniper/contrail-specs
[GitHub]: http://github.com/tungstenfabric
[git-review extension]: https://docs.openstack.org/infra/git-review/
[https://review.opencontrail.org]: https://review.opencontrail.org
[Tungsten Fabric CLA Wiki]: https://wiki.tungsten.io/display/TUN/Contributor+License+Agreement
[here]: https://github.com/Juniper/contrail-community-docs/blob/master/Contributor/GettingStarted/getting-started-with-opencontrail-development.md
[Build Tungsten Fabric]: https://github.com/Juniper/contrail-dev-env
[Debug Tungsten Fabric]: https://github.com/Juniper/contrail-ansible-deployer/wiki/Debugging-contrail-code-in-contrail-microservices
[Jira Blueprint]: https://jira.tungsten.io/projects/TFP/issues/TFP-6?filter=allopenissues
[Linux Foundation Networking Fund]: https://www.lfnetworking.org
[Linux Foundation]: http://linuxfoundation.org
[A Jira blueprint]: https://jira.tungsten.io/projects/TFP/issues/TFP-6?filter=allopenissues
[A detailed technical spec]: https://github.com/Juniper/contrail-specs
[A Jira bug ticket]: https://jira.tungsten.io/projects/TFB/issues/TFB-15?filter=allopenissues
[an example of a complete Jira blueprint]: https://jira.tungsten.io/browse/TFP-13
[file a bug report]: https://jira.tungsten.io/projects/TFB/issues/TFB-15?filter=allopenissues
[Linux Foundation ID]: https://identity.linuxfoundation.org
[several other mailing lists]: https://lists.tungsten.io
[A blueprint]: https://jira.tungsten.io/projects/TFP/issues/TFP-6?filter=allopenissues
[the wiki]: https://wiki.tungsten.io
