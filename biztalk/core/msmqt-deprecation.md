---
title: "非推奨の MSMQT |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7095c73cd337a1fb08f2d867e817ad5838206
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="5105b-102">非推奨の MSMQT</span><span class="sxs-lookup"><span data-stu-id="5105b-102">MSMQT Deprecation</span></span>
<span data-ttu-id="5105b-103">MSMQT 機能は BizTalk Server から削除されました。</span><span class="sxs-lookup"><span data-stu-id="5105b-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="5105b-104">オーケストレーション デザイナーで、MSMQT トランスポート オプションは、デザイン時のポート構成ウィザードを選択すると次の図に示すように、**今指定**オプションを**ポートのバインド**.</span><span class="sxs-lookup"><span data-stu-id="5105b-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="5105b-105">**MSMQT トランスポートを示すポート構成ウィザード**</span><span class="sxs-lookup"><span data-stu-id="5105b-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 ![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="5105b-106">BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="5105b-106">BizTalk Server Projects</span></span>  
 <span data-ttu-id="5105b-107">新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトでは MSMQT トランスポート オプションを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5105b-107">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="5105b-108">アプリケーション展開[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]は、エラーで失敗**プロトコルの種類"MSMQT"が見つかりません。**です。</span><span class="sxs-lookup"><span data-stu-id="5105b-108">Application deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="5105b-109">移行済み BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="5105b-109">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5105b-110">プロジェクトに移行できる[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]を使用して、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に記載されている変換ウィザード[BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="5105b-110"> projects can be migrated to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="5105b-111">MSMQT トランスポートを使用するように構成されたポートを含むプロジェクトは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] への展開の前に手動で再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5105b-111">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="5105b-112">推奨される再構成は、MSMQ アダプターを使用する構成です。</span><span class="sxs-lookup"><span data-stu-id="5105b-112">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="5105b-113">MSMQ アダプターの詳細については、次を参照してください。 [MSMQ アダプターは何ですか?](../core/what-is-the-msmq-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="5105b-113">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5105b-114">参照</span><span class="sxs-lookup"><span data-stu-id="5105b-114">See Also</span></span>  
 [<span data-ttu-id="5105b-115">MSMQT アダプターから MSMQ アダプターへの移行</span><span class="sxs-lookup"><span data-stu-id="5105b-115">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)