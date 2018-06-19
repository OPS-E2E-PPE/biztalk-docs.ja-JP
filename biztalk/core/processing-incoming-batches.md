---
title: 受信バッチの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264074"
---
# <a name="processing-incoming-batches"></a><span data-ttu-id="80eae-102">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="80eae-102">Processing Incoming Batches</span></span>
<span data-ttu-id="80eae-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がバッチ EDI インターチェンジを受信したときは、インターチェンジを複数のトランザクション セットに分割して各セットを個別に処理するか、インターチェンジをそのまま保持してすべてのトランザクション セットを 1 つのグループとして処理することができます。</span><span class="sxs-lookup"><span data-stu-id="80eae-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a batched EDI interchange, it can either split the interchange into its transaction sets, processing each one separately, or it can preserve the interchange, processing all transaction sets as a group.</span></span>  
  
 <span data-ttu-id="80eae-104">バッチ処理を決定する、**ローカル ホスト設定**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスの X12 と EDIFACT の両方のアグリーメント。</span><span class="sxs-lookup"><span data-stu-id="80eae-104">You determine batch processing in the **Local Host Settings** page of the one-way agreement tabs in the **Agreement Properties** dialog box for both X12 and EDIFACT agreements.</span></span> <span data-ttu-id="80eae-105">インターチェンジをそのまま保持する場合は、エラーの発生時にインターチェンジまたはトランザクション セットを保留するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="80eae-105">When you preserve the interchange, you have the choice to suspend either the interchange or the transaction sets if an error occurs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80eae-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="80eae-106">In This Section</span></span>  
  
-   [<span data-ttu-id="80eae-107">バッチ EDI インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="80eae-107">Splitting a Batched EDI Interchange</span></span>](../core/splitting-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="80eae-108">HIPAA サブドキュメントの分割</span><span class="sxs-lookup"><span data-stu-id="80eae-108">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
-   [<span data-ttu-id="80eae-109">バッチ EDI インターチェンジを受信した保持</span><span class="sxs-lookup"><span data-stu-id="80eae-109">Preserving a Received Batched EDI Interchange</span></span>](../core/preserving-a-received-batched-edi-interchange.md)