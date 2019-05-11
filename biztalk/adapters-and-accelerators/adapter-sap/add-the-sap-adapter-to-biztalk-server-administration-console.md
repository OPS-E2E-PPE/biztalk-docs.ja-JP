---
title: SAP アダプターを BizTalk Server 管理コンソールに追加します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95fc925d-0aac-4f0d-a19d-ad27469e4b3c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019edf01b4635777a91ac00efa0e2facebc7d1c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374267"
---
# <a name="add-the-sap-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="3c530-102">SAP アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="3c530-102">Add the SAP Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="3c530-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Biztalk WCF カスタム ポートまたは WCF SAP ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="3c530-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SAP port.</span></span> <span data-ttu-id="3c530-104">使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c530-104">If you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="3c530-105">ただし、使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF-SAP ポートを通じて、WCF-SAP アダプターを追加する必要があります最初、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c530-105">However, if you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] through a WCF-SAP port, you must first add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="3c530-106">このトピックでは、WCF-SAP アダプターを追加する方法を手順については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c530-106">This topic provides instructions on how to add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c530-107">WCF カスタム ポートを構成する場合これらのタスクを実行する必要ありません、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c530-107">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="add-the-sap-adapter"></a><span data-ttu-id="3c530-108">SAP アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="3c530-108">Add the SAP Adapter</span></span>  
  
1. <span data-ttu-id="3c530-109">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="3c530-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="3c530-110">コンソール ツリーで、展開、 **BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="3c530-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="3c530-111">右クリックして**アダプター**、 をポイント**新規**、 をクリック**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="3c530-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="3c530-112">![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="3c530-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="3c530-113">**アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を指定します、**アダプター**一覧で、[ **WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="3c530-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-SAP**.</span></span>  
  
    <span data-ttu-id="3c530-114">![SAP アダプターを BizTalk に追加](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="3c530-114">![Add SAP Adapter to BizTalk](../../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  
  
5. <span data-ttu-id="3c530-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c530-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c530-116">参照</span><span class="sxs-lookup"><span data-stu-id="3c530-116">See Also</span></span>  
[<span data-ttu-id="3c530-117">SAP アプリケーションを作成するための構成要素</span><span class="sxs-lookup"><span data-stu-id="3c530-117">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)