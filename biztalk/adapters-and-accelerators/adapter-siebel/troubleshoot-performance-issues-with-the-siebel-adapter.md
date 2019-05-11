---
title: Siebel アダプターを使用したパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c5ecd89cfe3ea284bdc3264e8db597f29fdde7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370409"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a><span data-ttu-id="f5536-102">Siebel アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f5536-102">Troubleshoot Performance Issues with the Siebel adapter</span></span>
<span data-ttu-id="f5536-103">このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f5536-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="f5536-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="f5536-104">Known Issues</span></span>  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="f5536-105">速度低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="f5536-105">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="f5536-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="f5536-106">**Problem**</span></span>  
  
 <span data-ttu-id="f5536-107">使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。</span><span class="sxs-lookup"><span data-stu-id="f5536-107">When using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="f5536-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="f5536-108">**Cause**</span></span>  
  
 <span data-ttu-id="f5536-109">**EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="f5536-109">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="f5536-110">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="f5536-110">**Resolution**</span></span>  
  
 <span data-ttu-id="f5536-111">設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。</span><span class="sxs-lookup"><span data-stu-id="f5536-111">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="f5536-112">このプロパティの詳細については、次を参照してください。 [Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5536-112">For more information about this property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span> <span data-ttu-id="f5536-113">バインドのプロパティを設定する方法については、次を参照してください。 [for Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5536-113">For instructions on how to set a binding property, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5536-114">参照</span><span class="sxs-lookup"><span data-stu-id="f5536-114">See Also</span></span>  
[<span data-ttu-id="f5536-115">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f5536-115">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)