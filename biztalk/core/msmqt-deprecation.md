---
title: 非推奨の MSMQT |Microsoft ドキュメント
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
ms.openlocfilehash: f869dde7cb4c793e1e36beee6a20bc89d19272e8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007635"
---
# <a name="msmqt-deprecation"></a><span data-ttu-id="24795-102">非推奨の MSMQT</span><span class="sxs-lookup"><span data-stu-id="24795-102">MSMQT Deprecation</span></span>
<span data-ttu-id="24795-103">MSMQT 機能は BizTalk Server から削除されました。</span><span class="sxs-lookup"><span data-stu-id="24795-103">The MSMQT feature has been removed from BizTalk Server.</span></span> <span data-ttu-id="24795-104">オーケストレーション デザイナーで、MSMQT トランスポート オプションは、デザイン時のポート構成ウィザードを選択すると次の図に示すように、**今指定**オプションを**ポートのバインド**.</span><span class="sxs-lookup"><span data-stu-id="24795-104">In Orchestration Designer, the MSMQT transport option remains available in the design-time Port Configuration Wizard as shown in the image below when you choose the **Specify now** option for **Port binding**.</span></span>  
  
 <span data-ttu-id="24795-105">**MSMQT トランスポートを示すポート構成ウィザード**</span><span class="sxs-lookup"><span data-stu-id="24795-105">**Port Configuration Wizard showing MSMQT transport**</span></span>  
  
 <span data-ttu-id="24795-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span><span class="sxs-lookup"><span data-stu-id="24795-106">![](../core/media/portconfigurationwizard-msmqt-transport.gif "PortConfigurationWizard_MSMQT_Transport")</span></span>  
  
## <a name="biztalk-server-projects"></a><span data-ttu-id="24795-107">BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="24795-107">BizTalk Server Projects</span></span>  
 <span data-ttu-id="24795-108">新しい [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトでは MSMQT トランスポート オプションを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="24795-108">New [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] projects should not use the MSMQT transport option.</span></span> <span data-ttu-id="24795-109">BizTalk Server にアプリケーションの展開は、エラーで失敗**プロトコルの種類"MSMQT"が見つかりません。** です。</span><span class="sxs-lookup"><span data-stu-id="24795-109">Application deployment to BizTalk Server will fail with the error **Protocol type “MSMQT” not found**.</span></span>  
  
## <a name="migrated-biztalk-server-projects"></a><span data-ttu-id="24795-110">移行済み BizTalk Server プロジェクト</span><span class="sxs-lookup"><span data-stu-id="24795-110">Migrated BizTalk Server Projects</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="24795-111">使用して BizTalk Server にプロジェクトを移行できる、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]変換ウィザードで説明するように[BizTalk Server プロジェクトを移行する](../core/migrating-a-biztalk-server-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="24795-111"> projects can be migrated to BizTalk Server by using the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Conversion Wizard as documented in [Migrating a BizTalk Server Project](../core/migrating-a-biztalk-server-project.md).</span></span> <span data-ttu-id="24795-112">MSMQT トランスポートを使用するように構成するポートを含むプロジェクトは、BizTalk Server に展開する前に手動で再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24795-112">Projects containing ports configured to use the MSMQT transport must be manually reconfigured before deployment to BizTalk Server.</span></span> <span data-ttu-id="24795-113">推奨される再構成は、MSMQ アダプターを使用する構成です。</span><span class="sxs-lookup"><span data-stu-id="24795-113">The recommended reconfiguration is to use the MSMQ adapter.</span></span>  <span data-ttu-id="24795-114">MSMQ アダプターの詳細については、次を参照してください。 [MSMQ アダプターは何ですか?](../core/what-is-the-msmq-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="24795-114">For more information about the MSMQ adapter see [What Is the MSMQ Adapter?](../core/what-is-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24795-115">参照</span><span class="sxs-lookup"><span data-stu-id="24795-115">See Also</span></span>  
 [<span data-ttu-id="24795-116">MSMQT アダプターから MSMQ アダプターへの移行</span><span class="sxs-lookup"><span data-stu-id="24795-116">Migrating from the MSMQT Adapter to the MSMQ Adapter</span></span>](../core/migrating-from-the-msmqt-adapter-to-the-msmq-adapter.md)