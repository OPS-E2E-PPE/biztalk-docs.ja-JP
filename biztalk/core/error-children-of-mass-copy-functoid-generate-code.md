---
title: エラー - 一括コピー Functoid の子がコードを生成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.massCopyChildtenGenCode
ms.assetid: c791009b-241b-4004-b0c6-f1536bb119c5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c11f96b753b100a9662671ff0c20d5671ad07055
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349005"
---
# <a name="error---children-of-mass-copy-functoid-generate-code"></a><span data-ttu-id="9c544-102">エラー - 一括コピー Functoid の子がコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="9c544-102">Error - Children of Mass Copy Functoid Generate Code</span></span>
<span data-ttu-id="9c544-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="9c544-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9c544-104">btm1068</span><span class="sxs-lookup"><span data-stu-id="9c544-104">btm1068</span></span>  
  
 <span data-ttu-id="9c544-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="9c544-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9c544-106">機能と矛盾するシナリオ、**一括コピー**マップに functoid が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="9c544-106">A scenario that contradicts the functionality of the **Mass Copy** functoid was found in the map.</span></span> <span data-ttu-id="9c544-107">送信先スキーマの出力にリンクされているノードの子孫のノードで、**一括コピー** functoid は自身の XSLT コードを生成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="9c544-107">In the destination schema, descendent nodes of a node that is linked to the output of a **Mass Copy** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="9c544-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="9c544-108">**User Action**</span></span>  
  
 <span data-ttu-id="9c544-109">非互換性を関連する使用状況を変更することで削除**一括コピー** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="9c544-109">Remove the incompatibility by changing the usage of the relevant **Mass Copy** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>