---
title: BizTalk エンドポイントを公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e8cc81-c6c7-4269-81e3-8725082a0c98
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f24dbdb80e284602d6c02ce7234f51c7c7f94048
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301847"
---
# <a name="publishing-biztalk-endpoints"></a><span data-ttu-id="e2bbe-102">BizTalk エンドポイントを公開します。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-102">Publishing BizTalk Endpoints</span></span>
<span data-ttu-id="e2bbe-103">ESB 管理ポータルを使用して、作成して、現在構成されている Universal Description, Discovery, and Integration (UDDI) サーバーへのエントリを発行することができます。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-103">You can use the ESB Management Portal to create and publish entries into the currently configured Universal Description, Discovery, and Integration (UDDI) server.</span></span>  
  
### <a name="to-publish-a-microsoft-biztalk-server-endpoint-into-the-current-uddi-server"></a><span data-ttu-id="e2bbe-104">現在の UDDI サーバーに Microsoft BizTalk Server のエンドポイントを公開するには</span><span class="sxs-lookup"><span data-stu-id="e2bbe-104">To publish a Microsoft BizTalk Server endpoint into the current UDDI server</span></span>  
  
1.  <span data-ttu-id="e2bbe-105">ポイントして、**レジストリ**ポータルのメイン メニューで、タブをクリックして**新しいレジストリ エントリ**を開く、[新しいレジストリ エントリ ページ](../esb-toolkit/new-registry-entry-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-105">Point to the **Registry** tab on the portal main menu, and then click **New Registry Entry** to open the [New Registry Entry Page](../esb-toolkit/new-registry-entry-page.md).</span></span>  
  
2.  <span data-ttu-id="e2bbe-106">ページのドロップダウン リストを使用して、エンドポイントが存在する場所をエンドポイントの種類、状態、およびアプリケーションでフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-106">Use the drop-down lists on the page to filter on the endpoint type, the status, and the application where the endpoint resides.</span></span>  
  
3.  <span data-ttu-id="e2bbe-107">UDDI 登録要求を発行するエンドポイントの横にある矢印アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-107">Click the arrow icon next to the endpoint you want to publish to create a UDDI registration request.</span></span>  
  
4.  <span data-ttu-id="e2bbe-108">管理者がエンドポイントの自動発行を有効な場合、ポータルは自動的に UDDI サーバーに新しいエントリを公開します。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-108">If an administrator has enabled auto-publishing of endpoints, the portal automatically publishes the new entry into the UDDI server.</span></span>  
  
5.  <span data-ttu-id="e2bbe-109">管理者は、エンドポイントの自動発行を有効になっていませんでは、管理者が承認または要求を拒否するまで、要求がキューに残ります。</span><span class="sxs-lookup"><span data-stu-id="e2bbe-109">If an administrator has not enabled auto-publishing of endpoints, the requests remains in the queue until an administrator approves or declines the request.</span></span>