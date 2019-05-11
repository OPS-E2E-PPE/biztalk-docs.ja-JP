---
title: JD Edwards OneWorld のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: f8d6ee388cc2d19cca67e8f4eda2d4d6cd11c05d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295753"
---
# <a name="troubleshooting-jd-edwards-oneworld"></a><span data-ttu-id="1f090-102">JD Edwards OneWorld のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1f090-102">Troubleshooting JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="1f090-103">概要</span><span class="sxs-lookup"><span data-stu-id="1f090-103">Overview</span></span>
<span data-ttu-id="1f090-104">このセクションでは、一般的な問題と BizTalk adapter for JD Edwards OneWorld が発生する可能性があり、考えられる修正方法を提供するエラー メッセージについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1f090-104">This section describes common issues and error messages that you might encounter in BizTalk Adapter for JD Edwards OneWorld, and provides possible corrections.</span></span> <span data-ttu-id="1f090-105">さらに、Windows のイベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="1f090-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="1f090-106">次のデバッグ/トレース ツールを使用すると、アダプターのトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="1f090-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="1f090-107">(たとえば、追跡の種類、ポート) またはオーケストレーション デバッガーの BizTalk Server デバッグ ネイティブです。</span><span class="sxs-lookup"><span data-stu-id="1f090-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="1f090-108">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1f090-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="1f090-109">BTAJDEOneWorldTrace.cmd および .etl ファイルで、tracerpt.exe や tracedmp.exe などに変換するツールの送信、受信側、および管理メッセージのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="1f090-109">The capture of transmitter, receiver, and management messages through BTAJDEOneWorldTrace.cmd and a tool that converts the .etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1f090-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="1f090-110">Next steps</span></span>
  
-   [<span data-ttu-id="1f090-111">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="1f090-111">Error Messages</span></span>](../core/error-messages2.md)  
  
-   [<span data-ttu-id="1f090-112">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="1f090-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows2.md)  
  
-   [<span data-ttu-id="1f090-113">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1f090-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter3.md)