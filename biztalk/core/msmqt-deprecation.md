---
title: 非推奨の MSMQT |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 007d65ce-d2a2-4602-80c8-55b26617f397
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a54e775d9a7f683b11440f1d6ad0e43bdbecb43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263640"
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="e9f66-102">非推奨の MSMQT</span><span class="sxs-lookup"><span data-stu-id="e9f66-102">MSMQT Deprecation</span></span>
<span data-ttu-id="e9f66-103">MSMQT 機能は BizTalk Server から削除されました。</span><span class="sxs-lookup"><span data-stu-id="e9f66-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="e9f66-104">オーケストレーション デザイナーでは MSMQT トランスポート オプションは選択すると次の図で示すようにデザイン時のポート構成ウィザードで使用できる、**今指定する**オプション**ポートのバインド**.</span><span class="sxs-lookup"><span data-stu-id="e9f66-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="e9f66-105">**MSMQT トランスポートを示すポート構成ウィザード**</span><span class="sxs-lookup"><span data-stu-id="e9f66-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 <span data-ttu-id="e9f66-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span><span class="sxs-lookup"><span data-stu-id="e9f66-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span></span>  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="e9f66-107">BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="e9f66-107">BizTalk Server Projects</span></span>  
 <span data-ttu-id="e9f66-108">新しい[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトでは、MSMQT トランスポート オプションを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e9f66-108">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="e9f66-109">アプリケーションの展開を BizTalk Server は、エラーで失敗**プロトコルの種類"MSMQT"が見つかりません。** します。</span><span class="sxs-lookup"><span data-stu-id="e9f66-109">Application deployment to BizTalk Server will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="e9f66-110">移行済み BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="e9f66-110">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e9f66-111">プロジェクトを使用して BizTalk Server に移行できる、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に記載されている変換ウィザード[BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9f66-111">projects can be migrated to BizTalk Server by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="e9f66-112">MSMQT トランスポートを使用するように構成するポートを含むプロジェクトは、BizTalk Server に展開する前に手動で再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9f66-112">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to BizTalk Server.</span></span> <span data-ttu-id="e9f66-113">推奨される再構成では、MSMQ アダプターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9f66-113">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="e9f66-114">MSMQ アダプターの詳細については、次を参照してください。 [MSMQ アダプターとは何ですか?](../core/what-is-the-msmq-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="e9f66-114">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f66-115">参照</span><span class="sxs-lookup"><span data-stu-id="e9f66-115">See Also</span></span>  
 [<span data-ttu-id="e9f66-116">MSMQT アダプターから MSMQ アダプターへの移行</span><span class="sxs-lookup"><span data-stu-id="e9f66-116">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)