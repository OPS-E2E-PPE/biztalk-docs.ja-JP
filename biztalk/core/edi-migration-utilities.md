---
title: "EDI 移行ユーティリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c594811-609a-42f7-9357-c29da76be15a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5d0249b38c7bfe090528df32e8bcb6fd21f410f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-migration-utilities"></a><span data-ttu-id="a4bbb-102">EDI 移行ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="a4bbb-102">EDI Migration Utilities</span></span>
<span data-ttu-id="a4bbb-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の以前のバージョンに付属していた EDI 移行ユーティリティでは、Base EDI アプリケーションを移行して、提供された EDI ソリューションを BizTalk Server 2006 R2 または BizTalk Server 2009 の一部として使用するようにしました。</span><span class="sxs-lookup"><span data-stu-id="a4bbb-103">The EDI migration utilities shipped with previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] were used to migrate Base EDI applications to use the EDI solution provided as part of BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span> <span data-ttu-id="a4bbb-104">Base EDI アプリケーションを [!INCLUDE[prague](../includes/prague-md.md)] に直接移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4bbb-104">Migrating Base EDI applications directly to [!INCLUDE[prague](../includes/prague-md.md)] is not supported.</span></span> <span data-ttu-id="a4bbb-105">最初に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の各バージョンに付属する EDI 移行ユーティリティを使用して BizTalk Sever 2006 R2 または BizTalk Server 2009 に Base EDI アプリケーションを移行する必要があります。次に、[!INCLUDE[prague](../includes/prague-md.md)] に付属するパーティ移行ツールを使用して BizTalk Server 2006 R2 または BizTalk Server 2009 から [!INCLUDE[prague](../includes/prague-md.md)] にパーティ定義を移行します。</span><span class="sxs-lookup"><span data-stu-id="a4bbb-105">You must first migrate the Base EDI applications to BizTalk Sever 2006 R2 or BizTalk Server 2009 using the EDI migration utilities shipped with these versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and then use the Party Migration Tool shipped with [!INCLUDE[prague](../includes/prague-md.md)] to migrate the party definitions from BizTalk Server 2006 R2 or BizTalk Server 2009 to [!INCLUDE[prague](../includes/prague-md.md)].</span></span>  
  
 <span data-ttu-id="a4bbb-106">パーティ移行ツールの詳細については、次を参照してください。 [EDI アイテムを BizTalk Server の以前のバージョンから移行する](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)です。</span><span class="sxs-lookup"><span data-stu-id="a4bbb-106">For more information about the Party Migration Tool, see [Migrating EDI Artifacts from a Previous Version of BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bbb-107">参照</span><span class="sxs-lookup"><span data-stu-id="a4bbb-107">See Also</span></span>  
 [<span data-ttu-id="a4bbb-108">SDK のユーティリティ</span><span class="sxs-lookup"><span data-stu-id="a4bbb-108">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)