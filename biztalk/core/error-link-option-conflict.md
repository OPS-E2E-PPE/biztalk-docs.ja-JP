---
title: エラー - リンク オプション競合しています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.linkOptionConflict
ms.assetid: dbad5c00-500b-4931-a54c-8b311fbfda53
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31f5829f971e524a5e4d2c0f443174c6511a6314
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---link-option-conflict"></a><span data-ttu-id="0de81-102">エラー - リンク オプション競合しています</span><span class="sxs-lookup"><span data-stu-id="0de81-102">Error - Link Option Conflict</span></span>
<span data-ttu-id="0de81-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0de81-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0de81-104">btm1022</span><span class="sxs-lookup"><span data-stu-id="0de81-104">btm1022</span></span>  
  
 <span data-ttu-id="0de81-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0de81-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0de81-106">送信先スキーマの各ノードの受信リンクに指定されているコンパイラ ディレクティブの中に、競合しているコンパイラ ディレクティブがあります。</span><span class="sxs-lookup"><span data-stu-id="0de81-106">The indicated nodes in the destination schema have conflicting compiler directives specified for their incoming links.</span></span>  
  
 <span data-ttu-id="0de81-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0de81-107">**User Action**</span></span>  
  
 <span data-ttu-id="0de81-108">送信先スキーマのノードへのリンクの一方または両方を選択し、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウでこれらのノードのコンパイラ ディレクティブを変更して、競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="0de81-108">Select one or both of the links leading to the indicated nodes in the destination schema and then in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change their compiler directives so that they are compatible.</span></span>