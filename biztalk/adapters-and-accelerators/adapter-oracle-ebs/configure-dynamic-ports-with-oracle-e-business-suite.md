---
title: Oracle E-business Suite での動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75a150ea-d957-4a37-81cf-c043a0a7d5cb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2f960560a631dd2eaf36f43522513242c240e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981915"
---
# <a name="configure-dynamic-ports-with-oracle-e-business-suite"></a><span data-ttu-id="e0064-102">Oracle E-business Suite での動的ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0064-102">Configure dynamic ports with Oracle E-Business Suite</span></span>
<span data-ttu-id="e0064-103">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0064-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="e0064-104">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]メッセージ コンテキスト プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e0064-104">Because the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="e0064-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、URI、アクション、およびバインド、受信メッセージのプロパティから決定されで指定された可能性があります、**式**図形、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="e0064-105">For the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="InterfaceTables/Insert/OFA/FA/FA_BOOKS";  
Request2(WCF.BindingType)="oracleEBSBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracleebs://ebs_instance";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
```  
  
> [!NOTE]
>  <span data-ttu-id="e0064-106">Wcf-oracleebs アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`ここで、 **OracleEBSAdapter**で Wcf-oracleebs アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="e0064-106">If you are using a WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleEBSAdapter"`, where **OracleEBSAdapter** is the name with which you added the WCF-OracleEBS adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="e0064-107">前の例では、</span><span class="sxs-lookup"><span data-stu-id="e0064-107">In the preceding example,</span></span>  
  
- <span data-ttu-id="e0064-108">Request1 メッセージから Request2 メッセージを作成しています。</span><span class="sxs-lookup"><span data-stu-id="e0064-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="e0064-109">両方のメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0064-109">Both messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
- <span data-ttu-id="e0064-110">送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="e0064-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="e0064-111">**式**図形は、BizTalk オーケストレーションの一部です。</span><span class="sxs-lookup"><span data-stu-id="e0064-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="e0064-112">オーケストレーションを展開すると、Wcf-custom 送信ポートも作成します。</span><span class="sxs-lookup"><span data-stu-id="e0064-112">Deploying the orchestration also creates a WCF-Custom send port.</span></span>  
  
  <span data-ttu-id="e0064-113">動的ポートを構成する方法の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0064-113">For more information about configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e0064-114">参照</span><span class="sxs-lookup"><span data-stu-id="e0064-114">See Also</span></span>  
[<span data-ttu-id="e0064-115">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="e0064-115">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)