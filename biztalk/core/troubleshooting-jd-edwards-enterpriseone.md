---
title: "JD Edwards EnterpriseOne のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting [JD Edwards EnterpriseOne adapters]
- JD Edwards EnterpriseOne adapters, troubleshooting
- adapters [JD Edwards EnterpriseOne adapters], troubleshooting
ms.assetid: 7b3e68fa-b81d-4767-ab62-3200ce89d81c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d32a4db56dc60d3a57d6e43985cc30a2868098bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-jd-edwards-enterpriseone"></a><span data-ttu-id="5d6db-102">JD Edwards EnterpriseOne のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5d6db-102">Troubleshooting JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="5d6db-103">ここでは、BizTalk Adapter for JD Edwards EnterpriseOne で発生する可能性がある一般的な問題およびエラー メッセージについて説明し、考えられる修正方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d6db-103">This section describes common issues and error messages you might encounter in BizTalk Adapter for JD Edwards EnterpriseOne and provides possible corrections for them.</span></span> <span data-ttu-id="5d6db-104">さらに、Windows イベント トレーシングの使用について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d6db-104">In addition, it discusses the use of Event Tracing for Windows.</span></span>  
  
 <span data-ttu-id="5d6db-105">以下のデバッグ/トレース ツールを使用して、アダプターのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5d6db-105">You can use the following debugging/tracing tools to troubleshoot the adapter:</span></span>  
  
-   <span data-ttu-id="5d6db-106">BizTalk Server のネイティブなデバッグ機能 (たとえば、ポートの [追跡の種類] やオーケストレーション デバッガー)。</span><span class="sxs-lookup"><span data-stu-id="5d6db-106">Native BizTalk Server debugging (for example, the Tracking Type on your port or the Orchestration Debugger).</span></span>  
  
-   <span data-ttu-id="5d6db-107">イベント ログに送信されるエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="5d6db-107">Error messages submitted to the Event Log.</span></span>  
  
-   <span data-ttu-id="5d6db-108">BTAJDEEnterpriseOneTrace.cmd および .etl ファイル変換ツール (tracerpt.exe や tracedmp.exe など) による、送信元、受信元、および管理メッセージのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="5d6db-108">The capture of transmitter, receiver, and management messages through BTAJDEEnterpriseOneTrace.cmd and a tool that converts.etl files, such as tracerpt.exe or tracedmp.exe.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d6db-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5d6db-109">In This Section</span></span>  
  
-   [<span data-ttu-id="5d6db-110">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="5d6db-110">Error Messages</span></span>](../core/error-messages1.md)  
  
-   [<span data-ttu-id="5d6db-111">Windows イベント トレーシングの使用</span><span class="sxs-lookup"><span data-stu-id="5d6db-111">Using Event Tracing for Windows</span></span>](../core/using-event-tracing-for-windows4.md)  
  
-   [<span data-ttu-id="5d6db-112">アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5d6db-112">Troubleshooting the Adapter</span></span>](../core/troubleshooting-the-adapter1.md)