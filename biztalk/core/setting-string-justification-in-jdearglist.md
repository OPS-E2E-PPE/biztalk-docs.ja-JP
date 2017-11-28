---
title: "Jdearglist で文字列の位置揃えを設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a><span data-ttu-id="4cc80-102">Jdearglist での文字列の位置揃えの設定</span><span class="sxs-lookup"><span data-stu-id="4cc80-102">Setting String Justification in Jdearglist</span></span>
<span data-ttu-id="4cc80-103">JD Edwards OneWorld の jdearglist.txt ファイルで特定の文字列引数を右揃え (左側に埋め込み) として構成するには、どのビジネス関数にアクセスするのかがわかっている必要があります。特に、ビジネス関数のどのフィールドを呼び出すのかがわかっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc80-103">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="4cc80-104">オーケストレーションでバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc80-104">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="4cc80-105">Jdearglist.txt を更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)です。</span><span class="sxs-lookup"><span data-stu-id="4cc80-105">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="4cc80-106">監査ログに jdearglist.txt の警告メッセージが出力された場合は、jdearglist.txt がないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="4cc80-106">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="4cc80-107">SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、ファイルが PATH に含まれている必要があります。そうでない場合は動作しません。</span><span class="sxs-lookup"><span data-stu-id="4cc80-107">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc80-108">参照</span><span class="sxs-lookup"><span data-stu-id="4cc80-108">See Also</span></span>  
 [<span data-ttu-id="4cc80-109">BizTalk Adapter for JD Edwards OneWorld の管理</span><span class="sxs-lookup"><span data-stu-id="4cc80-109">Administering BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)