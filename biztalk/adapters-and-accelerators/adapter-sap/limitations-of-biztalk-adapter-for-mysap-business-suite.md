---
title: BizTalk adapter 用 mySAP Business Suite の制限事項 |Microsoft ドキュメント
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
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217082"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="af177-102">BizTalk adapter 用 mySAP Business Suite の制限事項</span><span class="sxs-lookup"><span data-stu-id="af177-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="af177-103">制限事項一覧</span><span class="sxs-lookup"><span data-stu-id="af177-103">Limitations list</span></span>
<span data-ttu-id="af177-104">次はの既知の制限、 [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="af177-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
-   <span data-ttu-id="af177-105">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Microsoft BizTalk Adapter 用 mySAP Business Suite、以前のリリースのアダプターの互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="af177-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="af177-106">アダプターのこのリリースは、アダプターの以前のバージョンを使用して生成されたスキーマを持つメッセージの送受信をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af177-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
-   <span data-ttu-id="af177-107">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ITAB II (階層) テーブル型を含む、複雑なパラメーター型での Rfc をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af177-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
-   <span data-ttu-id="af177-108">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]カスタム ABAP 型を持つ Rfc をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af177-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
-   <span data-ttu-id="af177-109">基になるクライアント ライブラリによるタイムアウトの処理に関する問題のため、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]コマンドと接続のタイムアウトをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="af177-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="af177-110">BizTalk Server ホストを実行しているコンピューターのシステム時刻を変更する場合、時間は自動的に BizTalk Server ホストで更新されません。</span><span class="sxs-lookup"><span data-stu-id="af177-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="af177-111">これは、BizTalk Server の受信ポートを使用する受信操作の不適切な動作をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af177-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="af177-112">この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af177-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af177-113">参照</span><span class="sxs-lookup"><span data-stu-id="af177-113">See Also</span></span>  
 [<span data-ttu-id="af177-114">MySAP Business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="af177-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)