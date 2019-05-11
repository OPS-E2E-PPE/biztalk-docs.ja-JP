---
title: JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c92761a93dbbad66f8248c8b95a4f0247f64421c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295756"
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="559d2-102">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="559d2-102">Troubleshooting JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="559d2-103">概要</span><span class="sxs-lookup"><span data-stu-id="559d2-103">Overview</span></span>
<span data-ttu-id="559d2-104">このセクションでは、一般的な問題と BizTalk adapter for JD Edwards EnterpriseOne が発生する可能性があり、それらの考えられる修正方法を提供します。 エラー メッセージについて説明します。</span><span class="sxs-lookup"><span data-stu-id="559d2-104">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="559d2-105">さらに、Windows のイベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="559d2-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="559d2-106">次のデバッグ/トレース ツールを使用すると、アダプターのトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="559d2-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="559d2-107">(たとえば、追跡の種類、ポート) またはオーケストレーション デバッガーの BizTalk Server デバッグ ネイティブです。</span><span class="sxs-lookup"><span data-stu-id="559d2-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="559d2-108">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="559d2-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="559d2-109">BTAJDEEnterpriseOneTrace.cmd およびツールの送信、受信側、および管理メッセージのキャプチャ.etl ファイル変換、tracerpt.exe や tracedmp.exe などです。</span><span class="sxs-lookup"><span data-stu-id="559d2-109">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="559d2-110">次のステップ</span><span class="sxs-lookup"><span data-stu-id="559d2-110">Next steps</span></span>
  
-   [<span data-ttu-id="559d2-111">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="559d2-111">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="559d2-112">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="559d2-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="559d2-113">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="559d2-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)