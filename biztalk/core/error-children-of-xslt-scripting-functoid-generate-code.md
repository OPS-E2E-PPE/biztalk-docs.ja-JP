---
title: エラー - XSLT スクリプト Functoid の子がコードを生成します |Microsoft ドキュメント
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
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a><span data-ttu-id="d5546-102">エラー - XSLT スクリプト Functoid の子がコードを生成します</span><span class="sxs-lookup"><span data-stu-id="d5546-102">Error - Children of XSLT Scripting Functoid Generate Code</span></span>
<span data-ttu-id="d5546-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d5546-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d5546-104">btm1063</span><span class="sxs-lookup"><span data-stu-id="d5546-104">btm1063</span></span>  
  
 <span data-ttu-id="d5546-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d5546-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d5546-106">使用と矛盾するシナリオ、**スクリプト**インライン XSLT または XSLT 呼び出しテンプレートを使用するように構成されている functoid マップが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d5546-106">A scenario that contradicts the use of a **Scripting** functoid that is configured to use inline XSLT or an XSLT Call Template was found in the map.</span></span> <span data-ttu-id="d5546-107">送信先スキーマ、このような出力にリンクされているノードの子孫のノードで、**スクリプト**functoid は、自身の XSLT コードを生成しようとしています。</span><span class="sxs-lookup"><span data-stu-id="d5546-107">In the destination schema, descendent nodes of a node that is linked to the output of such a **Scripting** functoid are attempting to generate XSLT code of their own.</span></span>  
  
 <span data-ttu-id="d5546-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d5546-108">**User Action**</span></span>  
  
 <span data-ttu-id="d5546-109">関連の使用法を変更することで、非互換性を削除する**スクリプト**functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。</span><span class="sxs-lookup"><span data-stu-id="d5546-109">Remove the incompatibility by changing the usage of the relevant **Scripting** functoid or changing the child nodes such that they no longer generate XSLT code of their own.</span></span>