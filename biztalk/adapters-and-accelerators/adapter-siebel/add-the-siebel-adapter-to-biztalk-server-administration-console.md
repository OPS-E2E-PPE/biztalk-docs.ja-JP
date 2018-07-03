---
title: Siebel アダプターを BizTalk Server 管理コンソールに追加します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b64d0bdc-ac83-46c9-b27d-625088a013d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f8c30567849a0342432cb53e0c2de7959c175c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967427"
---
# <a name="add-the-siebel-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="c1afb-102">Siebel アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-102">Add the Siebel Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="c1afb-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Biztalk WCF カスタム ポートまたは Wcf-siebel ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1afb-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="c1afb-104">使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c1afb-104">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="c1afb-105">ただし、使用する場合、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Wcf-siebel ポートを経由する Wcf-siebel アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c1afb-105">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="c1afb-106">このトピックでは、Wcf-siebel アダプターを追加する方法を手順については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c1afb-106">This topic provides instructions on how to add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c1afb-107">WCF カスタム ポートを構成する場合これらのタスクを実行する必要ありません、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="add-the-siebel-adapter"></a><span data-ttu-id="c1afb-108">Siebel アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-108">Add the Siebel adapter</span></span>  
  
1. <span data-ttu-id="c1afb-109">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="c1afb-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="c1afb-110">コンソール ツリーで、展開、 **BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="c1afb-111">右クリックして**アダプター**、 をポイント**新規**、 をクリック**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="c1afb-112">![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="c1afb-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="c1afb-113">**アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を指定します、**アダプター**一覧で、[ **Wcf-siebel**します。</span><span class="sxs-lookup"><span data-stu-id="c1afb-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-Siebel**.</span></span>  
  
    <span data-ttu-id="c1afb-114">![WCF の追加&#45;BizTalk コンソールへの Siebel アダプター](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span><span class="sxs-lookup"><span data-stu-id="c1afb-114">![Add WCF&#45;Siebel adapter to BizTalk console](../../adapters-and-accelerators/adapter-siebel/media/6d39b874-2233-452a-81ef-d93274b0784c.gif "6d39b874-2233-452a-81ef-d93274b0784c")</span></span>  
  
5. <span data-ttu-id="c1afb-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1afb-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1afb-116">参照</span><span class="sxs-lookup"><span data-stu-id="c1afb-116">See Also</span></span>  
[<span data-ttu-id="c1afb-117">Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="c1afb-117">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)