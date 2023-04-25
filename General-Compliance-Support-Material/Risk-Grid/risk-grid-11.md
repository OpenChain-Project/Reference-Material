# Overview

This is a MarkDown conversation of the Risk Grid - Version 11. It is intended to help create new, improved versions. This document is a near-perfect copy of the original spreadsheet. The only changes are related to formatting and correcting typos or localization issues. The issues have also been numbered to enable easier editing moving forward.

# Structure:

Each issue is formatted as follows:

- Issue	
- Commentary	
- Who is best placed to bear risk?	
- Best mechanism to tackle risk	
- Sample Wording	
- Supplier's Arguments	
- Customer's arguments	
- Comments

## Issue #1	

Supplier-created code infringes copyright

### Commentary	

The risk of detection of infringement is easier for [F/OSS] (as the code is more readily available for comparison purposes, especially if the code is GPL and re-distributed, but the ability of the customer to mitigate its loss is greater, as it automatically has access to the source code, to enable it to re-engineer infringing code itself if the Supplier will not or cannot do so.

### Who is best placed to bear risk?

Supplier	

### Best mechanism to tackle risk

Indemnity/warranty from Supplier. Supplier has right to rewrite infringing code. Version control system (VCS) shared repository and allowing audit rights.	

### Sample Wording

The Supplier warrants that it has title to all Supplier-Created Code and that its delivery [assignment/license] to the Customer and use in accordance with this Agreement does not infringe the [copyright] of any third party.	

### Supplier's Arguments	

No good ones

### Customer's arguments	

Supplier is in control of code creation, and should therefore be liable for third party infringements. Supplier should use a common source code repository, to which Customer may be given access.

### Comments

Note that supplier-created code may in practice amount to  amendments to existing publicly available code (and create a derivative work of that code). In that case, the row below (publicly available code infringes copyright) would be more appropriately apply)

## Issue #2

Publicly-available code (i.e. code acquired from third parties under a [F/OSS] license, and incorporated into the software) infringes third party copyright.	
(Part 1)

### Commentary	

One risk is that the  publicly available code selected is inherently infringing (i.e. there is a provenance issue), or alternatively, the component is available under a [F/OSS] license, but not the one attached to it. Note that “publicly available code” will include publicly available code that has been amended by the Supplier to create a derivative work.

### Who is best placed to bear risk?

Varies from project to project. If the Customer specifies use of a specific component, then it should be liable for claims in relation to that component. If the Supplier selects the components, there is a stronger argument that the Supplier should bear some of the risk, or at least take care in the selection process.	

### Best mechanism to tackle risk

