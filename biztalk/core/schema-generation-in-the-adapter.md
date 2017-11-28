---
title: "アダプターではスキーマの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a><span data-ttu-id="3bbbc-102">アダプタでのスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="3bbbc-102">Schema Generation in the Adapter</span></span>
<span data-ttu-id="3bbbc-103">TIBCO Rendezvous システムには、メッセージの種類のリポジトリは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-103">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="3bbbc-104">すべてのメッセージの構築と解析は、Rendezvous アプリケーション レベルに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-104">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="3bbbc-105">この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous ではスキーマ生成機能を利用できません。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-105">Because of this limitation, Microsoft BizTalk Adapter for TIBCO Rendezvous cannot provide schema-generation capabilities.</span></span>  
  
## <a name="writing-schemas"></a><span data-ttu-id="3bbbc-106">スキーマの記述</span><span class="sxs-lookup"><span data-stu-id="3bbbc-106">Writing Schemas</span></span>  
 <span data-ttu-id="3bbbc-107">スキーマを記述して、使用する必要があります**既存項目の追加**オーケストレーションで使用できるは、インポートする Visual Studio でします。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-107">You must write a schema and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="3bbbc-108">スキーマは、BizTalk Server の開発ツールに必要で、Visual Studio での統合において非常に重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-108">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="3bbbc-109">BizTalk Server の開発者は、完全なスキーマを作成する必要はなく、最小限のスキーマやその中間のスキーマも作成できます。</span><span class="sxs-lookup"><span data-stu-id="3bbbc-109">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbbc-110">参照</span><span class="sxs-lookup"><span data-stu-id="3bbbc-110">See Also</span></span>  
 [<span data-ttu-id="3bbbc-111">作業の開始</span><span class="sxs-lookup"><span data-stu-id="3bbbc-111">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)