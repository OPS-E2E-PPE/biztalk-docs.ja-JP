---
title: MySAP Business Suite for BizTalk アダプターの制限事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f289d1f70005e8b4caa0e7c739522cc5590bca58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973715"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="0a239-102">MySAP Business Suite for BizTalk アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="0a239-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="0a239-103">制限事項の一覧</span><span class="sxs-lookup"><span data-stu-id="0a239-103">Limitations list</span></span>
<span data-ttu-id="0a239-104">次の制限事項を呼びます、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0a239-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
- <span data-ttu-id="0a239-105">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft BizTalk Adapter for mySAP Business Suite、以前のリリースのアダプターの互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="0a239-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="0a239-106">このリリースのアダプターは、アダプターの以前のバージョンを使用して生成されたスキーマのメッセージの送受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0a239-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
- <span data-ttu-id="0a239-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ITAB II (階層) テーブルの型を含む、複雑なパラメーター型を持つ Rfc をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0a239-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
- <span data-ttu-id="0a239-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]カスタム ABAP 型を持つ Rfc をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0a239-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
- <span data-ttu-id="0a239-109">基になるクライアント ライブラリで処理をタイムアウトに関する問題のため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0a239-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="0a239-110">BizTalk Server ホストを実行しているコンピューターのシステム時刻を変更する場合、時間は自動的に BizTalk Server ホストで更新されません。</span><span class="sxs-lookup"><span data-stu-id="0a239-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="0a239-111">これは、BizTalk Server の受信ポートを使用する受信操作の不適切な動作につながりますでした。</span><span class="sxs-lookup"><span data-stu-id="0a239-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="0a239-112">この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a239-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a239-113">参照</span><span class="sxs-lookup"><span data-stu-id="0a239-113">See Also</span></span>  
 [<span data-ttu-id="0a239-114">BizTalk Adapter for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="0a239-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)