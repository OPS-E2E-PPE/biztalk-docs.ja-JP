---
title: "エラー - には、複数の同レベルの子が生成されました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686899c2871ded25f6901e919e9283694b9bacf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---could-generate-multiple-equivalent-children"></a><span data-ttu-id="0d90b-102">エラー - には、複数の同レベルの子が生成されました</span><span class="sxs-lookup"><span data-stu-id="0d90b-102">Error - Could Generate Multiple Equivalent Children</span></span>
<span data-ttu-id="0d90b-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="0d90b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="0d90b-104">btm1026</span><span class="sxs-lookup"><span data-stu-id="0d90b-104">btm1026</span></span>  
  
 <span data-ttu-id="0d90b-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="0d90b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="0d90b-106">送信先スキーマへのリンクには内で複数のノードに不適切な**等価**グループ ノードを生成します。</span><span class="sxs-lookup"><span data-stu-id="0d90b-106">Links to the destination schema inappropriately enable multiple nodes within an **Equivalent** group node to be generated.</span></span>  
  
 <span data-ttu-id="0d90b-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="0d90b-107">**User Action**</span></span>  
  
 <span data-ttu-id="0d90b-108">可能性があるため、論理演算 functoid を使用して、送信先スキーマへのリンクを修正内で 1 つのノードだけである、**等価**グループ ノードは、マッピング中に生成されることができます。</span><span class="sxs-lookup"><span data-stu-id="0d90b-108">Rework the links into the destination schema, potentially using logical functoids, so that only a single node within the **Equivalent** group node can be generated during mapping.</span></span>