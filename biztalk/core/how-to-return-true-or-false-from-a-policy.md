---
title: ポリシーから True または False を返す方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 093d58d97d6ecc2df842118b5a30f9858f4b4b96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334902"
---
# <a name="how-to-return-true-or-false-from-a-policy"></a><span data-ttu-id="ae748-102">ポリシーから True または False を返す方法</span><span class="sxs-lookup"><span data-stu-id="ae748-102">How to Return True or False from a Policy</span></span>
<span data-ttu-id="ae748-103">ポリシーの戻り値の型を直接指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="ae748-103">You cannot specify a return type for a policy directly.</span></span> <span data-ttu-id="ae748-104">ただし、ファクトの種類は次の 1 つをポリシーに渡す、このファクトの値を変更するポリシーが適用されて`true`または`false`、し、ポリシーの実行後に、プロパティ、要素、列の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae748-104">However, you can pass one of the following types of facts to the policy, have the policy change the value of the fact to `true` or `false`, and then check the value of the property/element/column after the policy is executed:</span></span>  
  
-   <span data-ttu-id="ae748-105">型のプロパティを使用して、.NET オブジェクト `Boolean`</span><span class="sxs-lookup"><span data-stu-id="ae748-105">A .NET object with a property of type `Boolean`</span></span>  
  
-   <span data-ttu-id="ae748-106">型の要素を持つ XML ドキュメント `Boolean`</span><span class="sxs-lookup"><span data-stu-id="ae748-106">An XML document with an element of type `Boolean`</span></span>  
  
-   <span data-ttu-id="ae748-107">型の列を含むデータベース テーブル `Boolean`</span><span class="sxs-lookup"><span data-stu-id="ae748-107">A database table with a column of type `Boolean`</span></span>