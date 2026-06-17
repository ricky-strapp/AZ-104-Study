# Domain 5 - Notes / Key Takeaways

**Insights - VM:** I had a persistent error saying that the workspace was 'Not Onboarded' and data was not displaying in the performance tab, despite the Monitor Agent being successfully installed on the VM. This was really quite tricky to solve because there were 3 separate root causes combined together which impacted the situation. 

The first root cause was from the Data Collection Rule (DCR) being associated with a different VM from a different resource group (which was deallocated). I think this was caused by incorrectly applying the settings at the subscription level. To solve this, I restarted the deallocated VM. This, I believe, allowed the DCR to initialize properly, which it was prevented from doing before then.

The second root cause was previously applied NSGs blocking outbound traffic to Azure Monitor's service endpoints. I fixed this by checking the NSGs in force and adding an explicit outbound traffic rule for the `AzureMonitor` Service Tag on port 443.

The third root cause was that the Data Collection Rule data source was configured with only the 'Custom' counter, which seemingly does not populate the `Perf` table in Log Analytics. Once I found this and changed it to include CPU, Memory, etc., the data started to flow through to Insights.

**Configure Azure Site Recovery for Azure resources:** I couldn't initially get disaster recovery set up for a VM. It was failing during setup because there was an NSG in place which was ultimately preventing the VM from reaching the Azure Recovery Services endpoints. When the NSG rule was removed, the process went smoothly.

**Perform a failover to a secondary region by using Site Recovery:** Failover failed the first time I tried to run it. The error was “We do not have sufficient capacity for the requested VM size in this zone (Error 28031)”, so it was not an issue on my side. In order to test the failover again, I first had to clear out the failed attempt. Then, I amended the VM size to a smaller option and retried a second time after 15 minutes or so, which was successful.
