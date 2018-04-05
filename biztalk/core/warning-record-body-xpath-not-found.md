---
title: 警告 - レコードのボディ XPath が見つかりません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.recordBodyXPathNotFound
ms.assetid: d46e0732-08ce-4292-84d8-56dc020063e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd6640aa469fe9383b615d70235ab488c8798f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---record-body-xpath-not-found"></a><span data-ttu-id="8d820-102">警告 - レコードのボディ XPath が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="8d820-102">Warning - Record Body XPath Not Found</span></span>
<span data-ttu-id="8d820-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="8d820-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8d820-104">BEC1008</span><span class="sxs-lookup"><span data-stu-id="8d820-104">BEC1008</span></span>  
  
 <span data-ttu-id="8d820-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="8d820-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8d820-106">**ボディ XPath**空にするこのエンベロープ スキーマに含まれているルート ノードのプロパティが見つかりましたまたは存在しないノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="8d820-106">The **Body XPath** property of the indicated root node in this envelope schema was found to be empty or referencing a nonexistent node.</span></span> <span data-ttu-id="8d820-107">指定したとおり、エンベロープ スキーマ、**エンベロープ**のプロパティ、**スキーマ**ノード、有効な値を設定するために必要な**ボディ XPath**指定されたルートのプロパティスキーマ内のノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="8d820-107">Envelope schemas, as specified by the **Envelope** property of the **Schema** node, are required to have a valid value in the **Body XPath** property of the specified root reference node in the schema.</span></span>  
  
 <span data-ttu-id="8d820-108">ルート参照ノードが指定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノード、スキーマでは、既定のルート参照ノードの最初のルート ノードがそので有効な値を設定する必要が**ボディ XPath**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8d820-108">If no root reference node is specified by the **Root Reference** property of the **Schema** node, the first root node in the schema, the default root reference node, is required to have a valid value in its **Body XPath** property.</span></span> <span data-ttu-id="8d820-109">**ボディ XPath**プロパティ値をエンベロープ内のメッセージの各スキーマの識別に使用します。</span><span class="sxs-lookup"><span data-stu-id="8d820-109">**Body XPath** property values are used to identify the schema for the each of the messages contained within the envelope.</span></span>  
  
 <span data-ttu-id="8d820-110">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="8d820-110">**User Action**</span></span>  
  
 <span data-ttu-id="8d820-111">対象のルート ノードを選択し、値を選択、**ボディ XPath**正しく関連付けられているメッセージ本文のスキーマを識別するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8d820-111">Select the indicated root node and then select the value for the **Body XPath** property that correctly identifies the schema of the associated message body.</span></span>