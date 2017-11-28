---
title: "ポリシーから True または False を返す方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281d5ab7648545f2e0616095f3c535d7d109136f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-return-true-or-false-from-a-policy"></a><span data-ttu-id="58834-102">ポリシーから True または False を返す方法</span><span class="sxs-lookup"><span data-stu-id="58834-102">How to Return True or False from a Policy</span></span>
<span data-ttu-id="58834-103">ポリシーで戻り値の型を直接指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="58834-103">You cannot specify a return type for a policy directly.</span></span> <span data-ttu-id="58834-104">ただし、次に示すファクトの種類の 1 つをポリシーに渡し、このファクトの値をポリシーで `true` または `false` に変更して、ポリシーの実行後にプロパティ、要素、または列の値を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="58834-104">However, you can pass one of the following types of facts to the policy, have the policy change the value of the fact to `true` or `false`, and then check the value of the property/element/column after the policy is executed:</span></span>  
  
-   <span data-ttu-id="58834-105">`Boolean` 型のプロパティを持つ .NET オブジェクト</span><span class="sxs-lookup"><span data-stu-id="58834-105">A .NET object with a property of type `Boolean`</span></span>  
  
-   <span data-ttu-id="58834-106">`Boolean` 型の要素を持つ XML ドキュメント</span><span class="sxs-lookup"><span data-stu-id="58834-106">An XML document with an element of type `Boolean`</span></span>  
  
-   <span data-ttu-id="58834-107">`Boolean` 型の列を持つデータベース テーブル</span><span class="sxs-lookup"><span data-stu-id="58834-107">A database table with a column of type `Boolean`</span></span>