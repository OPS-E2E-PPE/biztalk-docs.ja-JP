---
title: JD Edwards OneWorld のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 15d73c2a-c6ee-46bf-8837-9c6ae3b098d2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85c4b1099814c4cf7489f18ae5cd921f46f180bc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015609"
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="2dfb6-102">JD Edwards OneWorld のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dfb6-102">Troubleshooting JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="2dfb6-103">概要</span><span class="sxs-lookup"><span data-stu-id="2dfb6-103">Overview</span></span>
<span data-ttu-id="2dfb6-104">このセクションでは、BizTalk Adapter for JD Edwards OneWorld で発生する可能性がある一般的な問題とエラー メッセージについて説明し、考えられる修正方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-104">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="2dfb6-105">さらに、Windows イベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="2dfb6-106">以下のデバッグ/トレース ツールを使用して、アダプターのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="2dfb6-107">BizTalk Server のネイティブなデバッグ機能 (たとえば、ポートの [追跡の種類] やオーケストレーション デバッガー)。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="2dfb6-108">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="2dfb6-109">BTAJDEOneWorldTrace.cmd および .etl ファイル変換ツール (tracerpt.exe や tracedmp.exe など) による、送信元、受信元、および管理メッセージのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="2dfb6-109">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2dfb6-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="2dfb6-110">Next steps</span></span>
  
-   [<span data-ttu-id="2dfb6-111">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="2dfb6-111">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="2dfb6-112">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="2dfb6-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="2dfb6-113">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2dfb6-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)