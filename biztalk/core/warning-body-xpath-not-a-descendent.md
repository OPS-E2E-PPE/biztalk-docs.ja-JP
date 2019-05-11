---
title: 警告 - ボディ XPath がいない子孫 |Microsoft Docs
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
ms.openlocfilehash: e37a2cd645053ce22f6e2f2536b4f647f4738f11
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279595"
---
# <a name="warning---body-xpath-not-a-descendent"></a><span data-ttu-id="925ce-102">警告 - ボディ XPath がいない子孫</span><span class="sxs-lookup"><span data-stu-id="925ce-102">Warning - Body XPath Not A Descendent</span></span>
<span data-ttu-id="925ce-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="925ce-103">**Error Code**</span></span>  
  
 <span data-ttu-id="925ce-104">BEC1004</span><span class="sxs-lookup"><span data-stu-id="925ce-104">BEC1004</span></span>  
  
 <span data-ttu-id="925ce-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="925ce-105">**Explanation**</span></span>  
  
 <span data-ttu-id="925ce-106">**ボディ XPath**このエンベロープ スキーマに含まれているルート ノードのプロパティは、必要に応じて、そのルート ノードの子孫でないノードを参照します。</span><span class="sxs-lookup"><span data-stu-id="925ce-106">The **Body XPath** property of the indicated root node in this envelope schema references a node that is not a descendent of that root node, as required.</span></span> <span data-ttu-id="925ce-107">しない限り、このエラーは発生しません、**ボディ XPath**プロパティが BizTalk エディターの外部で変更されています。</span><span class="sxs-lookup"><span data-stu-id="925ce-107">This error should not occur unless the **Body XPath** property is modified outside of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="925ce-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="925ce-108">**User Action**</span></span>  
  
 <span data-ttu-id="925ce-109">対象のルート ノードを選択しの値を選択、**ボディ XPath**正しく関連付けられたメッセージ本文の最上位ノードを識別するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="925ce-109">Select the indicated root node and select the value for the **Body XPath** property that correctly identifies the top-level node of the associated message body.</span></span>