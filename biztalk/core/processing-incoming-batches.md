---
title: 受信バッチの処理 |Microsoft Docs
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
ms.openlocfilehash: a6a7b40401623a867d706d82c50eb150a84a9eff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299817"
---
# <a name="processing-incoming-batches"></a><span data-ttu-id="4e076-102">受信バッチの処理</span><span class="sxs-lookup"><span data-stu-id="4e076-102">Processing Incoming Batches</span></span>
<span data-ttu-id="4e076-103">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチ EDI インターチェンジの受信をそれぞれを個別に、処理、トランザクション セットにインターチェンジを分割することができますか、またはグループとしてすべてのトランザクション セットの処理、インターチェンジを保持できます。</span><span class="sxs-lookup"><span data-stu-id="4e076-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a batched EDI interchange, it can either split the interchange into its transaction sets, processing each one separately, or it can preserve the interchange, processing all transaction sets as a group.</span></span>  
  
 <span data-ttu-id="4e076-104">バッチ処理を決定する、**ローカル ホスト設定**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ**X12 と EDIFACT の両方のアグリーメントのダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4e076-104">You determine batch processing in the **Local Host Settings** page of the one-way agreement tabs in the **Agreement Properties** dialog box for both X12 and EDIFACT agreements.</span></span> <span data-ttu-id="4e076-105">インターチェンジを保存するときにエラーが発生した場合、インターチェンジまたはトランザクション セットを中断するかの選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="4e076-105">When you preserve the interchange, you have the choice to suspend either the interchange or the transaction sets if an error occurs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4e076-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4e076-106">In This Section</span></span>  
  
-   [<span data-ttu-id="4e076-107">バッチ EDI インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="4e076-107">Splitting a Batched EDI Interchange</span></span>](../core/splitting-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="4e076-108">HIPAA サブドキュメントの分割</span><span class="sxs-lookup"><span data-stu-id="4e076-108">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
-   [<span data-ttu-id="4e076-109">受信したバッチ EDI インターチェンジの保存</span><span class="sxs-lookup"><span data-stu-id="4e076-109">Preserving a Received Batched EDI Interchange</span></span>](../core/preserving-a-received-batched-edi-interchange.md)