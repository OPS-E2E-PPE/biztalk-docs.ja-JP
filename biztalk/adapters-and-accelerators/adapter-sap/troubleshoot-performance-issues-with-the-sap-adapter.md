---
title: SAP アダプターを使用したパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c44bf56f73cd23de36e53ae6f0720d863e4f694e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372387"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a><span data-ttu-id="976d6-102">SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="976d6-102">Troubleshoot Performance Issues with the SAP adapter</span></span>
<span data-ttu-id="976d6-103">このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="976d6-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
##  <a name="BKMK_SAPSlowdown"></a> <span data-ttu-id="976d6-104">速度低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="976d6-104">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="976d6-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="976d6-105">**Problem**</span></span>  
  
 <span data-ttu-id="976d6-106">使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。</span><span class="sxs-lookup"><span data-stu-id="976d6-106">When using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="976d6-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="976d6-107">**Cause**</span></span>  
  
 <span data-ttu-id="976d6-108">**EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="976d6-108">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="976d6-109">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="976d6-109">**Resolution**</span></span>  
  
 <span data-ttu-id="976d6-110">設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。</span><span class="sxs-lookup"><span data-stu-id="976d6-110">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="976d6-111">このプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="976d6-111">For more information about this property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span> <span data-ttu-id="976d6-112">バインドのプロパティを設定する方法については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="976d6-112">For instructions on how to set a binding property, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
##  <a name="BKMK_SAPMemLeak"></a> <span data-ttu-id="976d6-113">パラメーターを NULL 値を使用する場合、メモリ リーク</span><span class="sxs-lookup"><span data-stu-id="976d6-113">Possible memory leak when using NULL values for parameters</span></span>  
 <span data-ttu-id="976d6-114">**問題**</span><span class="sxs-lookup"><span data-stu-id="976d6-114">**Problem**</span></span>  
  
 <span data-ttu-id="976d6-115">メモリ リークが発生する場合は、SAP システム内の成果物の呼び出し中に入力、またはテーブル パラメーターの値を指定しないを確認できます。</span><span class="sxs-lookup"><span data-stu-id="976d6-115">You may observe memory leak if you do not specify values for input or table parameters while invoking artifacts in the SAP system.</span></span>  
  
 <span data-ttu-id="976d6-116">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="976d6-116">**Resolution**</span></span>  
  
 <span data-ttu-id="976d6-117">SAP システムで成果物の呼び出し中にすべての入力および表のパラメーターの値を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="976d6-117">Make sure you specify values for all the input and table parameters while invoking an artifact in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976d6-118">参照</span><span class="sxs-lookup"><span data-stu-id="976d6-118">See Also</span></span>  
[<span data-ttu-id="976d6-119">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="976d6-119">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)