Warranty or indemnity from the Supplier, to encourage Supplier to take care in source selection. A list of agreed sources of code may give the Customer comfort (even if this is by no means conclusive), and may encourage the Supplier to take fewer risks in terms of provenance. Further, if code is obtained from recognized locations, it is more likely to be heavily reused, and therefore there is, arguably,  safety in numbers (i.e. the code has been used many times before and there hasn't been a claim yet), and also the likelihood that if it is found to be infringing, the community will generate a non-infringing alternative.	

### Sample Wording	

The Supplier warrants that each component of Publicly Available Code incorporated in the Software has been acquired solely from the locations listed in Appendix [1] and that the source of each such acquisition shall be accurately documented [as set out in Appendix [2]]. [The Supplier further confirms that it has compiled, [with reasonable skill and care], documentation required by the license[s] applicable to the Publicly Available Code and will provide it to the Customer in order to enable the Customer to comply with [the notice and disclaimer] conditions applicable to such license[s]].

### Supplier's Arguments	

Each Customer has a different appetite for risk. Requiring  the Customer to document how it regards the risk of accessing code from different locations, gives the Supplier more information on which to base an accurate price for the job. Alternatively, Supplier may want to give the Customer the option of a cheaper price by doing “quick and dirty” development by scraping code from anywhere, without provenance checking, providing that the Customer takes the risk. In any case, this clause as drafted could prove unduly restrictive for the Supplier. There are vast amounts of quality code available from “grey” sites. Also, is “reasonable skill and care” capable of consistent interpretation given the state of the art? Koders.com contains plenty of roll-your own licenses, for example. Also, just because something is on sourceforge.net does not mean that it is necessarily of any better provenance than elsewhere.

### Customer's arguments

Supplier is contracting to supply IPR, and should bear all the risk. How Supplier intends to source IPR should not be Customer's issue. In any event, where the Supplier is actively choosing the code to use, provenance checking should be a selection criterion.	

### Comments

Infringement can occur either because the infringing code is not available under any [F/OSS] license (e.g. it is derived from proprietary code), or because it is not available under the license supposedly attached to it (e.g. it is available under the GPL, but appears to be available under the BSD). It may also occur because the code has not been released by complying with the appropriate notices in the licenses (e.g. copyright notices, disclaimers). These are reasonably easy to correct.

## Issue #3	

Publicly-available code (i.e. code acquired from third parties under a [F/OSS] license, and incorporated into the software) infringes third party copyright.
(Part 2)

### Commentary	

Another risk is that the Customer (as opposed to the Supplier) may specify the use of specific [F/OSS] components, and in using these components faces a similar issue as above, though with a different context for allocating potential liability.

### Who is best placed to bear risk?	

If the Supplier selects the components, there is a stronger argument that the Supplier should bear some of the risk, or at least take care in the selection process.  If the Customer performs this selection, the opposite is true.

### Best mechanism to tackle risk	

Customer takes all risks relating to the nominated code.

### Sample Wording	

The Customer acknowledges, notwithstanding any other provision of this Agreement, that the Supplier shall not be responsible for any claim, cost or expense howsoever arising from the Supplier's incorporation, use of, modification of, linking  to  the Customer's Specified Components [and the Customer shall indemnify the Supplier for any cost, claim or expense arising therefrom].

### Supplier's Arguments	

The Supplier's choice of component is restricted, and therefore it should not be held liable for such use.

### Customer's arguments	

None Listed.

### Comments

None Listed.

## Issue #4	

Publicly-available code (i.e. code acquired from third parties under a [F/OSS] license, and incorporated into the software) infringes third party copyright.
(Part 3)

### Commentary	

It is possible to explicitly address the risk of publicly available code not being available under the license apparently attached to it, and instead actually falling under a different license and potentially incompatible license.

### Who is best placed to bear risk?	

This is similar to the provenance issue, in that the Customer's use/modification/distribution of the Software may infringe third party rights, but in this case, infringement may depend on the Customer's intended out-license or intended use of the Software. This wording contains an option which limits the Supplier's obligations to checking that the components' attached licences are on an approved list, but not that they are compatible with any intended use.

### Best mechanism to tackle risk	

Warranty relating to the licenses attached to publicly-available code components. Optional exclusion of liability for license incompatibility (Customer takes risk of incompatibility).

### Sample Wording	

[The Supplier warrants that[, so far as it is aware,] each component of Publicly Available Code incorporated in the Software is available under one of the licenses specified in Appendix [3] and has documented the provenance of each such component [as set out in Appendix [1]][ The Supplier does not warrant that use, modification or distribution by the Customer of the Software will not infringe the rights of any third party, and no provision of this Agreement or implied term shall be construed as such a warranty].

### Supplier's Arguments	

The Supplier does not want to be responsible for ensuring license compatibility, as the Customer will be much better placed to determine what its intended use is. Therefore, it's more practical for the Customer to specify a list of compatible licenses, than having the Supplier do compatibility checks.

### Customer's arguments	

The Customer selects code.

### Comments

None Listed.

## Issue #5	

Publicly-available code (i.e. code acquired from third parties under a [F/OSS] license, and incorporated into the software) infringes third party copyright.
(Part 4)

### Commentary	

Sweeper up warranty designed to ensure that code-selection for copyrights is within the ambit of the Supplier's services.

### Who is best placed to bear risk?	

Supplier

### Best mechanism to tackle risk	

Warranty that skill and care has been taken in component selection, so far as third party copyrights are concerned.

### Sample Wording	

[The Supplier warrants that it has taken reasonable skill and care in selecting publicly available components having regard to the non-infringement of third party copyrights [the Customer's Specified Use and the Customer's Specified Out-License], and has documented the provenance and licenses applicable to such components [as set out in Appendix [1] and [2] [with reference to Appendix [3] where applicable]].]

### Supplier's Arguments	

This warranty is too vague, at least without qualification as to whether the licences which are attached to the components are compatible with the Customer's Specified Use or (preferably) the Customer's Specified Out-License.

### Customer's arguments	

The Supplier needs to be put under a practical obligation to make copyright compatibility/awareness part of its selection criteria.

### Comments

None Listed.

## Issue #6	

Publicly-available code (i.e. code acquired from third parties under a [F/OSS] license, and incorporated into the software) infringes third party copyright.
(Part 5)

### Commentary	

Publicly available code is incompatible with the Customer's Specified Use or Specified Out-License. By requiring the Customer to specify in this way, expectations are managed, and minds are focused. Note that 'Specified Use' may include internal use only with no possibility of distribution (which allows code to be mingled freely), or internal use only with interaction over a network externally, (which allows code to be mingled freely, unless network-aware licenses like AGPL or OSL are employed).

### Who is best placed to bear risk?	

Supplier (in relation to code and module assembly) and Customer (in ensuring that the code is only used for the Specified Use).

### Best mechanism to tackle risk	

None listed.

### Sample Wording	

The Supplier warrants that [so far as it is aware, but without having made any specific enquiry] the development of the Software, its delivery to the Customer and the Customer's modification, distribution and use of the Software within the Specified Use [or relicensing to third parties within the Specified Out-License]. shall not infringe the licenses set out in Appendix [3]. The Customer acknowledges that use of the Software outside the scope of the Specified Use [and any distribution of the Software to a third party] may infringe third party rights.

### Supplier's Arguments	

This warranty places the onus on the Supplier (at least without the awareness qualification) to ensure compatibility, which can include a legal analysis of different licences. This may be outside the scope of the ability of the Supplier, or the scope of the services intended to be provided.

### Customer's arguments	

The Customer has taken time to specify either the licenses to be used, or the Specified Use, and it is up to the Supplier to ensure that the Software complies with this requirement.

### Comments

Code with incompatible licenses can be intermingled, if there is no question of it being distributed (and, where relevant licenses like AGPL and OSL are concerned, accessed externally over a network). If the Customer brief requires this, then it is sensible to include a clause in the agreement stating that the Supplier is acting as the agent of the Customer in authoring the code, to prevent the distribution of code from Supplier to Customer being a distribution. This is particularly important in jurisdictions (like the UK) with no work-for-hire doctrine. It is sensible also to consider present transfer of future rights. See 'Status of Supplier' below.

## Issue #7	

Infringement by misuse of third party code by the Customer.

### Commentary	

None listed.

### Who is best placed to bear risk?	

Customer

### Best mechanism to tackle risk	

None listed.

### Sample Wording	

[The Customer is responsible for ensuring that its own subsequent use, modification and re-distribution of the software [outside the Specified Use] is in accordance with [the licenses set out in Appendix [3]].

### Supplier's Arguments	

The Supplier is developing  for the Customer. Therefore the Supplier is not to be concerned about out-licensing, outside the scope of the specified use. This is the Customer's issue.  Any future or different uses would be subject to a future or different agreement.

### Customer's arguments	

The Customer may want to distribute in the future, and may want to out-license to customers etc. Also, passing around the group, or to the acquirer of the business may be “distribution” and therefore should be covered.

### Comments

None listed.

## Issue #8	

Bought-in proprietary code infringes third party copyright

### Commentary	

A third party proprietary library may have a provenance issue – i.e. it obtains code which the supplier is not entitled to license This code may itself be proprietary, or it may be [F/OSS].

### Who is best placed to bear risk?	

Supplier (through contractual relationship with provider of the proprietary code) (unless use of that component is nominated by the Customer – see above)

### Best mechanism to tackle risk	

Indemnity/warranty from Supplier - but can Supplier obtain a back to back indemnity from the provider of that code? This chain may need to extend all the way up to the ultimate provider.

### Sample Wording	

The Supplier [confirms that the licenses under which the third party components of the Software are available [are contained within the list set out in Appendix [3] as amended from time to time by agreement between the parties]][will not be breached by the Customer's Specified Use][,permit the Customer to out-license the Software under the Specified Out-License] and that so far as it is aware [but not having made specific enquiry] the development of the Software and its delivery to the Customer do not infringe such licenses. [The Customer is responsible for ensuring that its own subsequent use, modification and re-distribution of the software [outside the Specified Use] is in accordance with such licenses.][The Supplier agrees to provide reasonable assistance to the Customer in passing the benefit of any warranties associated with such third party [proprietary] components to the Customer subject to the Customer's continued compliance with the licenses applicable to such code.

### Supplier's Arguments	

Supplier to use reasonable skill and care in selecting code, but should not be liable for third party infringement. Similar to the supply of third party hardware. May offer to pass on any third party warranties available. May also be subject to the Customer complying with terms passed through by the Supplier.

### Customer's arguments	

Supplier is contracting to supply IPR, and should bear all the risk. How Supplier intends to source IPR should not be Customer's issue.

### Comments

The third party code may infringe because it contains copyleft code, but the source is not made available. This may cause the customer to be the subject of, for example, a GPL violations claim, even if the customer wishes all the code to be available under the GPL, because it does not have access to the source. The customer's remedy may therefore be to compel the supplier to release the source (which may have to pass this requirement up the supply chain). This also suggests a circumstance where the customer insists on the source code being placed in escrow, and released if there is a third party GPL violations claim.

## Issue #9	

Infringement of patent in Supplier Created Code

### Commentary	

None listed.

### Who is best placed to bear risk?	

Where Supplier has choice of implementation: Supplier. Where implementation is dictated by Customer's requirements: Customer.

### Best mechanism to tackle risk	

Right to change implementation, if implementation is determined by Supplier. Otherwise, risk is on Customer. May be possible to negotiate risk sharing. May be possible to get insurance? Audit rights?

### Sample Wording	

The Supplier warrants that [so far as the Supplier is aware [not having made any enquiry]] the use by the Customer of the Software for its Specified Use [within [jurisdictions]] will not infringe any right which any third party may hold under any valid patent.

### Supplier's Arguments	

It is not economically feasible to undertake a patent clearance prior to implementation. If the implementation is dictated by the Customer's requirements, this should not affect liability. The existence of patents in the Customer's field of business (particularly of they are business-method patents) are part of the cost and risk of doing business in that sector, and the customer should be aware of, and take the risk, accordingly.

### Customer's arguments	

Supplier is contracting to supply IPR, and should bear all the risk. How Supplier intends to source IPR should not be Customer's issue.

### Comments

None listed.

# DOCUMENT INCOMPLETE AND AWAITING FURTHER POPULATION.


## Issue	



### Commentary	



### Who is best placed to bear risk?	



### Best mechanism to tackle risk	



### Sample Wording	



### Supplier's Arguments	



### Customer's arguments	


### Comments



## Issue	



### Commentary	



### Who is best placed to bear risk?	



### Best mechanism to tackle risk	



### Sample Wording	



### Supplier's Arguments	



### Customer's arguments	


### Comments



## Issue	



### Commentary	



### Who is best placed to bear risk?	



### Best mechanism to tackle risk	



### Sample Wording	



### Supplier's Arguments	



### Customer's arguments	


### Comments



## Issue	



### Commentary	



### Who is best placed to bear risk?	



### Best mechanism to tackle risk	



### Sample Wording	



### Supplier's Arguments	



### Customer's arguments	


### Comments

