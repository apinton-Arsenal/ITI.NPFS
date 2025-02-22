This profile defines how to enable the sharing of non-patient files.

Those files can be created, consumed and updated by many different
systems involved in a wide variety of data sharing workflows (clinical
workflow definition, domain policies sharing, stylesheets management,
etc.). This profile identifies three actors: File Manager, File
Consumer, and File Source. To fulfill use-case requirements, this
profile defines four new transactions (Submit File \[ITI-87\], Search
File \[ITI-88\], and Update DocumentReference \[ITI-89\]) and Retrieve File \[ITI-109\].

There are IHE profiles that define the content of files that are not
patient-related; this profile does not require that the actors be able
to process the contents of the files being shared. Understanding this
profile does not require the knowledge of the files shared.

The NPFS Profile specifies transactions for the sharing of files. Any
file type can be shared using this profile; however, specific guidance
is given for three types of files:

- Workflow Definitions: files which define the processing rules for a
  specific clinical/administrative workflow (see [ITI TF-1: 30.4.1.1 “XDW Workflow Architecture”](https://profiles.ihe.net/ITI/TF/Volume1/ch-30.html#30.4.1.1) for additional information).

- Privacy Domain Policies: files which describe a specific privacy
  policy that applies to, or may be agreed by the patient (see [ITI TF-1: 19.2 “Creating Patient Privacy Policies”](https://profiles.ihe.net/ITI/TF/Volume1/ch-19.html#19.2) for further details).

- Stylesheets: structured documents used by user-agents (e.g., Web
  Browsers) to render the content of an XML document.

Local policies may extend the types of files shared using NPFS and that
can be classified using the metadata model described in this profile.

<div markdown="1" class="stu-note">

| [Significant Changes, Open and Closed Issues](issues.html) |
{: .grid}

</div>

### Organization of This Guide
This guide is organized into the following sections:

- Volume 1:
  - [Introduction](volume-1.html)
  - [Actors, Transactions, and Content](volume-1.html#1471-npfs-actors-transactions-and-content-modules)
  - [Actor Options](volume-1.html#1472-npfs-actor-options)
  - [Actor Required Groupings](volume-1.html#1473-npfs-required-actor-groupings)
  - [Overview](volume-1.html#1474-npfs-overview)
  - [Security Considerations](volume-1.html#1475-npfs-security-considerations)
  - [Cross Profile Considerations](volume-1.html#1476-npfs-cross-profile-considerations)
- Volume 2: Transaction Detail
  - [Submit File \[ITI-87\]](ITI-87.html)
  - [Search File \[ITI-88\]](ITI-88.html)
  - [Update DocumentReference \[ITI-89\]](ITI-89.html)
  - [Retrieve File [ITI-109]](ITI-109.html)
- Other
  - [Test Plan](testplan.html)
  - [Changes to Other IHE Specifications](other.html)
  - [Download and Analysis](download.html) 

See also the [Table of Contents](toc.html) and the index of [Artifacts](artifacts.html) defined as part of this implementation guide.

### Conformance Expectations

IHE uses the normative words: Shall, Should, and May according to [standards conventions](https://profiles.ihe.net/GeneralIntro/ch-E.html).

#### Must Support

The use of ```mustSupport``` in StructureDefinition profiles equivalent to the IHE use of **R2** as defined in [Appendix Z](https://profiles.ihe.net/ITI/TF/Volume2/ch-Z.html#Y).

mustSupport of true - only has a meaning on items that are minimal cardinality of zero (0), and applies only to the source actor populating the data. The source actor shall populate the elements marked with MustSupport, if the concept is supported by the actor, a value exists, and security and consent rules permit. 
The consuming actors should handle these elements being populated or being absent/empty. 
Note that sometimes mustSupport will appear on elements with a minimal cardinality greater than zero (0), this is due to inheritance from a less constrained profile.
