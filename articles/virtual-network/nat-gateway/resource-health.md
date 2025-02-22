---
title: Azure Virtual Network NAT Resource Health
titleSuffix: Azure Virtual Network
description: Understand how to use resource health for Virtual Network NAT.
author: asudbring
ms.service: virtual-network
ms.subservice: nat
# Customer intent: As an IT administrator, I want to understand how to use resource health to monitor Virtual Network NAT.
ms.topic: conceptual
ms.date: 04/25/2022
ms.author: allensu
---
# Azure Virtual Network NAT Resource Health

This article provides guidance on how to use Azure Resource Health to monitor and troubleshoot connectivity issues with your NAT gateway resource. Resource health provides an automatic check to keep you informed on the current availability of your NAT gateway.

## Resource health status

[Azure Resource Health](/azure/service-health/overview) provides information about the health of your NAT gateway resource. You can use resource health and Azure monitor notifications to keep you informed on the availability and health status of your NAT gateway resource. Resource health can help you quickly assess whether an issue is due to a problem in your Azure infrastructure or because of an Azure platform event. The resource health of your NAT gateway is evaluated by measuring the data-path availability of your NAT gateway endpoint.

> [!IMPORTANT]
> When you first create your NAT gateway resource and attach it to a subnet and public IP address/prefix, there is no available data as of yet to determine the health status of your NAT gateway resource. In the first few minutes after your NAT gateway is created, you may see the health status of your NAT gateway change from Unavailable to Degraded and then to Available as health data is generated. This is an expected behavior. If you have only a public IP address or only a subnet attached to your NAT gateway resource upon deployment, the health status will immmediately show as Unknown.  

You can view the status of your NAT gateway’s health status on the **Resource Health** page, found under **Support + troubleshooting** for your NAT gateway resource.  

The health of your NAT gateway resource is displayed as one of the following statuses: 

| Resource health status | Description |
|---|---|
| Available | Your NAT gateway resource is healthy and available. |
| Degraded | Your NAT gateway resource has platform or user initiated events impacting the health of your NAT gateway. The metric for the data-path availability has reported less than 80% but greater than 25% health for the last fifteen minutes. |
| Unavailable | Your NAT gateway resource is not healthy. The metric for the data-path availability has reported less than 25% for the past 15 minutes. You may experience unavailability of your NAT gateway resource for outbound connectivity. |
| Unknown | Health status for your NAT gateway resource hasn’t been updated or hasn’t received information for data-path availability for more than 5 minutes. This state should be transient and will reflect the correct status as soon as data is received. |

For more information about Azure Resource Health, see [Resource Health overview](/azure/service-health/resource-health-overview).

To view the health of your NAT gateway resource:

1. From the NAT gateway resource page, under **Support + troubleshooting**, select **Resource health**.

2. In the health history section, select the drop-down arrows next to dates to get more information on health history events of your NAT gateway resource. You can view up to 30 days of history in the health history section. 

3. Select the **+ Add resource health alert** at the top of the page to set up an alert for a specific health status of your NAT gateway resource. 

## Next steps

- Learn about [Virtual Network NAT](/azure/virtual-network/nat-gateway/nat-overview)
- Learn about [metrics and alerts for NAT gateway](/azure/virtual-network/nat-gateway/nat-metrics)
- Learn about [troubleshooting NAT gateway resources](/azure/virtual-network/nat-gateway/troubleshoot-nat)
- Learn about [Azure resource health](/azure/service-health/resource-health-overview)
