---
title: JD Edwards OneWorld アダプターで文字列の位置揃えを設定 |Microsoft ドキュメント
description: BizTalk Server オーケストレーションに、JD Edwards OneWorld アダプターを使用する jdearglist ファイルを更新します。
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
ms.openlocfilehash: 70b32d0106d95a1970b480e32dfa47a81ebf98ca
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013001"
---
# <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="1adee-103">Jdearglist での位置揃えの文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="1adee-103">Set string Justification in Jdearglist</span></span>

## <a name="overview"></a><span data-ttu-id="1adee-104">概要</span><span class="sxs-lookup"><span data-stu-id="1adee-104">Overview</span></span>
<span data-ttu-id="1adee-105">JD Edwards OneWorld の jdearglist.txt ファイルで特定の文字列引数を右揃え (左側に埋め込み) として構成するには、どのビジネス関数にアクセスするのかがわかっている必要があります。特に、ビジネス関数のどのフィールドを呼び出すのかがわかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1adee-105">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="1adee-106">オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1adee-106">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="1adee-107">Jdearglist.txt を更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)です。</span><span class="sxs-lookup"><span data-stu-id="1adee-107">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="1adee-108">監査ログに jdearglist.txt の警告メッセージが出力された場合は、jdearglist.txt がないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="1adee-108">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="1adee-109">SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、ファイルが PATH に含まれている必要があります。そうでない場合は動作しません。</span><span class="sxs-lookup"><span data-stu-id="1adee-109">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adee-110">参照</span><span class="sxs-lookup"><span data-stu-id="1adee-110">See Also</span></span>  
[<span data-ttu-id="1adee-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="1adee-111">Use BizTalk Server Exception Handling</span></span>](using-biztalk-server-exception-handling1.md)