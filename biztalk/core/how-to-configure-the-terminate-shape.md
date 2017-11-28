---
title: "終了図形を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-terminate-shape"></a><span data-ttu-id="2cae3-102">終了図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2cae3-102">How to Configure the Terminate Shape</span></span>
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
<span data-ttu-id="2cae3-103">終了図形</span><span class="sxs-lookup"><span data-stu-id="2cae3-103">Terminate shape</span></span>  
  
 <span data-ttu-id="2cae3-104">終了図形は、オーケストレーション インスタンスを終了するために使用します。</span><span class="sxs-lookup"><span data-stu-id="2cae3-104">The Terminate shape is used to end an orchestration instance.</span></span> <span data-ttu-id="2cae3-105">[グループ ハブ] ページからの出力で表示する際に図形に添えるメッセージ文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2cae3-105">You can specify a message string to accompany the shape when viewed in the output from the Group Hub page.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2cae3-106">配置した場合、 **Terminate**図形内、**並列アクション**図形とで、分岐、 **Terminate**では、実行、インスタンスが、すぐに完了に関係なくかどうか、他の分岐の実行が完了します。</span><span class="sxs-lookup"><span data-stu-id="2cae3-106">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="2cae3-107">デザイン方法によっては、この場合の結果が予測できないものになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cae3-107">Depending on your design, results might be unpredictable in this case.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2cae3-108">場合、 **Terminate**図形が同期的に呼び出されたオーケストレーションで検出された (と同様、**呼び出す**図形) によって別のオーケストレーション、入れ子になったインスタンスおよびそれを囲むすべてのオーケストレーションインスタンスは終了されます。</span><span class="sxs-lookup"><span data-stu-id="2cae3-108">If a **Terminate** shape is encountered in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be terminated.</span></span>  
  
### <a name="to-configure-a-terminate-shape"></a><span data-ttu-id="2cae3-109">終了図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="2cae3-109">To configure a Terminate shape</span></span>  
  
-   <span data-ttu-id="2cae3-110">使用することができます、**エラー メッセージ**プロパティ グループ ハブ ページのクエリ出力に表示する際に図形に関連付けるテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="2cae3-110">You can use the **Error Message** property to specify text that you want to associate with the shape when viewed in the query output on the Group Hub page.</span></span> <span data-ttu-id="2cae3-111">このテキストはリテラル文字列、またはに評価される式が適用される場合があります、 **System.String**です。</span><span class="sxs-lookup"><span data-stu-id="2cae3-111">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="2cae3-112">リテラル文字列を入力する場合は、二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cae3-112">If you enter a literal string, you must enclose it in quotation marks.</span></span>