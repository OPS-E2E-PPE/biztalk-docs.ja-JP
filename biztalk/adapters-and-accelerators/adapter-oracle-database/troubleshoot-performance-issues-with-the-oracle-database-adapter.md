---
title: Oracle データベース アダプターのパフォーマンスに関するトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: 9ba487bcd5d6d245c979dec903613465ae54f8d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962352"
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="d3e0c-102">Oracle データベース アダプターのパフォーマンスに関するをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-102">Troubleshoot performance issues with the Oracle Database adapter</span></span>
<span data-ttu-id="d3e0c-103">このセクションで説明を使用する場合に発生する可能性があるパフォーマンスの問題を解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="d3e0c-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d3e0c-104">Known Issue</span></span>  
 <span data-ttu-id="d3e0c-105">使用する場合に発生する可能性が最も一般的なパフォーマンスの問題を次に示します、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、およびその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-105">The following is the most common performance issue you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with its probable cause and resolution.</span></span>  
  
##  <a name="BKMK_Slowdown"></a><span data-ttu-id="d3e0c-106">処理速度が低下またはスループットのアダプターを BizTalk Server を使用すると停止</span><span class="sxs-lookup"><span data-stu-id="d3e0c-106">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="d3e0c-107">**問題**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-107">**Problem**</span></span>  
  
 <span data-ttu-id="d3e0c-108">使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、アダプターによって送信または受信メッセージの数が遅くなったり、stall にします。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-108">When using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="d3e0c-109">**原因**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-109">**Cause**</span></span>  
  
 <span data-ttu-id="d3e0c-110">**EnableBizTalkCompatibilityMode** binding プロパティが設定されていない Wcf-custom 送信ポートまたは受信ポートを BizTalk Server 管理コンソールでします。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-110">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="d3e0c-111">**解決策**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-111">**Resolution**</span></span>  
  
 <span data-ttu-id="d3e0c-112">設定、 **EnableBizTalkCompatibilityMode**バインディング プロパティを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-112">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="d3e0c-113">このプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-113">For more information about this property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="d3e0c-114">バインディング プロパティを設定する方法の手順については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-114">For instructions on how to set a binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a><span data-ttu-id="d3e0c-115">Oracle データベース アダプターを使用して、FLOAT データ型に関連する操作を実行する場合に、64 ビット コンピューターにメモリ リーク</span><span class="sxs-lookup"><span data-stu-id="d3e0c-115">Possible memory leak on a 64-bit computer when using the Oracle database adapter to perform operations involving FLOAT data type</span></span>  
 <span data-ttu-id="d3e0c-116">**問題**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-116">**Problem**</span></span>  
  
 <span data-ttu-id="d3e0c-117">使用する場合に、メモリ リークが発生する可能性があります、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] FLOAT データ型に関連する操作を実行する 64 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-117">You may experience a memory leak when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on a 64-bit computer to perform operations that involve FLOAT data types.</span></span>  
  
 <span data-ttu-id="d3e0c-118">**解決策**</span><span class="sxs-lookup"><span data-stu-id="d3e0c-118">**Resolution**</span></span>  
  
 <span data-ttu-id="d3e0c-119">.NET インストール\<*バージョン*\> (x64) 64 ビット コンピューターにします。</span><span class="sxs-lookup"><span data-stu-id="d3e0c-119">Install .NET \<*version*\> (x64) on the 64-bit computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e0c-120">参照</span><span class="sxs-lookup"><span data-stu-id="d3e0c-120">See Also</span></span>  
[<span data-ttu-id="d3e0c-121">Oracle のトラブルシューティングを行うデータベース adapter.md</span><span class="sxs-lookup"><span data-stu-id="d3e0c-121">Troubleshoot the Oracle Database adapter.md</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)