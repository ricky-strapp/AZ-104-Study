# Domain 2 - Notes / Key Takeaways

**Azcopy:** - When I initially ran the command to upload a test file, it failed to transfer, returning a 403 error. I ran an IP query to see what IP address Azure was actually seeing; this was different to my usual IP address. I then added that IP address to the whitelist, and the transfer then worked. The learning point here is to check what IP address Azure is actually seeing before doing such queries. 
