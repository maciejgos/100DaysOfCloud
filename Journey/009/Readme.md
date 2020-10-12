<!-- This is a template you can use for quick progress days. It removes a lot of the steps we encourage you to share in the longer template 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->

# [9-12/100] Implement VMs for Windows and Linux #az303

## Cloud Research
Important thing to consider implementing/using VM's is to choose correct size and availability options. Also it is recommended to setup VM's using VNet's and secure them by NSG (Network Security Groups).
- [Azure Virtual Machines documentation](https://docs.microsoft.com/en-us/azure/virtual-machines/) 
- [Sizes for virtual machines in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes)
- [Availability options for virtual machines in Azure](https://docs.microsoft.com/en-us/azure/virtual-machines/availability)

We can also reduce costs of VM's using...
> ## Reducing costs by using low-priority scale sets
> A low-priority virtual machine scale set allows you to use Azure compute resources at cost savings of up to 80 percent. The global Azure infrastructure frequently > has underused compute resources available. A low-priority scale set provisions VMs through this underused compute capability.
> When you use these VMs, keep in mind that they're temporary. Availability depends on size, region, time of day, and so on. These VMs have no SLA.
> When Azure needs the computing power again, you'll receive a notification about the VM that will be removed from your scale set. If you need to clean up or > gracefully exit code on your VM, you can use Azure Scheduled Events to react to the notification within the VM. You can also make the scale set try to create > another VM to replace the one that's being removed. The creation of the new VM is, however, not guaranteed.
> In a low-priority scale set, you specify two kinds of removal:
> 	• Delete: The entire VM is removed, including all of the underlying disks.
> 	• Deallocate: The VM is stopped. The processing and memory resources are deallocated. Disks are left intact and data is kept. You're charged for the disk space > while the VM isn't running.
> Low-priority scale sets are useful for workloads that run with interruptions or when you need larger VMs at a much-reduced cost. Just keep in mind that you can't > control when a VM might be removed.

From <https://docs.microsoft.com/en-us/learn/modules/build-app-with-scale-sets/2-features-benefits-virtual-machine-scale-sets> 

## Social Proof

✍️ Show that you shared your process on Twitter or LinkedIn

[Twitter](https://twitter.com/maciejgos/status/1315630596966752256)
