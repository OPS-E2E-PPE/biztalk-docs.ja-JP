---
title: Oracle データベース アダプターのパフォーマンスの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23c36e2df514f6caf5e654a99c4d57a5c4b41e65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375903"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="52ae3-102">Oracle データベース アダプターのパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="52ae3-102">Troubleshoot performance issues with the Oracle Database adapter</span></span>
<span data-ttu-id="52ae3-103">このセクションを使用する場合に発生する可能性のあるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="52ae3-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="52ae3-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="52ae3-104">Known Issue</span></span>  
 <span data-ttu-id="52ae3-105">使用する場合に発生する可能性が最も一般的なパフォーマンスの問題を次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と共にその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="52ae3-105">The following is the most common performance issue you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with its probable cause and resolution.</span></span>  
  
##  <a name="BKMK_Slowdown"></a> <span data-ttu-id="52ae3-106">速度低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="52ae3-106">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="52ae3-107">**問題**</span><span class="sxs-lookup"><span data-stu-id="52ae3-107">**Problem**</span></span>  
  
 <span data-ttu-id="52ae3-108">使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、停止します。</span><span class="sxs-lookup"><span data-stu-id="52ae3-108">When using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="52ae3-109">**原因**</span><span class="sxs-lookup"><span data-stu-id="52ae3-109">**Cause**</span></span>  
  
 <span data-ttu-id="52ae3-110">**EnableBizTalkCompatibilityMode**プロパティのバインドが設定されておらず、Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="52ae3-110">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="52ae3-111">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="52ae3-111">**Resolution**</span></span>  
  
 <span data-ttu-id="52ae3-112">設定、 **EnableBizTalkCompatibilityMode**プロパティを True にバインドします。</span><span class="sxs-lookup"><span data-stu-id="52ae3-112">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="52ae3-113">このプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="52ae3-113">For more information about this property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="52ae3-114">バインドのプロパティを設定する方法については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="52ae3-114">For instructions on how to set a binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a><span data-ttu-id="52ae3-115">FLOAT データ型に関連する操作を実行する Oracle データベース アダプターを使用する場合は、64 ビット コンピューターでメモリ リーク</span><span class="sxs-lookup"><span data-stu-id="52ae3-115">Possible memory leak on a 64-bit computer when using the Oracle database adapter to perform operations involving FLOAT data type</span></span>  
 <span data-ttu-id="52ae3-116">**問題**</span><span class="sxs-lookup"><span data-stu-id="52ae3-116">**Problem**</span></span>  
  
 <span data-ttu-id="52ae3-117">使用する場合にメモリ リークが発生する可能性があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] FLOAT データ型に関連する操作を実行する 64 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="52ae3-117">You may experience a memory leak when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on a 64-bit computer to perform operations that involve FLOAT data types.</span></span>  
  
 <span data-ttu-id="52ae3-118">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="52ae3-118">**Resolution**</span></span>  
  
 <span data-ttu-id="52ae3-119">.NET インストール\<*バージョン*\> (x64) 64 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="52ae3-119">Install .NET \<*version*\> (x64) on the 64-bit computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ae3-120">参照</span><span class="sxs-lookup"><span data-stu-id="52ae3-120">See Also</span></span>  
[<span data-ttu-id="52ae3-121">Oracle のトラブルシューティングを行うデータベース adapter.md</span><span class="sxs-lookup"><span data-stu-id="52ae3-121">Troubleshoot the Oracle Database adapter.md</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)