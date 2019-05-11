---
title: 警告 - レコードのボディ XPath が見つかりません |。Microsoft Docs
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
ms.openlocfilehash: a651748c16862bbb3a23b3e792c0ab17fc3687f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393646"
---
# <a name="warning---record-body-xpath-not-found"></a><span data-ttu-id="45acf-102">警告 - レコードのボディ XPath が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="45acf-102">Warning - Record Body XPath Not Found</span></span>
<span data-ttu-id="45acf-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="45acf-103">**Error Code**</span></span>  
  
 <span data-ttu-id="45acf-104">BEC1008</span><span class="sxs-lookup"><span data-stu-id="45acf-104">BEC1008</span></span>  
  
 <span data-ttu-id="45acf-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="45acf-105">**Explanation**</span></span>  
  
 <span data-ttu-id="45acf-106">**ボディ XPath**空にするこのエンベロープ スキーマに含まれているルート ノードのプロパティが見つかりました。 または、存在しないノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="45acf-106">The **Body XPath** property of the indicated root node in this envelope schema was found to be empty or referencing a nonexistent node.</span></span> <span data-ttu-id="45acf-107">指定したとおり、エンベロープ スキーマ、**エンベロープ**のプロパティ、**スキーマ**ノード有効な値を設定するために必要な**ボディ XPath**指定したルートのプロパティスキーマ内のノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="45acf-107">Envelope schemas, as specified by the **Envelope** property of the **Schema** node, are required to have a valid value in the **Body XPath** property of the specified root reference node in the schema.</span></span>  
  
 <span data-ttu-id="45acf-108">ルート参照ノードが指定されていない場合、**ルート参照**のプロパティ、**スキーマ**ノード、スキーマ、既定のルート参照ノードの最初のルート ノードがそので有効な値を設定する必要が**ボディ XPath**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="45acf-108">If no root reference node is specified by the **Root Reference** property of the **Schema** node, the first root node in the schema, the default root reference node, is required to have a valid value in its **Body XPath** property.</span></span> <span data-ttu-id="45acf-109">**ボディ XPath**プロパティ値の各エンベロープ内に含まれるメッセージのスキーマの識別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="45acf-109">**Body XPath** property values are used to identify the schema for the each of the messages contained within the envelope.</span></span>  
  
 <span data-ttu-id="45acf-110">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="45acf-110">**User Action**</span></span>  
  
 <span data-ttu-id="45acf-111">対象のルート ノードを選択しの値を選択し、**ボディ XPath**が関連付けられたメッセージ本文のスキーマを正しく識別されるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="45acf-111">Select the indicated root node and then select the value for the **Body XPath** property that correctly identifies the schema of the associated message body.</span></span>