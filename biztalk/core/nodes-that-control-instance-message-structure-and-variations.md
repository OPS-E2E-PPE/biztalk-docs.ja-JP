---
title: メッセージの構造とバリエーションのインスタンスを制御するノード |Microsoft Docs
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
ms.openlocfilehash: 14be46a217bae51a31b785d4ad60700ecd7f30d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263360"
---
# <a name="nodes-that-control-instance-message-structure-and-variations"></a><span data-ttu-id="8f483-102">インスタンス メッセージの構造とバリエーションを制御するノード</span><span class="sxs-lookup"><span data-stu-id="8f483-102">Nodes That Control Instance Message Structure and Variations</span></span>
<span data-ttu-id="8f483-103">一部の BizTalk エディターでスキーマを作成するために使用するノードの種類はの構造とインスタンス メッセージ内のバリエーションを制御します。</span><span class="sxs-lookup"><span data-stu-id="8f483-103">Some of the node types that you use to create schemas in BizTalk Editor control the structure of, and variations within, instance messages.</span></span> <span data-ttu-id="8f483-104">使用する**シーケンス グループ**ノード要素のシーケンスする必要があります、インスタンス メッセージ内の対応する位置の特定の順序で発生するように指定します。</span><span class="sxs-lookup"><span data-stu-id="8f483-104">You use **Sequence Group** nodes to specify that a sequence of elements must occur in a specific order in the corresponding location in an instance message.</span></span> <span data-ttu-id="8f483-105">使用する**グループの選択**要素のコレクションから 1 つの要素を指定するノードがインスタンス メッセージに対応する場所で発生することができます。</span><span class="sxs-lookup"><span data-stu-id="8f483-105">You use **Choice Group** nodes to specify that one element from a collection of elements can occur in the corresponding location in an instance message.</span></span> <span data-ttu-id="8f483-106">使用する**すべてのグループ**ノードをすべての指定した要素をインスタンス メッセージに対応する場所で任意の順序が一度だけ発生ことができることを指定します。</span><span class="sxs-lookup"><span data-stu-id="8f483-106">You use **All Group** nodes to specify that all of the specified elements can occur in any order, but only once, at the corresponding location in an instance message.</span></span> <span data-ttu-id="8f483-107">**\<等価\>** をインスタンス メッセージ内の派生に基づく多態性が場所関連の多くの複雑なデータの許可の 1 つ有効になってで発生する種類を示すために、スキーマ ツリー ノードとその子ノードを表示しますインスタンス メッセージ内の対応する位置。</span><span class="sxs-lookup"><span data-stu-id="8f483-107">**\<Equivalent\>** nodes and their child nodes are displayed in the schema tree to indicate locations in instance messages where derivation-based polymorphism is in effect, allowing one of many related complex data types to occur in the corresponding location in an instance message.</span></span>  
  
 <span data-ttu-id="8f483-108">このセクションの残りの部分は、このクラスのノードに関する追加情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="8f483-108">The remainder of this section provides additional information about this class of nodes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f483-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8f483-109">In This Section</span></span>  
  
-   <span data-ttu-id="8f483-110">[[シーケンス グループ] ノード](../core/sequence-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="8f483-110">[Sequence Group Nodes](../core/sequence-group-nodes.md)</span></span>  
  
-   <span data-ttu-id="8f483-111">[[グループの選択] ノード](../core/choice-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="8f483-111">[Choice Group Nodes](../core/choice-group-nodes.md)</span></span>  
  
-   <span data-ttu-id="8f483-112">[[すべてのグループ] ノード](../core/all-group-nodes.md)</span><span class="sxs-lookup"><span data-stu-id="8f483-112">[All Group Nodes](../core/all-group-nodes.md)</span></span>  
  
-   [<span data-ttu-id="8f483-113">\<等価\>ノードとその子ノード</span><span class="sxs-lookup"><span data-stu-id="8f483-113">\<Equivalent\> Nodes and Their Child Nodes</span></span>](../core/equivalent-nodes-and-their-child-nodes.md)