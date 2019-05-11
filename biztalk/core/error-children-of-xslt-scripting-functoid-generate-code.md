---
title: エラー - XSLT スクリプト Functoid の子がコードを生成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4111d359c0a764c92fc9736fdd2fcbc879252274
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388988"
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a><span data-ttu-id="a906d-102">エラー - XSLT スクリプト Functoid の子がコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="a906d-102">Error - Children of XSLT Scripting Functoid Generate Code</span></span>
<span data-ttu-id="a906d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="a906d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="a906d-104">btm1063</span><span class="sxs-lookup"><span data-stu-id="a906d-104">btm1063</span></span>  
  
 <span data-ttu-id="a906d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="a906d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="a906d-106">使用と矛盾するシナリオを**Scripting**マップに functoid のインライン XSLT または XSLT 呼び出しテンプレートを使用するように構成が見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a906d-106">A scenario that contradicts the use of a **Scripting** functoid that is configured to use inline XSLT or an XSLT Call Template was found in the map.</span></span> <span data-ttu-id="a906d-107">送信先スキーマ、このような出力にリンクされているノードの子孫のノードで、 **Scripting** functoid は自身の XSLT コードを生成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="a906d-107">In the destination schema, descendent nodes of a node that is linked to the output of such a **Scripting** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="a906d-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="a906d-108">**User Action**</span></span>  
  
 <span data-ttu-id="a906d-109">非互換性を関連する使用状況を変更することで削除**Scripting** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a906d-109">Remove the incompatibility by changing the usage of the relevant **Scripting** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>