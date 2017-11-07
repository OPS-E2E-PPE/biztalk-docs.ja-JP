---
title: "JD Edwards EnterpriseOne アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d46fd3375f49f9fabd6ce8028cc226bce5885db
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="37a7c-102">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="37a7c-102">Troubleshooting JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="37a7c-103">概要</span><span class="sxs-lookup"><span data-stu-id="37a7c-103">Overview</span></span>
<span data-ttu-id="37a7c-104">ここでは、BizTalk Adapter for JD Edwards EnterpriseOne で発生する可能性がある一般的な問題およびエラー メッセージについて説明し、考えられる修正方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37a7c-104">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="37a7c-105">さらに、Windows イベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="37a7c-105">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="37a7c-106">以下のデバッグ/トレース ツールを使用して、アダプターのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="37a7c-106">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="37a7c-107">BizTalk Server のネイティブなデバッグ機能 (たとえば、ポートの [追跡の種類] やオーケストレーション デバッガー)。</span><span class="sxs-lookup"><span data-stu-id="37a7c-107">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="37a7c-108">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="37a7c-108">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="37a7c-109">BTAJDEEnterpriseOneTrace.cmd および .etl ファイル変換ツール (tracerpt.exe や tracedmp.exe など) による、送信元、受信元、および管理メッセージのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="37a7c-109">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="37a7c-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="37a7c-110">Next steps</span></span>
  
-   [<span data-ttu-id="37a7c-111">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="37a7c-111">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="37a7c-112">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="37a7c-112">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="37a7c-113">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="37a7c-113">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)