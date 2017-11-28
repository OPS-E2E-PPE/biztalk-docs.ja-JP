---
title: "Wcf-customisolated アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-CustomIsolated adapters
ms.assetid: 0b529992-65e4-4543-951f-61644f8315a0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734986a7ea87ff3b5a4b4a46a307d44665246b22
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-customisolated-adapter"></a><span data-ttu-id="69795-102">Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="69795-102">WCF-CustomIsolated Adapter</span></span>
<span data-ttu-id="69795-103">Wcf-customisolated アダプターを構成できる分離アダプターの受信場所、HTTP トランスポート経由で、バインディングおよび動作設定で Windows Communication Foundation (WCF) に適用される[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="69795-103">The WCF-CustomIsolated adapter is an isolated adapter to allow configuring receive locations over the HTTP transport with any binding and behavior settings for Windows Communication Foundation (WCF) that are applicable to [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="69795-104">WCF-CustomIsolated アダプタは、標準の WCF アダプタがサポートされないシナリオに対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="69795-104">You can use the WCF-CustomIsolated adapter for scenarios that the standard WCF adapters do not support.</span></span> <span data-ttu-id="69795-105">また、WCF-CustomIsolated アダプタを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で WCF の機能拡張ポイントを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="69795-105">The WCF-CustomIsolated adapter also enables you to use the WCF extensibility points in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="69795-106">WCF-CustomIsolated アダプタは、分離ホストで実行される受信場所に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="69795-106">The WCF-CustomIsolated adapter is used for the receive location running in an isolated host.</span></span> <span data-ttu-id="69795-107">WCF-CustomIsolated アダプタを使用するには、BizTalk WCF サービス公開ウィザードを使用して、Microsoft インターネット インフォメーション サービス (IIS) でこの受信場所に対応する仮想ディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69795-107">To use the WCF-CustomIsolated adapter, you must use the BizTalk WCF Service Publishing Wizard to create in Microsoft Internet Information Services (IIS) the virtual directory corresponding to this receive location.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69795-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="69795-108">In This Section</span></span>  
  
-   [<span data-ttu-id="69795-109">Wcf-customisolated アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="69795-109">What Is the WCF-CustomIsolated Adapter?</span></span>](../core/what-is-the-wcf-customisolated-adapter.md)  
  
-   [<span data-ttu-id="69795-110">Wcf-customisolated アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="69795-110">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="69795-111">参照</span><span class="sxs-lookup"><span data-stu-id="69795-111">See Also</span></span>  
 [<span data-ttu-id="69795-112">拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="69795-112">Introduction to Extensibility</span></span>](http://go.microsoft.com/fwlink/?LinkId=82590)