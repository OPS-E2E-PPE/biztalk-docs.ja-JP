---
title: エラー - リンク オプションが競合 |Microsoft Docs
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
ms.openlocfilehash: 3abbafbc33681ed043e55fb4ad2aa19199b1736f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347898"
---
# <a name="error---link-option-conflict"></a><span data-ttu-id="f06a6-102">エラー - リンク オプションが競合</span><span class="sxs-lookup"><span data-stu-id="f06a6-102">Error - Link Option Conflict</span></span>
<span data-ttu-id="f06a6-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f06a6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f06a6-104">btm1022</span><span class="sxs-lookup"><span data-stu-id="f06a6-104">btm1022</span></span>  
  
 <span data-ttu-id="f06a6-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="f06a6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f06a6-106">送信先スキーマの各ノードの受信リンクに指定されているコンパイラ ディレクティブの中に、競合しているコンパイラ ディレクティブがあります。</span><span class="sxs-lookup"><span data-stu-id="f06a6-106">The indicated nodes in the destination schema have conflicting compiler directives specified for their incoming links.</span></span>  
  
 <span data-ttu-id="f06a6-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="f06a6-107">**User Action**</span></span>  
  
 <span data-ttu-id="f06a6-108">送信先スキーマのノードへのリンクの一方または両方を選択し、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のプロパティ ウィンドウでこれらのノードのコンパイラ ディレクティブを変更して、競合しないようにします。</span><span class="sxs-lookup"><span data-stu-id="f06a6-108">Select one or both of the links leading to the indicated nodes in the destination schema and then in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, change their compiler directives so that they are compatible.</span></span>