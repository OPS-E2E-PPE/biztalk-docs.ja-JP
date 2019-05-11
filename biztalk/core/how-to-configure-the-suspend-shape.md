---
title: 中断図形を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Suspend shapes
- Suspend shape [Orchestration Designer], literal strings
- Suspend shape [Orchestration Designer], configuring
- Suspend shape [Orchestration Designer]
- atomic transactions, Suspend shape [Orchestration Designer]
- Suspend shape [Orchestration Designer], atomic transactions
- Suspend shape [Orchestration Designer], about Suspend shape
ms.assetid: 62fbb6d4-78d2-4671-84bb-909cbf6b0ec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4a60bfc2d5a98d407e917e0271a9987e88c0bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385953"
---
# <a name="how-to-configure-the-suspend-shape"></a><span data-ttu-id="19e45-102">中断図形を構成する方法</span><span class="sxs-lookup"><span data-stu-id="19e45-102">How to Configure the Suspend Shape</span></span>
<span data-ttu-id="19e45-103">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span><span class="sxs-lookup"><span data-stu-id="19e45-103">![](../core/media/ebiz-orch-suspend.gif "ebiz_orch_suspend")</span></span>  
<span data-ttu-id="19e45-104">中断図形</span><span class="sxs-lookup"><span data-stu-id="19e45-104">Suspend shape</span></span>  
  
 <span data-ttu-id="19e45-105">オーケストレーション インスタンスが中断されると、エラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="19e45-105">When an orchestration instance is suspended, an error is logged.</span></span> <span data-ttu-id="19e45-106">管理者の状況を診断に役立つエラーに添えるメッセージ文字列を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="19e45-106">You can specify a message string to accompany the error to help the administrator diagnose the situation.</span></span>  
  
 <span data-ttu-id="19e45-107">すべてのオーケストレーション インスタンスの状態情報は保存され、管理者が、オーケストレーション インスタンスを再開する場合に再開します。</span><span class="sxs-lookup"><span data-stu-id="19e45-107">All of the state information for the orchestration instance is saved, and is reinstated if and when the administrator resumes the orchestration instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19e45-108">場合、**中断**が同期的に呼び出されたオーケストレーションに図形が存在します (と同様、**呼び出す**図形) 別のオーケストレーションによって、入れ子になったインスタンスとすべてを囲んでいるオーケストレーション インスタンスが、中断されます。</span><span class="sxs-lookup"><span data-stu-id="19e45-108">If a **Suspend** shape exists in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19e45-109">配置することはできません、 **Suspend**アトミックのトランザクション内の図形。</span><span class="sxs-lookup"><span data-stu-id="19e45-109">You cannot place a **Suspend** shape inside an atomic transaction.</span></span>  
  
### <a name="to-configure-a-suspend-shape"></a><span data-ttu-id="19e45-110">中断図形を構成するには</span><span class="sxs-lookup"><span data-stu-id="19e45-110">To configure a Suspend shape</span></span>  
  
-   <span data-ttu-id="19e45-111">使用することができます、**エラー メッセージ**プロパティにテキストを指定するときにログに記録、 **Suspend**図形が検出されました。</span><span class="sxs-lookup"><span data-stu-id="19e45-111">You can use the **Error Message** property to specify text that you want to be logged when a **Suspend** shape is encountered.</span></span> <span data-ttu-id="19e45-112">このテキスト リテラル文字列の場合、またはに評価される式が適用される場合があります、 **System.String**します。</span><span class="sxs-lookup"><span data-stu-id="19e45-112">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="19e45-113">リテラル文字列を入力する場合は、引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="19e45-113">If you enter a literal string, you must enclose it in quotation marks.</span></span>