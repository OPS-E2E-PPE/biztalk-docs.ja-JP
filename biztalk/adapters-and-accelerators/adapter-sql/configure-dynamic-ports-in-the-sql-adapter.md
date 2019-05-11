---
title: SQL アダプターで動的ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98b66ed-0bf7-4b24-9d16-9792d033b818
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c4f9cba33b8e26287fa7be424c0376a60333bf7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369954"
---
# <a name="configure-dynamic-ports-in-the-sql-adapter"></a><span data-ttu-id="69bf3-102">SQL アダプターで動的ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-102">Configure dynamic ports in the SQL adapter</span></span>
<span data-ttu-id="69bf3-103">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="69bf3-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]メッセージ コンテキスト プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="69bf3-104">Because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by using message context properties.</span></span>  

## <a name="use-an-expression-shape"></a><span data-ttu-id="69bf3-105">式図形を使用します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-105">Use an expression shape</span></span>  
 <span data-ttu-id="69bf3-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、URI、アクション、およびバインド、受信メッセージのプロパティから決定されで指定された可能性があります、**式**図形、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="69bf3-106">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="TableOp/Insert/dbo/CustomerTable";  
Request2(WCF.BindingType)="sqlBinding";  
Request2(WCF.UserName)="myuser";  
Request2(WCF.Password)="mypass";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="mssql://sql_server/my_instance/my_database";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="69bf3-107">WCF-SQL アダプターを使用しているかどうか[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、トランスポートの種類としても指定できます`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`ここで、 **SQLAdapter**の WCF-SQL アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="69bf3-107">If you are using a WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="SQLAdapter"`, where **SQLAdapter** is the name with which you added the WCF-SQL adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="69bf3-108">前の例では、</span><span class="sxs-lookup"><span data-stu-id="69bf3-108">In the preceding example,</span></span>  
  
- <span data-ttu-id="69bf3-109">Request1 メッセージから Request2 メッセージを作成しています。</span><span class="sxs-lookup"><span data-stu-id="69bf3-109">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="69bf3-110">両方のメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-110">Both messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
- <span data-ttu-id="69bf3-111">送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="69bf3-111">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
  <span data-ttu-id="69bf3-112">**式**図形は、BizTalk オーケストレーションの一部です。</span><span class="sxs-lookup"><span data-stu-id="69bf3-112">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="69bf3-113">オーケストレーションを展開すると、Wcf-custom 送信ポートも作成します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-113">Deploying the orchestration also creates a WCF-Custom send port.</span></span>  
  
  <span data-ttu-id="69bf3-114">動的ポートを構成する方法の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="69bf3-114">For more information about configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="69bf3-115">参照</span><span class="sxs-lookup"><span data-stu-id="69bf3-115">See Also</span></span>  
[<span data-ttu-id="69bf3-116">SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="69bf3-116">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)