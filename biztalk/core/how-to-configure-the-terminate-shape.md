---
title: 終了図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177666efceb34d78b492c93b7f365fc36c3855bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340291"
---
# <a name="how-to-configure-the-terminate-shape"></a><span data-ttu-id="87b33-102">終了図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="87b33-102">How to Configure the Terminate Shape</span></span>
<span data-ttu-id="87b33-103">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span><span class="sxs-lookup"><span data-stu-id="87b33-103">![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")</span></span>  
<span data-ttu-id="87b33-104">終了図形</span><span class="sxs-lookup"><span data-stu-id="87b33-104">Terminate shape</span></span>  
  
 <span data-ttu-id="87b33-105">終了図形を使用して、オーケストレーション インスタンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="87b33-105">The Terminate shape is used to end an orchestration instance.</span></span> <span data-ttu-id="87b33-106">グループ ハブ ページからの出力で表示したときに図形に添えるメッセージ文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="87b33-106">You can specify a message string to accompany the shape when viewed in the output from the Group Hub page.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="87b33-107">配置した場合、 **Terminate**図形内、**並列アクション**形状、および分岐を**Terminate**で実行されて、インスタンスが、すぐに完了に関係なくかどうか他の分岐の実行が完了します。</span><span class="sxs-lookup"><span data-stu-id="87b33-107">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="87b33-108">設計によって結果予測できないここでします。</span><span class="sxs-lookup"><span data-stu-id="87b33-108">Depending on your design, results might be unpredictable in this case.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="87b33-109">場合、 **Terminate**が同期的に呼び出されたオーケストレーションの図形が検出された (と同様、**呼び出す**図形) 別のオーケストレーション、入れ子になったインスタンスおよびそれを囲むすべてのオーケストレーションインスタンスは終了されます。</span><span class="sxs-lookup"><span data-stu-id="87b33-109">If a **Terminate** shape is encountered in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be terminated.</span></span>  
  
### <a name="to-configure-a-terminate-shape"></a><span data-ttu-id="87b33-110">終了図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="87b33-110">To configure a Terminate shape</span></span>  
  
-   <span data-ttu-id="87b33-111">使用することができます、**エラー メッセージ**グループ ハブ ページでクエリの出力に表示したときに図形に関連付けるテキストを指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="87b33-111">You can use the **Error Message** property to specify text that you want to associate with the shape when viewed in the query output on the Group Hub page.</span></span> <span data-ttu-id="87b33-112">このテキスト リテラル文字列の場合、またはに評価される式が適用される場合があります、 **System.String**します。</span><span class="sxs-lookup"><span data-stu-id="87b33-112">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="87b33-113">リテラル文字列を入力する場合は、引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="87b33-113">If you enter a literal string, you must enclose it in quotation marks.</span></span>