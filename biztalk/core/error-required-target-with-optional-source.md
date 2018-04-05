---
title: エラー - 必須ターゲットに省略可能なソース |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76dd96f61766a475db6385e306bc64bc36db4fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-with-optional-source"></a><span data-ttu-id="fe62b-102">エラー - 必須ターゲットに省略可能なソース</span><span class="sxs-lookup"><span data-stu-id="fe62b-102">Error - Required Target with Optional Source</span></span>
<span data-ttu-id="fe62b-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="fe62b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="fe62b-104">btm1001</span><span class="sxs-lookup"><span data-stu-id="fe62b-104">btm1001</span></span>  
  
 <span data-ttu-id="fe62b-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="fe62b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="fe62b-106">送信先スキーマの必須ノードのデータが、送信元スキーマの任意指定ノードから取得されています。</span><span class="sxs-lookup"><span data-stu-id="fe62b-106">The data for the indicated required node in the destination schema comes from an optional node in the source schema.</span></span> <span data-ttu-id="fe62b-107">このため、有効なインスタンス メッセージの中に、マッピングできないものがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe62b-107">Therefore, there may be valid instance messages for which mapping will fail.</span></span>  
  
 <span data-ttu-id="fe62b-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="fe62b-108">**User Action**</span></span>  
  
 <span data-ttu-id="fe62b-109">指定された送信元ノードと送信先ノードの特性が省略可能か必須かを確認します。これらのノードの特性は、同じにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe62b-109">Confirm the optional and required characteristics of the specified source and destination nodes, respectively, and consider making these characteristics match.</span></span>