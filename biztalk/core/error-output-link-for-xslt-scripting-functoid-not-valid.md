---
title: エラー - XSLT スクリプト Functoid の無効の出力リンクが |Microsoft Docs
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
ms.openlocfilehash: 1348fd9cab436ca3ddbd0991acd5861283d933b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388503"
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a><span data-ttu-id="acf19-102">エラー - XSLT スクリプト Functoid の無効の出力リンク</span><span class="sxs-lookup"><span data-stu-id="acf19-102">Error - Output Link For XSLT Scripting Functoid Not Valid</span></span>
<span data-ttu-id="acf19-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="acf19-103">**Error Code**</span></span>  
  
 <span data-ttu-id="acf19-104">btm1075</span><span class="sxs-lookup"><span data-stu-id="acf19-104">btm1075</span></span>  
  
 <span data-ttu-id="acf19-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="acf19-105">**Explanation**</span></span>  
  
 <span data-ttu-id="acf19-106">関連するは、出力リンク**Scripting** functoid のインライン XSLT または XSLT 呼び出しテンプレートを使用するように構成が無効です。</span><span class="sxs-lookup"><span data-stu-id="acf19-106">The output link of the relevant **Scripting** functoid configured to use inline XSLT or an XSLT Call Template is not valid.</span></span> <span data-ttu-id="acf19-107">このような出力**Scripting** functoid を接続する必要があります、送信先スキーマのノードに直接 (および例については、別の functoid)。</span><span class="sxs-lookup"><span data-stu-id="acf19-107">The output of such **Scripting** functoids must be connected directly to a node in the destination schema (and not to another functoid, for example).</span></span>  
  
 <span data-ttu-id="acf19-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="acf19-108">**User Action**</span></span>  
  
 <span data-ttu-id="acf19-109">関連する出力リンクが接続できるように**Scripting** functoid を送信先スキーマ内のノードに直接します。</span><span class="sxs-lookup"><span data-stu-id="acf19-109">Ensure that you connect the output link from the relevant **Scripting** functoid directly to a node in the destination schema.</span></span>