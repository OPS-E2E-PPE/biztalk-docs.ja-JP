---
title: ノード インスタンスを制御するメッセージの構造とバリエーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3af8e6ce-282d-4318-a538-046b423ef033
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa82def3f62c6a603ef67e098e53b48a49013a3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970928"
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="573a0-102">インスタンス メッセージの構造とバリエーションを制御するノード</span><span class="sxs-lookup"><span data-stu-id="573a0-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="573a0-103">BizTalk エディターでスキーマの作成に使用されるノードのいくつかは、インスタンス メッセージの構造やバリエーションを制御します。</span><span class="sxs-lookup"><span data-stu-id="573a0-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="573a0-104">使用する**シーケンス グループ**ノード要素のシーケンスが必要があります、インスタンス メッセージ内の対応する位置の特定の順序で発生するように指定します。</span><span class="sxs-lookup"><span data-stu-id="573a0-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="573a0-105">使用する**選択肢グループ**要素のコレクションから 1 つの要素を指定するノードがインスタンス メッセージ内の対応する位置で発生することができます。</span><span class="sxs-lookup"><span data-stu-id="573a0-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="573a0-106">使用する**すべてのグループ**ことのすべての指定した要素で同時実行できるは 1 回のみ以外のすべての順序、インスタンス メッセージ内の対応する位置を指定するノードです。</span><span class="sxs-lookup"><span data-stu-id="573a0-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="573a0-107">**\<等価\>** ノードとその子ノードがインスタンス メッセージの派生に基づく多態性が場所実際、多くの関連する複雑なデータの許可のいずれかで発生する種類を示すために、スキーマ ツリーに表示されますが、インスタンス メッセージに対応する場所です。</span><span class="sxs-lookup"><span data-stu-id="573a0-107">**\<Equivalent\>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="573a0-108">このセクションの残りの部分では、このクラスのノードに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="573a0-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="573a0-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="573a0-109">In This Section</span></span>  
  
-   <span data-ttu-id="573a0-110">[[シーケンス グループ] ノード](../core/sequence-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="573a0-110">[Sequence Group Nodes](../core/sequence-group-nodes.md)</span></span>  
  
-   <span data-ttu-id="573a0-111">[[グループの選択] ノード](../core/choice-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="573a0-111">[Choice Group Nodes](../core/choice-group-nodes.md)</span></span>  
  
-   <span data-ttu-id="573a0-112">[[すべてのグループ] ノード](../core/all-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="573a0-112">[All Group Nodes](../core/all-group-nodes.md)</span></span>  
  
-   [<span data-ttu-id="573a0-113">\<等価\>ノードとその子ノード</span><span class="sxs-lookup"><span data-stu-id="573a0-113">\<Equivalent\> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)