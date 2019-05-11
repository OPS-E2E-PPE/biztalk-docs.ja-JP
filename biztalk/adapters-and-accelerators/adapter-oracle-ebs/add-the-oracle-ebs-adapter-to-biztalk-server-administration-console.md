---
title: Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加します |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24b126aa-2a05-49fa-80e1-f1d5c21ad60f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b11a6959ecffb7447c577153104977bd90815105
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375811"
---
# <a name="add-the-oracle-e-business-suite-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="2955c-102">Oracle E-business Suite アダプターを BizTalk Server 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="2955c-102">Add the Oracle E-Business Suite adapter to BizTalk Server Administration console</span></span>
<span data-ttu-id="2955c-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] BizTalk Server で WCF カスタム ポートまたは Wcf-oracleebs ポートとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="2955c-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] can be used in BizTalk Server either as a WCF-Custom port or a WCF-OracleEBS port.</span></span> <span data-ttu-id="2955c-104">使用する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF カスタム ポートには WCF カスタム ポートを追加する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに、WCF カスタム ポートが追加されるため、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]既定では、管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2955c-104">If you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="2955c-105">ただし、使用する場合、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Wcf-oracleebs ポートを経由する Wcf-oracleebs アダプターを最初に追加する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2955c-105">However, if you want to use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] through a WCF-OracleEBS port, you must first add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="2955c-106">このトピックでは、Wcf-oracleebs アダプターを追加する方法を手順については、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2955c-106">This topic provides instructions on how to add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2955c-107">WCF カスタム ポートを構成するかどうか、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2955c-107">If you want to configure a WCF-Custom port for the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you need not perform this procedure.</span></span>  
  
### <a name="to-add-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="2955c-108">Oracle E-business Suite アダプターを追加するには</span><span class="sxs-lookup"><span data-stu-id="2955c-108">To add the Oracle E-Business Suite Adapter</span></span>  
  
1. <span data-ttu-id="2955c-109">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2955c-109">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="2955c-110">コンソール ツリーで、展開、 **BizTalk グループ**、展開**プラットフォームの設定**、 をクリックし、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="2955c-110">In the console tree, expand the **BizTalk Group**, expand **Platform Settings**, and then click **Adapters**.</span></span>  
  
3. <span data-ttu-id="2955c-111">右クリックして**アダプター**、 をポイント**新規**、 をクリック**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="2955c-111">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
    <span data-ttu-id="2955c-112">![アダプターを追加する](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="2955c-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="2955c-113">**アダプター プロパティ**] ダイアログ ボックスで、アダプターとの間の名前を指定します、**アダプター**一覧で、[ **Wcf-oracleebs**します。</span><span class="sxs-lookup"><span data-stu-id="2955c-113">In the **Adapter Properties** dialog box, specify a name for the adapter and from the **Adapter** list, select **WCF-OracleEBS**.</span></span>  
  
    <span data-ttu-id="2955c-114">![WCF の追加&#45;OracleEBS BizTalk アダプター](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span><span class="sxs-lookup"><span data-stu-id="2955c-114">![Add WCF&#45;OracleEBS adapter to BizTalk](../../adapters-and-accelerators/adapter-oracle-ebs/media/3e2cde5a-9f32-489c-a931-0dd509451e62.gif "3e2cde5a-9f32-489c-a931-0dd509451e62")</span></span>  
  
5. <span data-ttu-id="2955c-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2955c-115">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2955c-116">参照</span><span class="sxs-lookup"><span data-stu-id="2955c-116">See Also</span></span>  
 [<span data-ttu-id="2955c-117">Oracle E-business Suite のアプリケーションを作成する構成要素</span><span class="sxs-lookup"><span data-stu-id="2955c-117">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)