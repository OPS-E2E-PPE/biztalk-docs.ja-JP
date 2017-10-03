---
title: "エラー - 一括コピー Functoid の子がコードを生成します |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68183a90be46b176d13100b02cbed2798fe24b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a><span data-ttu-id="ebe9c-102">エラー - 一括コピー Functoid の子がコードを生成します</span><span class="sxs-lookup"><span data-stu-id="ebe9c-102">Error - Children of Mass Copy Functoid Generate Code</span></span>
<span data-ttu-id="ebe9c-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ebe9c-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ebe9c-104">btm1068</span><span class="sxs-lookup"><span data-stu-id="ebe9c-104">btm1068</span></span>  
  
 <span data-ttu-id="ebe9c-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ebe9c-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ebe9c-106">機能と矛盾するシナリオ、**一括コピー**マップに functoid が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="ebe9c-106">A scenario that contradicts the functionality of the **Mass Copy** functoid was found in the map.</span></span> <span data-ttu-id="ebe9c-107">送信先スキーマの出力にリンクされているノードの子孫のノードで、**一括コピー** functoid は、自身の XSLT コードを生成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="ebe9c-107">In the destination schema, descendent nodes of a node that is linked to the output of a **Mass Copy** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="ebe9c-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ebe9c-108">**User Action**</span></span>  
  
 <span data-ttu-id="ebe9c-109">関連の使用法を変更することで、非互換性を削除する**一括コピー** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ebe9c-109">Remove the incompatibility by changing the usage of the relevant **Mass Copy** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>