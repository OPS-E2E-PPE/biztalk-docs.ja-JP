---
title: エラー - ループしない入力が複数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-inputs-without-looping"></a><span data-ttu-id="be631-102">エラー - ループしない入力が複数あります。</span><span class="sxs-lookup"><span data-stu-id="be631-102">Error - Multiple Inputs Without Looping</span></span>
<span data-ttu-id="be631-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="be631-103">**Error Code**</span></span>  
  
 <span data-ttu-id="be631-104">btm1004</span><span class="sxs-lookup"><span data-stu-id="be631-104">btm1004</span></span>  
  
 <span data-ttu-id="be631-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="be631-105">**Explanation**</span></span>  
  
 <span data-ttu-id="be631-106">複数のリンクが、指定されたノードの先祖ノードのいずれかに接続されている場合にのみ有効ですが、送信先スキーマのノードに接続している、**ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="be631-106">Multiple links are connected to the indicated node in the destination schema, which is only valid when one of the ancestor nodes of the indicated node is connected to a **Looping** functoid.</span></span>  
  
 <span data-ttu-id="be631-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="be631-107">**User Action**</span></span>  
  
 <span data-ttu-id="be631-108">送信先スキーマの対象ノードへのリンクのうち 1 つを残して後のリンクをすべて削除するか、対象ノードの祖先ノードの 1 つをループ Functoid に接続します。</span><span class="sxs-lookup"><span data-stu-id="be631-108">Either remove all but one of the links to the indicated node in the destination schema, or connect one of the ancestor nodes of the indicated node to a looping functoid.</span></span>