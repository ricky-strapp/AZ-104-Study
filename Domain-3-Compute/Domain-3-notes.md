# Domain 3 - Notes / Key Takeaways

**VM Move - IP Address:** I had to dissociate the IP address before I could move the VM to a different subscription. This was something I wasn't expecting, so was an interesting learning point.

**VM Cross-region Move:** I deliberately did not complete the final step in the cross-region move for a VM in my practical testing. This was to avoid data egress costs. The preliminary steps are shown in my screenshots though.

**Subscription Quotas / Region Restrictions:** I found that I could not create resources at all in UK South and was limited in other regions as well. I suspect this to either be because I am using the 30-day free trial credits, or because it is a new account, or both. Quota limit increases require a support request.

**App Service Custom Name Domain:** I could not fully complete this element because I did not have a Custom Domain that I could use for this purpose. I have therefore just shown the correct screen where these changes can be made in the portal. 

**App Service Certificates:** For the same reasons as the Custom Domain element, I could not fully complete this element either. I have therefore just shown the correct screen where these changes can be made in the portal.

**ARM Templates:** I found out that the Visual Studio Code ARM Tools extension has a known schema validation bug where it checks the literal length of parameter expression strings rather than their runtime values. This causes false maxLength errors. Ultimately the solution was to hardcode the resource names in the ARM templates when using VS Code. Using the Azure template editor would have been more lenient here.