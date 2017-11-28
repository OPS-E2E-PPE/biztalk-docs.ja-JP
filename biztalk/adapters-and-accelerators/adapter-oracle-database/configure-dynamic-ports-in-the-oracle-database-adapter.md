---
title: "Oracle データベース アダプターの動的ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: dynamic ports, configuring
ms.assetid: c4f67707-76a0-4d72-913f-03219b412e2a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c58243ba2c953000cbccd7dc9d6c1da34889058
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dynamic-ports-in-the-oracle-database-adapter"></a><span data-ttu-id="85a3a-102">Oracle データベース アダプターの動的ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="85a3a-102">Configure dynamic ports in the Oracle Database Adapter</span></span>
<span data-ttu-id="85a3a-103">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の動的ポートを構成することができます、[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85a3a-103">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can configure dynamic ports for a [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)].</span></span> <span data-ttu-id="85a3a-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF ベース アダプターでは、用のポートを動的に構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]メッセージ コンテキスト プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="85a3a-104">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF-based adapter, you can dynamically configure a port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using message context properties.</span></span>  
  
 <span data-ttu-id="85a3a-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、URI、アクション、およびバインドのプロパティを受信メッセージから決定されで指定して可能性があります、**式**図形を次の例で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="85a3a-105">For the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the URI, action, and binding may be determined from a property on an incoming message, and then specified in the **Expression** shape, as shown in the following example:</span></span>  
  
```  
Request2=Request1;  
Request2(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select";  
Request2(WCF.BindingType)="oracleDBBinding";  
Request2(WCF.UserName)="SCOTT";  
Request2(WCF.Password)="TIGER";  
SendPort(Microsoft.XLANGs.BaseTypes.Address)="oracledb://adapdoc/";  
SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="WCF-Custom";  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="85a3a-106">Wcf-oracledb アダプターを使用しているかどうかは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、指定することも、トランスポートの種類として`SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`ここで、 **OracleDatabaseAdapter**の Wcf-oracledb アダプターを追加する名前を指定します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="85a3a-106">If you are using a WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can also specify the transport type as `SendPort(Microsoft.XLANGs.BaseTypes.TransportType)="OracleDatabaseAdapter"`, where **OracleDatabaseAdapter** is the name with which you added the WCF-OracleDB adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="85a3a-107">上記の例では、</span><span class="sxs-lookup"><span data-stu-id="85a3a-107">In the above example,</span></span>  
  
-   <span data-ttu-id="85a3a-108">Request1 メッセージから Request2 メッセージを作成しています。</span><span class="sxs-lookup"><span data-stu-id="85a3a-108">Request2 message is being created from Request1 message.</span></span> <span data-ttu-id="85a3a-109">どちらのメッセージが操作を使用して生成されるスキーマ、マップ、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="85a3a-109">Both the messages map to an operation schema, which is generated using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
-   <span data-ttu-id="85a3a-110">送信ポートは、BizTalk オーケストレーションの論理送信ポートの名前です。</span><span class="sxs-lookup"><span data-stu-id="85a3a-110">SendPort is the name of the logical send port in the BizTalk orchestration.</span></span>  
  
 <span data-ttu-id="85a3a-111">**式**図形は、BizTalk オーケストレーションの一部です。</span><span class="sxs-lookup"><span data-stu-id="85a3a-111">The **Expression** shape is part of the BizTalk orchestration.</span></span> <span data-ttu-id="85a3a-112">オーケストレーションを展開するときに、wcf-custom 送信ポートも作成されます。</span><span class="sxs-lookup"><span data-stu-id="85a3a-112">When you deploy the orchestration, the WCF-custom send port is also created.</span></span>  
  
 <span data-ttu-id="85a3a-113">動的ポートの構成の詳細については、次を参照してください。[動的送信ポートを使用して WCF アダプター コンテキスト プロパティの構成](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="85a3a-113">For more information on configuring dynamic ports, see [Configuring Dynamic Send Ports Using WCF Adapters Context Properties](../../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85a3a-114">参照</span><span class="sxs-lookup"><span data-stu-id="85a3a-114">See Also</span></span>  
[<span data-ttu-id="85a3a-115">Oracle データベースと BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="85a3a-115">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)