---
title: 警告 - ボディ XPath が子孫ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.bodyXPathNotDescendant
ms.assetid: bfeff370-9b84-4fd9-81e9-1e54b166f561
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b5d228e1119bc7c569b45cc6795f3f5b8454ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---body-xpath-not-a-descendent"></a><span data-ttu-id="d3ad1-102">警告 - ボディ XPath が子孫ではありません</span><span class="sxs-lookup"><span data-stu-id="d3ad1-102">Warning - Body XPath Not A Descendent</span></span>
<span data-ttu-id="d3ad1-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="d3ad1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="d3ad1-104">BEC1004</span><span class="sxs-lookup"><span data-stu-id="d3ad1-104">BEC1004</span></span>  
  
 <span data-ttu-id="d3ad1-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="d3ad1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="d3ad1-106">**ボディ XPath**このエンベロープ スキーマに含まれているルート ノードのプロパティが参照ノードは、必要に応じて、そのルート ノードの子孫ではありません。</span><span class="sxs-lookup"><span data-stu-id="d3ad1-106">The **Body XPath** property of the indicated root node in this envelope schema references a node that is not a descendent of that root node, as required.</span></span> <span data-ttu-id="d3ad1-107">しない限り、このエラーは発生しません、**ボディ XPath**プロパティが BizTalk エディターの外部で変更されています。</span><span class="sxs-lookup"><span data-stu-id="d3ad1-107">This error should not occur unless the **Body XPath** property is modified outside of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="d3ad1-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="d3ad1-108">**User Action**</span></span>  
  
 <span data-ttu-id="d3ad1-109">対象のルート ノードを選択し、値を選択、**ボディ XPath**正しく関連付けられているメッセージ本文の最上位ノードを識別するプロパティです。</span><span class="sxs-lookup"><span data-stu-id="d3ad1-109">Select the indicated root node and select the value for the **Body XPath** property that correctly identifies the top-level node of the associated message body.</span></span>