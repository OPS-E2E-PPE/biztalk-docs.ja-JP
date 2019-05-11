---
title: オーケストレーション エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d3eaebe4244dfd1e7ad60cf6541c4573a9f2158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263003"
---
# <a name="orchestration-failures"></a><span data-ttu-id="c1e72-102">オーケストレーション エラー</span><span class="sxs-lookup"><span data-stu-id="c1e72-102">Orchestration Failures</span></span>
<span data-ttu-id="c1e72-103">オーケストレーションの複雑さ; が異なりますたとえば、オーケストレーションは、.NET オブジェクトを呼び出す可能性があります。 またはトランス フォームと割り当て図形を使用してメッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="c1e72-103">Orchestrations vary in complexity; for example, an orchestration may call a .NET object or construct messages via transform and assignment shape.</span></span> <span data-ttu-id="c1e72-104">その結果、レベルのカスタマイズと同様に、さまざまなコンテンツのためのすべての可能性のあるエラーを列挙することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1e72-104">As a result, it is impossible to list out every possible failure, due to the variety of its content as well as level of customization.</span></span> <span data-ttu-id="c1e72-105">ただし、例外として、オーケストレーションで発生したすべてのエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1e72-105">However, all failures encountered in orchestrations appear as exceptions.</span></span>  
  
 <span data-ttu-id="c1e72-106">いずれかのオーケストレーションが含まれない場合**CatchException**図形例外、例外の原因を中断、再開できないするオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="c1e72-106">If an orchestration does not include any **CatchException** shape for an exception, the exception causes the orchestration to be Suspended, but not resumable.</span></span> <span data-ttu-id="c1e72-107">これはメッセージとサービス インスタンスの追跡、または WMI スクリプトでは、インスタンスを修復できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="c1e72-107">This means that message and service instance tracking, or a WMI script, cannot recover the instance.</span></span> <span data-ttu-id="c1e72-108">ただし、中断されたに関連付けられているすべてのメッセージを保存することができます (再開できない) インスタンスの診断や手動の再試行の追跡 (または WMI スクリプト) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c1e72-108">However, you can save all messages associated with the Suspended (not Resumable) instance using tracking (or WMI script) for diagnostic and manual retry.</span></span>  
  
 <span data-ttu-id="c1e72-109">問題を診断するには、オーケストレーション デバッガーを使用して、インスタンスが中断される前に実行される直前に図形を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1e72-109">To diagnose the problem, use the Orchestration Debugger to see the last shape executed before the instance is suspended.</span></span> <span data-ttu-id="c1e72-110">オーケストレーション デバッガーを使用して例外の詳細を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1e72-110">You can also view exception details using the Orchestration Debugger.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1e72-111">参照</span><span class="sxs-lookup"><span data-stu-id="c1e72-111">See Also</span></span>  
 <span data-ttu-id="c1e72-112">[オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md) </span><span class="sxs-lookup"><span data-stu-id="c1e72-112">[Investigating Orchestration, Port, and Message Failures](../core/investigating-orchestration-port-and-message-failures.md) </span></span>  
 [<span data-ttu-id="c1e72-113">オーケストレーションのデバッグ</span><span class="sxs-lookup"><span data-stu-id="c1e72-113">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)