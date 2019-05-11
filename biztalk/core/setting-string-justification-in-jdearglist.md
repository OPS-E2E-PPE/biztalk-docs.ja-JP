---
title: JD Edwards OneWorld アダプターでの文字列の位置を設定 |Microsoft Docs
description: Jdearglist ファイルは、JD Edwards OneWorld アダプターを使用して BizTalk Server オーケストレーションを更新します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f33941e997315a5e91e5c99f4e6dc4bd0d2b7aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393246"
---
# <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="abbe4-103">Jdearglist での位置の文字列の設定</span><span class="sxs-lookup"><span data-stu-id="abbe4-103">Set string Justification in Jdearglist</span></span>

## <a name="overview"></a><span data-ttu-id="abbe4-104">概要</span><span class="sxs-lookup"><span data-stu-id="abbe4-104">Overview</span></span>
<span data-ttu-id="abbe4-105">特定の文字列引数として構成するのに右揃え (および左側に埋め込み) では、JD Edwards OneWorld の jdearglist.txt ファイル; にアクセスするどのようなビジネス機能を知る必要があります具体的には、呼び出したいビジネス関数のどのフィールドが必要です。</span><span class="sxs-lookup"><span data-stu-id="abbe4-105">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="abbe4-106">オーケストレーションのバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbe4-106">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="abbe4-107">Jdearglist.txt ファイルを更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)します。</span><span class="sxs-lookup"><span data-stu-id="abbe4-107">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="abbe4-108">監査ログに jdearglist.txt の警告メッセージを受信する場合に通知する、jdearglist.txt がないこと。</span><span class="sxs-lookup"><span data-stu-id="abbe4-108">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="abbe4-109">SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、パスにファイルが必要または機能しません。</span><span class="sxs-lookup"><span data-stu-id="abbe4-109">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbe4-110">参照</span><span class="sxs-lookup"><span data-stu-id="abbe4-110">See Also</span></span>  
[<span data-ttu-id="abbe4-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="abbe4-111">Use BizTalk Server Exception Handling</span></span>](using-biztalk-server-exception-handling1.md)