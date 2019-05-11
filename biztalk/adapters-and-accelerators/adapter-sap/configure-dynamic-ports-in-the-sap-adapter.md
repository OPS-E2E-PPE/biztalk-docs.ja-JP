---
title: SAP アダプターの動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports, configuring
- configuring, dynamic ports
ms.assetid: 4d6569f9-e513-47f3-b2c1-4c21bafb2bf2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b2f02382c9b6825b91c802bf1fcb6d669284dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373868"
---
# <a name="configure-dynamic-ports-in-the-sap-adapter"></a><span data-ttu-id="40da3-102">SAP アダプターの動的ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="40da3-102">Configure dynamic ports in the SAP adapter</span></span>
## <a name="use-message-context-properties"></a><span data-ttu-id="40da3-103">メッセージ コンテキスト プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="40da3-103">Use message context properties</span></span>
<span data-ttu-id="40da3-104">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40da3-104">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="40da3-105">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージ コンテキスト プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="40da3-105">Because [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="40da3-106">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]URI、アクション、およびバインドのプロパティを受信メッセージから決定され、式図形で指定されたし、次の例に示すように可能性があります。</span><span class="sxs-lookup"><span data-stu-id="40da3-106">For the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], the URI, action, and binding might be determined from a property on an incoming message, and then specified in the Expression shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET";  
Request2(WCF.BindingType)="sapBinding";  
Request2(WCF.UserName)="YourUserName";  
Request2(WCF.Password)="YourPassword";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="sap://CLIENT=800;LANG=EN;@A/YourSAPHost/00";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="40da3-107">WCF-SAP アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`ここで、 **SAPAdapter**の WCF-SAP アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="40da3-107">If you are using a WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SAPAdapter"`, where **SAPAdapter** is the name with which you added the WCF-SAP adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="40da3-108">前の例。</span><span class="sxs-lookup"><span data-stu-id="40da3-108">In the preceding example:</span></span>  
  
- <span data-ttu-id="40da3-109">Request1 メッセージから Request2 メッセージを作成しています。</span><span class="sxs-lookup"><span data-stu-id="40da3-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="40da3-110">どちらのメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40da3-110">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
- <span data-ttu-id="40da3-111">送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="40da3-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="40da3-112">式図形には、BizTalk オーケストレーションの一部です。</span><span class="sxs-lookup"><span data-stu-id="40da3-112">The Expression shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="40da3-113">オーケストレーションを展開するときに、Wcf-custom 送信ポートも作成されます。</span><span class="sxs-lookup"><span data-stu-id="40da3-113">When you deploy the orchestration, the WCF-Custom send port is also created.</span></span>  
  
  <span data-ttu-id="40da3-114">動的ポートの構成の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="40da3-114">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40da3-115">参照</span><span class="sxs-lookup"><span data-stu-id="40da3-115">See Also</span></span>  
[<span data-ttu-id="40da3-116">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="40da3-116">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)