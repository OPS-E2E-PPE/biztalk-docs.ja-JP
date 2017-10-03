---
title: "管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, TIBCO Rendezvous adapters
- TIBCO Rendezvous adapters, schemas
ms.assetid: 620e7c52-8938-4199-8105-a43c161bff5e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60beb4adfaeb08dcb5bb95eceb87a7a1b0dedb11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="management"></a><span data-ttu-id="d9e78-102">管理</span><span class="sxs-lookup"><span data-stu-id="d9e78-102">Management</span></span>
<span data-ttu-id="d9e78-103">TIBCO Rendezvous はメタデータ リポジトリを備えておらず、Microsoft BizTalk Adapter for TIBCO Rendezvous 管理アセンブリは参照機能またはスキーマ生成機能を備えていません。</span><span class="sxs-lookup"><span data-stu-id="d9e78-103">TIBCO Rendezvous does not provide metadata repositories, and Microsoft BizTalk Adapter for TIBCO Rendezvous management assembly does not provide browsing capabilities or schema generation.</span></span> <span data-ttu-id="d9e78-104">したがって、ユーザーがスキーマを BizTalk Server に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9e78-104">Therefore, you must provide a schema to BizTalk Server.</span></span> <span data-ttu-id="d9e78-105">詳細については、次を参照してください。[アダプターではスキーマの生成](../core/schema-generation-in-the-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9e78-105">For more information, see [Schema Generation in the Adapter](../core/schema-generation-in-the-adapter.md).</span></span>  
  
 <span data-ttu-id="d9e78-106">BizTalk Adapter for TIBCO Rendezvous には定義済みの型のスキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9e78-106">BizTalk Adapter for TIBCO Rendezvous includes a schema with predefined types.</span></span> <span data-ttu-id="d9e78-107">アダプターは、一部の特定のデータ型 (配列) のメッセージを生成するときに、これらの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e78-107">The adapter uses these types when generating messages for some specific data types (arrays).</span></span> <span data-ttu-id="d9e78-108">詳細については、次を参照してください。 [BizTalk Server のメッセージ コンテキスト プロパティ (送信ハンドラー)](../core/biztalk-server-message-context-properties-send-handlers.md)です。</span><span class="sxs-lookup"><span data-stu-id="d9e78-108">For more information, see [BizTalk Server Message Context Properties (Send Handlers)](../core/biztalk-server-message-context-properties-send-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e78-109">参照</span><span class="sxs-lookup"><span data-stu-id="d9e78-109">See Also</span></span>  
 [<span data-ttu-id="d9e78-110">TIBCO Rendezvous 送信ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9e78-110">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)