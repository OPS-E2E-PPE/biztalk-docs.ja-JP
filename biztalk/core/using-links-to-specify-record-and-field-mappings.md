---
title: リンクを使用してレコードを指定するフィールドのマッピングと |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c669d93-e088-459e-8f45-87c359874a7e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79595e3acc916e61919d77c4f39fe24ff43b00f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287250"
---
# <a name="using-links-to-specify-record-and-field-mappings"></a><span data-ttu-id="1ed35-102">リンクを使用してレコードを指定してフィールドのマッピング</span><span class="sxs-lookup"><span data-stu-id="1ed35-102">Using Links to Specify Record and Field Mappings</span></span>
<span data-ttu-id="1ed35-103">BizTalk マッパーでは、リンクを使用して、送信元スキーマのデータ項目を送信先スキーマのデータ項目に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1ed35-103">In BizTalk Mapper, a link is the way you associate a data item in the source schema with a data item in the destination schema.</span></span> <span data-ttu-id="1ed35-104">通常、完成したマップには、送信元スキーマと送信先スキーマの間に多数のリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="1ed35-104">Typically, in a completed map there are many links between the source schema and the destination schema.</span></span> <span data-ttu-id="1ed35-105">すべてのリンクが一体となって、送信元インスタンス メッセージのデータを送信先インスタンス メッセージに変換する方法を指定します。送信先インスタンス メッセージは、送信元と同等の意味を持ちますが、構文的には異なります。</span><span class="sxs-lookup"><span data-stu-id="1ed35-105">All together the links specify how the data in the source instance messages will be transformed into a semantically equivalent, but syntactically distinct, destination instance messages.</span></span>  
  
 <span data-ttu-id="1ed35-106">このセクションでは、新しいリンクの作成、既存リンクの操作、リンクの自動作成などの各リンク操作タスクに関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ed35-106">This section provides task-specific information about creating new links, working with existing links, creating links automatically, and other linking operations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ed35-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ed35-107">In This Section</span></span>  
  
-   [<span data-ttu-id="1ed35-108">リンクを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-108">How to Create Links</span></span>](../core/how-to-create-links.md)  
  
-   [<span data-ttu-id="1ed35-109">リンクのプロパティを編集する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-109">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)  
  
-   [<span data-ttu-id="1ed35-110">レコードを自動的にリンクする方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-110">How to Link Records Automatically</span></span>](../core/how-to-link-records-automatically.md)  
  
-   [<span data-ttu-id="1ed35-111">既存のリンクを管理する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-111">How to Manage Existing Links</span></span>](../core/how-to-manage-existing-links.md)  
  
-   [<span data-ttu-id="1ed35-112">一致するノードの階層を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-112">How to Configure Node Hierarchy Matching</span></span>](../core/how-to-configure-node-hierarchy-matching.md)  
  
-   [<span data-ttu-id="1ed35-113">ソースへのリンクのコンパイラ値を設定する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-113">How to Set the Source Links Compiler Value</span></span>](../core/how-to-set-the-source-links-compiler-value.md)  
  
-   [<span data-ttu-id="1ed35-114">コンパイラ リンクを非表示にしたりする方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-114">How to Show and Hide Compiler Links</span></span>](../core/how-to-show-and-hide-compiler-links.md)  
  
-   [<span data-ttu-id="1ed35-115">コピー、切り取り、およびリンクおよび Functoid を貼り付けする方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-115">How to Copy, Cut, and Paste Links and Functoids</span></span>](../core/how-to-copy-cut-and-paste-links-and-functoids.md)  
  
-   [<span data-ttu-id="1ed35-116">リンクのラベルを付ける方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-116">How to Label a Link</span></span>](../core/how-to-label-a-link.md)  
  
-   [<span data-ttu-id="1ed35-117">複数のリンクおよび Functoid を選択する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-117">How to Select Multiple Links and Functoids</span></span>](../core/how-to-select-multiple-links-and-functoids.md)  
  
-   [<span data-ttu-id="1ed35-118">複数のリンクおよび Functoid のラベルとコメントを設定する方法</span><span class="sxs-lookup"><span data-stu-id="1ed35-118">How to Set Label and Comment on Multiple Links and Functoids</span></span>](../core/how-to-set-label-and-comment-on-multiple-links-and-functoids.md)