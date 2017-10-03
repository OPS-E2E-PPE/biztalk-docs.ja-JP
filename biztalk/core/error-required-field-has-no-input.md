---
title: "エラー - 必須フィールドに入力がありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.reqdFieldHasNoInput
ms.assetid: 2454baf8-aa28-4b7b-93cd-aab9afc63823
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343b565dec1ee3d0bc2487bd32ea3854cbacb3bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-field-has-no-input"></a><span data-ttu-id="cc986-102">エラー - 必須フィールドに入力がありません。</span><span class="sxs-lookup"><span data-stu-id="cc986-102">Error - Required Field Has No Input</span></span>
<span data-ttu-id="cc986-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="cc986-103">**Error Code**</span></span>  
  
 <span data-ttu-id="cc986-104">btm1028</span><span class="sxs-lookup"><span data-stu-id="cc986-104">btm1028</span></span>  
  
 <span data-ttu-id="cc986-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="cc986-105">**Explanation**</span></span>  
  
 <span data-ttu-id="cc986-106">送信先スキーマでは、対象のノードは必須と指定されていますが、受信リンク、定数値、または既定値がありません。したがって、ノードはこのマップで提供される出力インスタンス メッセージに含められません。</span><span class="sxs-lookup"><span data-stu-id="cc986-106">The indicated node in the destination schema is specified as required, yet has no incoming link, constant value, or default value, and thus will not be included in output instance messages provided by this map.</span></span>  
  
 <span data-ttu-id="cc986-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="cc986-107">**User Action**</span></span>  
  
 <span data-ttu-id="cc986-108">適宜、送信先スキーマの対象ノードを省略可能に変更するか、受信リンク、定数値、または既定値をそのノードに設定します。</span><span class="sxs-lookup"><span data-stu-id="cc986-108">As appropriate, either change the indicated node in the destination schema to optional, or provide an incoming link, constant value, or default value for it.</span></span>