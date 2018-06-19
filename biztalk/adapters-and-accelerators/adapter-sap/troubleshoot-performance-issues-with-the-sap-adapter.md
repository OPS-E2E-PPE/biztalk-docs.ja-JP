---
title: SAP アダプターを使用したパフォーマンスの問題をトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217122"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a><span data-ttu-id="669b9-102">SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="669b9-102">Troubleshoot Performance Issues with the SAP adapter</span></span>
<span data-ttu-id="669b9-103">このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="669b9-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
##  <a name="BKMK_SAPSlowdown"></a><span data-ttu-id="669b9-104">処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="669b9-104">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="669b9-105">**問題**</span><span class="sxs-lookup"><span data-stu-id="669b9-105">**Problem**</span></span>  
  
 <span data-ttu-id="669b9-106">使用する場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。</span><span class="sxs-lookup"><span data-stu-id="669b9-106">When using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="669b9-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="669b9-107">**Cause**</span></span>  
  
 <span data-ttu-id="669b9-108">**EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="669b9-108">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="669b9-109">**解決策**</span><span class="sxs-lookup"><span data-stu-id="669b9-109">**Resolution**</span></span>  
  
 <span data-ttu-id="669b9-110">設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="669b9-110">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="669b9-111">このプロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="669b9-111">For more information about this property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span> <span data-ttu-id="669b9-112">バインディング プロパティを設定する方法の手順については、次を参照してください。 [SAP アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="669b9-112">For instructions on how to set a binding property, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
##  <a name="BKMK_SAPMemLeak"></a><span data-ttu-id="669b9-113">パラメーターを NULL 値を使用する場合の可能なメモリ リーク</span><span class="sxs-lookup"><span data-stu-id="669b9-113">Possible memory leak when using NULL values for parameters</span></span>  
 <span data-ttu-id="669b9-114">**問題**</span><span class="sxs-lookup"><span data-stu-id="669b9-114">**Problem**</span></span>  
  
 <span data-ttu-id="669b9-115">メモリがリークする SAP システム内の成果物の呼び出し中に入力またはテーブルのパラメーターの値を指定しない場合を確認することがあります。</span><span class="sxs-lookup"><span data-stu-id="669b9-115">You may observe memory leak if you do not specify values for input or table parameters while invoking artifacts in the SAP system.</span></span>  
  
 <span data-ttu-id="669b9-116">**解決策**</span><span class="sxs-lookup"><span data-stu-id="669b9-116">**Resolution**</span></span>  
  
 <span data-ttu-id="669b9-117">SAP システム内の成果物の呼び出し中にすべての入力およびテーブルのパラメーターの値を指定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="669b9-117">Make sure you specify values for all the input and table parameters while invoking an artifact in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669b9-118">参照</span><span class="sxs-lookup"><span data-stu-id="669b9-118">See Also</span></span>  
[<span data-ttu-id="669b9-119">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="669b9-119">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)