---
title: "JD Edwards OneWorld のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, troubleshooting
- troubleshooting [JD Edwards OneWorld adapters]
ms.assetid: 15d73c2a-c6ee-46bf-8837-9c6ae3b098d2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b79e1bab85b52f816788b4e5e3550a5fa8059a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="b88a0-102">JD Edwards OneWorld のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b88a0-102">Troubleshooting JD Edwards OneWorld</span></span>
<span data-ttu-id="b88a0-103">このセクションでは、BizTalk Adapter for JD Edwards OneWorld で発生する可能性がある一般的な問題とエラー メッセージについて説明し、考えられる修正方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b88a0-103">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="b88a0-104">さらに、Windows イベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="b88a0-104">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="b88a0-105">以下のデバッグ/トレース ツールを使用して、アダプターのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b88a0-105">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="b88a0-106">BizTalk Server のネイティブなデバッグ機能 (たとえば、ポートの [追跡の種類] やオーケストレーション デバッガー)。</span><span class="sxs-lookup"><span data-stu-id="b88a0-106">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="b88a0-107">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b88a0-107">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="b88a0-108">BTAJDEOneWorldTrace.cmd および .etl ファイル変換ツール (tracerpt.exe や tracedmp.exe など) による、送信元、受信元、および管理メッセージのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="b88a0-108">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b88a0-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b88a0-109">In This Section</span></span>  
  
-   [<span data-ttu-id="b88a0-110">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="b88a0-110">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="b88a0-111">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="b88a0-111">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="b88a0-112">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b88a0-112">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)