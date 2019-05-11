---
title: BizTalk Server 2013 および 2013 R2 へのアップグレード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, BizTalk Server
- deploying [BizTalk Server], upgrading
- BizTalk Server, upgrading
- upgrading
ms.assetid: acb0a96e-091b-45c3-8d41-affe9ffcf134
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd8b2eda26ff6de37288612db55815d27020c34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401448"
---
# <a name="upgrade-to-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="592a5-102">2013 R2 および BizTalk Server 2013 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="592a5-102">Upgrade to BizTalk Server 2013 and 2013 R2</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="592a5-103">以前のバージョンから簡単にアップグレードできるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="592a5-103">is designed to allow for an easy upgrade experience from previous versions.</span></span> <span data-ttu-id="592a5-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 および 2013 R2 のアップグレード ガイドは、「[関連する BizTalk Server 2013 インストール ガイド](http://www.microsoft.com/download/details.aspx?id=35552)します。</span><span class="sxs-lookup"><span data-stu-id="592a5-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2013 and 2013 R2 Upgrade Guide is available at [Installation Guides Related to BizTalk Server 2013](http://www.microsoft.com/download/details.aspx?id=35552).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="592a5-105">アップグレードを実行するときに、スキーマの圧縮ファイルが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="592a5-105">The compressed file of schemas will be replaced when an upgrade is performed.</span></span> <span data-ttu-id="592a5-106">Microsoft をアップグレードする場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に関連付けられた MicrosoftEdiXSDTemplates.exe ファイルを (たとえば、製品のリリース版にベータ版) から新しいビルド、インストール内の MicrosoftEdiXSDTemplates.exe ファイルが置き換えられますアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="592a5-106">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build (for example, from a beta version to the retail release version), the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="592a5-107">引き続き古い圧縮ファイルからスキーマを使用する場合は、不要になったアクセスことは、圧縮ファイルに、アップグレード後に古い圧縮ファイルをバックアップする場合を除き。</span><span class="sxs-lookup"><span data-stu-id="592a5-107">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span> <span data-ttu-id="592a5-108">詳細については、次を参照してください。 **EDI スキーマのインストール**で[構成後の手順、環境を最適化する](post-configuration-steps-to-optimize-your-environment.md)します。</span><span class="sxs-lookup"><span data-stu-id="592a5-108">For more information, see **Install EDI schemas** at [Post-configuration steps to optimize your environment](post-configuration-steps-to-optimize-your-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="592a5-109">参照</span><span class="sxs-lookup"><span data-stu-id="592a5-109">See Also</span></span>  
[<span data-ttu-id="592a5-110">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="592a5-110">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)