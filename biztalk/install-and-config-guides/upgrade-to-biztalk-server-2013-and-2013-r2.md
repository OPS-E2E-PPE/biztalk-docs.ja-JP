---
title: "BizTalk Server 2013 および 2013 R2 へのアップグレード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, BizTalk Server
- deploying [BizTalk Server], upgrading
- BizTalk Server, upgrading
- upgrading
ms.assetid: acb0a96e-091b-45c3-8d41-affe9ffcf134
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97337438ca6be06b542baf61ad8d26fa2045180a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="71581-102">BizTalk Server 2013 および 2013 R2 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="71581-102">Upgrade to BizTalk Server 2013 and 2013 R2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="71581-103"> は、以前のバージョンから簡単にアップグレードできるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="71581-103"> is designed to allow for an easy upgrade experience from previous versions.</span></span> <span data-ttu-id="71581-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 および 2013 R2 のアップグレード ガイドは、「[BizTalk Server 2013 に関連するインストール ガイド](http://www.microsoft.com/download/details.aspx?id=35552)」でご覧いただけます。</span><span class="sxs-lookup"><span data-stu-id="71581-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 and 2013 R2 Upgrade Guide is available at [Installation Guides Related to BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71581-105">アップグレードを実行すると、スキーマの圧縮ファイルが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="71581-105">The compressed file of schemas will be replaced when an upgrade is performed.</span></span> <span data-ttu-id="71581-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を新しいビルドにアップグレードするとき (ベータ版からリテール リリース バージョンにアップグレードするときなど)、環境内の MicrosoftEdiXSDTemplates.exe ファイルが、アップグレードに関連付けられた MicrosoftEdiXSDTemplates.exe ファイルに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="71581-106">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build (for example, from a beta version to the retail release version), the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="71581-107">古い圧縮ファイルのスキーマを引き続き使用する場合は、古い圧縮ファイルをバックアップしない限り、アップグレード後、圧縮ファイルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="71581-107">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span> <span data-ttu-id="71581-108">詳細については、次を参照してください。**インストール EDI スキーマ**で[、環境を最適化するために後の構成手順](post-configuration-steps-to-optimize-your-environment.md)です。</span><span class="sxs-lookup"><span data-stu-id="71581-108">For more information, see **Install EDI schemas** at [Post-configuration steps to optimize your environment](post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="71581-109">参照</span><span class="sxs-lookup"><span data-stu-id="71581-109">See Also</span></span>  
[<span data-ttu-id="71581-110">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="71581-110">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)