---
title: "オーケストレーション エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d95cab903ae9bf5faacdf385f667c33f9a2d5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-failures"></a><span data-ttu-id="5aca5-102">オーケストレーション エラー</span><span class="sxs-lookup"><span data-stu-id="5aca5-102">Orchestration Failures</span></span>
<span data-ttu-id="5aca5-103">各オーケストレーションの複雑さは異なります。たとえば、.NET オブジェクトを呼び出すオーケストレーションもあれば、変換図形と割り当て図形を経由してメッセージを構築するオーケストレーションもあります。</span><span class="sxs-lookup"><span data-stu-id="5aca5-103">Orchestrations vary in complexity; for example, an orchestration may call a .NET object or construct messages via transform and assignment shape.</span></span> <span data-ttu-id="5aca5-104">このように、オーケストレーションの内容やカスタマイズ レベルはさまざまなので、発生する可能性のあるすべてのエラーを列挙することはできません。</span><span class="sxs-lookup"><span data-stu-id="5aca5-104">As a result, it is impossible to list out every possible failure, due to the variety of its content as well as level of customization.</span></span> <span data-ttu-id="5aca5-105">ただし、オーケストレーションで発生するすべてのエラーは例外として表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aca5-105">However, all failures encountered in orchestrations appear as exceptions.</span></span>  
  
 <span data-ttu-id="5aca5-106">いずれかのオーケストレーションが含まれない場合**CatchException**例外、例外の図形により、オーケストレーションが中断、再開できません。</span><span class="sxs-lookup"><span data-stu-id="5aca5-106">If an orchestration does not include any **CatchException** shape for an exception, the exception causes the orchestration to be Suspended, but not resumable.</span></span> <span data-ttu-id="5aca5-107">これは、メッセージおよびサービス インスタンスの追跡や WMI スクリプトではインスタンスを修復できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5aca5-107">This means that message and service instance tracking, or a WMI script, cannot recover the instance.</span></span> <span data-ttu-id="5aca5-108">ただし、診断や手動での再試行用に、追跡 (または WMI スクリプト) を使用して、中断された (再開できない) インスタンスに関連付けられたすべてのメッセージを保存できます。</span><span class="sxs-lookup"><span data-stu-id="5aca5-108">However, you can save all messages associated with the Suspended (not Resumable) instance using tracking (or WMI script) for diagnostic and manual retry.</span></span>  
  
 <span data-ttu-id="5aca5-109">問題を診断するには、オーケストレーション デバッガーを使用して、インスタンスが中断される直前に実行された図形を確認します。</span><span class="sxs-lookup"><span data-stu-id="5aca5-109">To diagnose the problem, use the Orchestration Debugger to see the last shape executed before the instance is suspended.</span></span> <span data-ttu-id="5aca5-110">また、オーケストレーション デバッガーを使用して、例外の詳細を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5aca5-110">You can also view exception details using the Orchestration Debugger.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aca5-111">参照</span><span class="sxs-lookup"><span data-stu-id="5aca5-111">See Also</span></span>  
 <span data-ttu-id="5aca5-112">[オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md) </span><span class="sxs-lookup"><span data-stu-id="5aca5-112">[Investigating Orchestration, Port, and Message Failures](../core/investigating-orchestration-port-and-message-failures.md) </span></span>  
 [<span data-ttu-id="5aca5-113">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="5aca5-113">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)