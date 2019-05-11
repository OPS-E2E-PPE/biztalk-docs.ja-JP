---
title: Wcf-customisolated アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters
ms.assetid: 0b529992-65e4-4543-951f-61644f8315a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56bb02f99aaebf4e301239c26cfcf9f6e6c21c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399406"
---
# <a name="wcf-customisolated-adapter"></a><span data-ttu-id="e6861-102">Wcf-customisolated アダプター</span><span class="sxs-lookup"><span data-stu-id="e6861-102">WCF-CustomIsolated Adapter</span></span>
<span data-ttu-id="e6861-103">Wcf-customisolated アダプターは分離アダプターの構成を許可する HTTP トランスポート経由でのバインドおよび動作の設定で Windows Communication Foundation (WCF) に適用される場所を受信する[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e6861-103">The WCF-CustomIsolated adapter is an isolated adapter to allow configuring receive locations over the HTTP transport with any binding and behavior settings for Windows Communication Foundation (WCF) that are applicable to [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e6861-104">Wcf-customisolated アダプターを使用して、標準の WCF アダプターがサポートされないシナリオのことができます。</span><span class="sxs-lookup"><span data-stu-id="e6861-104">You can use the WCF-CustomIsolated adapter for scenarios that the standard WCF adapters do not support.</span></span> <span data-ttu-id="e6861-105">Wcf-customisolated アダプターでは WCF の拡張ポイントを使用することもできます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e6861-105">The WCF-CustomIsolated adapter also enables you to use the WCF extensibility points in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e6861-106">Wcf-customisolated アダプターは、分離ホストで実行されている受信場所に対して使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6861-106">The WCF-CustomIsolated adapter is used for the receive location running in an isolated host.</span></span> <span data-ttu-id="e6861-107">Wcf-customisolated アダプタを使用して、仮想 Microsoft インターネット インフォメーション サービス (IIS) を作成する、BizTalk WCF サービス公開ウィザードを使用する必要がありますこれに対応するディレクトリの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="e6861-107">To use the WCF-CustomIsolated adapter, you must use the BizTalk WCF Service Publishing Wizard to create in Microsoft Internet Information Services (IIS) the virtual directory corresponding to this receive location.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6861-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e6861-108">In This Section</span></span>  
  
-   [<span data-ttu-id="e6861-109">WCF-CustomIsolated アダプターについて</span><span class="sxs-lookup"><span data-stu-id="e6861-109">What Is the WCF-CustomIsolated Adapter?</span></span>](../core/what-is-the-wcf-customisolated-adapter.md)  
  
-   [<span data-ttu-id="e6861-110">WCF-CustomIsolated アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="e6861-110">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6861-111">参照</span><span class="sxs-lookup"><span data-stu-id="e6861-111">See Also</span></span>  
 [<span data-ttu-id="e6861-112">拡張機能の概要</span><span class="sxs-lookup"><span data-stu-id="e6861-112">Introduction to Extensibility</span></span>](http://go.microsoft.com/fwlink/?LinkId=82590)