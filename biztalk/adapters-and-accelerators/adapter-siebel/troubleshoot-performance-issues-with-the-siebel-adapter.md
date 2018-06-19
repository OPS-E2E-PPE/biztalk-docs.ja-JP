---
title: Siebel アダプターのパフォーマンスの問題のトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: 6443dd8b96b19b3cf42f6444ba1ae6c16f2b4ee6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221994"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a><span data-ttu-id="564d0-102">Siebel アダプターのパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="564d0-102">Troubleshoot Performance Issues with the Siebel adapter</span></span>
<span data-ttu-id="564d0-103">このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="564d0-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="564d0-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="564d0-104">Known Issues</span></span>  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="564d0-105">処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="564d0-105">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="564d0-106">**問題**</span><span class="sxs-lookup"><span data-stu-id="564d0-106">**Problem**</span></span>  
  
 <span data-ttu-id="564d0-107">使用する場合、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。</span><span class="sxs-lookup"><span data-stu-id="564d0-107">When using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="564d0-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="564d0-108">**Cause**</span></span>  
  
 <span data-ttu-id="564d0-109">**EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="564d0-109">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="564d0-110">**解決策**</span><span class="sxs-lookup"><span data-stu-id="564d0-110">**Resolution**</span></span>  
  
 <span data-ttu-id="564d0-111">設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="564d0-111">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="564d0-112">このプロパティの詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインドのプロパティについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="564d0-112">For more information about this property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span> <span data-ttu-id="564d0-113">バインディング プロパティを設定する方法の手順については、次を参照してください。 [Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="564d0-113">For instructions on how to set a binding property, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="564d0-114">参照</span><span class="sxs-lookup"><span data-stu-id="564d0-114">See Also</span></span>  
[<span data-ttu-id="564d0-115">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="564d0-115">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)