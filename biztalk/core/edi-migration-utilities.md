---
title: EDI 移行ユーティリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c594811-609a-42f7-9357-c29da76be15a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0612d940651215564bcf660186314480a5642832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005083"
---
# <a name="edi-migration-utilities"></a><span data-ttu-id="024bb-102">EDI 移行ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="024bb-102">EDI Migration Utilities</span></span>
<span data-ttu-id="024bb-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の以前のバージョンに付属していた EDI 移行ユーティリティでは、Base EDI アプリケーションを移行して、提供された EDI ソリューションを BizTalk Server 2006 R2 または BizTalk Server 2009 の一部として使用するようにしました。</span><span class="sxs-lookup"><span data-stu-id="024bb-103">The EDI migration utilities shipped with previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] were used to migrate Base EDI applications to use the EDI solution provided as part of BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span> <span data-ttu-id="024bb-104">ベース EDI を移行する BizTalk Server に直接アプリケーションはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="024bb-104">Migrating Base EDI applications directly to BizTalk Server is not supported.</span></span> <span data-ttu-id="024bb-105">BizTalk Sever 2006 R2 またはこれらのバージョンに付属する EDI 移行ユーティリティを使用して BizTalk Server 2009 に Base EDI アプリケーションを移行する必要がありますまず[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、BizTalk Server に付属するパーティ移行ツールを使用して、パーティの移行BizTalk Server 2006 R2 または BizTalk Server 2009 から BizTalk Server に定義します。</span><span class="sxs-lookup"><span data-stu-id="024bb-105">You must first migrate the Base EDI applications to BizTalk Sever 2006 R2 or BizTalk Server 2009 using the EDI migration utilities shipped with these versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and then use the Party Migration Tool shipped with BizTalk Server to migrate the party definitions from BizTalk Server 2006 R2 or BizTalk Server 2009 to BizTalk Server.</span></span>  
  
 <span data-ttu-id="024bb-106">パーティ移行ツールの詳細については、次を参照してください。 [EDI アイテムを BizTalk Server の以前のバージョンから移行する](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)です。</span><span class="sxs-lookup"><span data-stu-id="024bb-106">For more information about the Party Migration Tool, see [Migrating EDI Artifacts from a Previous Version of BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024bb-107">参照</span><span class="sxs-lookup"><span data-stu-id="024bb-107">See Also</span></span>  
 [<span data-ttu-id="024bb-108">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="024bb-108">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)