---
title: エラー - XSLT スクリプト Functoid が無効の出力リンク |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.outputLinkForXsltNotValid
ms.assetid: cdf8e779-6cf6-4d9c-8655-f8b406498fb7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd597a3953db76087086c7ea9038e9fa1fd87eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a><span data-ttu-id="76f86-102">エラー - XSLT スクリプト Functoid が無効の出力リンク</span><span class="sxs-lookup"><span data-stu-id="76f86-102">Error - Output Link For XSLT Scripting Functoid Not Valid</span></span>
<span data-ttu-id="76f86-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="76f86-103">**Error Code**</span></span>  
  
 <span data-ttu-id="76f86-104">btm1075</span><span class="sxs-lookup"><span data-stu-id="76f86-104">btm1075</span></span>  
  
 <span data-ttu-id="76f86-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="76f86-105">**Explanation**</span></span>  
  
 <span data-ttu-id="76f86-106">関連出力リンク**スクリプト**functoid のインライン XSLT または XSLT 呼び出しテンプレートを使用するように構成が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="76f86-106">The output link of the relevant **Scripting** functoid configured to use inline XSLT or an XSLT Call Template is not valid.</span></span> <span data-ttu-id="76f86-107">このような出力**スクリプト**functoid が接続されていること、送信先スキーマのノードに直接 (および例については、別の functoid にありません)。</span><span class="sxs-lookup"><span data-stu-id="76f86-107">The output of such **Scripting** functoids must be connected directly to a node in the destination schema (and not to another functoid, for example).</span></span>  
  
 <span data-ttu-id="76f86-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="76f86-108">**User Action**</span></span>  
  
 <span data-ttu-id="76f86-109">関連する出力リンクを接続することを確認**スクリプト**functoid を送信先スキーマのノードに直接できます。</span><span class="sxs-lookup"><span data-stu-id="76f86-109">Ensure that you connect the output link from the relevant **Scripting** functoid directly to a node in the destination schema.</span></span>