---
title: エラー - 複数のループ パス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleLoopPaths
ms.assetid: 3f7c0c1c-5aaa-4da9-99ab-78bac536b8dd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afdcb1a235c71163552fd5f6b255e572feef8dc5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241090"
---
# <a name="error---multiple-loop-paths"></a><span data-ttu-id="791a1-102">エラー - 複数のループ パス</span><span class="sxs-lookup"><span data-stu-id="791a1-102">Error - Multiple Loop Paths</span></span>
<span data-ttu-id="791a1-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="791a1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="791a1-104">btm1030</span><span class="sxs-lookup"><span data-stu-id="791a1-104">btm1030</span></span>  
  
 <span data-ttu-id="791a1-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="791a1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="791a1-106">送信先スキーマのノードに、複数の送信元ループ パスがあります。</span><span class="sxs-lookup"><span data-stu-id="791a1-106">The indicated node in the destination schema has multiple source loop paths.</span></span>  
  
 <span data-ttu-id="791a1-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="791a1-107">**User Action**</span></span>  
  
 <span data-ttu-id="791a1-108">使用して、**ループ**functoid を明示的にする、ループの実行、送信元スキーマ内のノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="791a1-108">Use a **Looping** functoid to explicitly specify the node in the source schema over which the looping will be performed.</span></span>