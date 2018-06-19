---
title: データが格納されているバッチの状態レポートの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d55aa0e1-095f-434e-8530-f1a946ad4430
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db9831aafce56845fe7b75e91f5369a8860d8996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238594"
---
# <a name="data-stored-for-batching-status-reports"></a><span data-ttu-id="e9954-102">バッチの状態レポート用に格納されるデータ</span><span class="sxs-lookup"><span data-stu-id="e9954-102">Data Stored for Batching Status Reports</span></span>
<span data-ttu-id="e9954-103">ときに、**レポートをオンに**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は各バッチ処理のインスタンスの状態を格納します。</span><span class="sxs-lookup"><span data-stu-id="e9954-103">When the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the status of each batching instance.</span></span> <span data-ttu-id="e9954-104">このプロパティで使用できる、**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e9954-104">This property is in available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="e9954-105">状態は、次のいずれかの値になります。</span><span class="sxs-lookup"><span data-stu-id="e9954-105">The status can be any of the following:</span></span>  
  
-   <span data-ttu-id="e9954-106">**定義されている**: バッチ インスタンスは、構成します。</span><span class="sxs-lookup"><span data-stu-id="e9954-106">**Defined**: The batch instance is configured.</span></span> <span data-ttu-id="e9954-107">バッチ アクティベーションの開始日時は、現在の日時よりも後になっています。</span><span class="sxs-lookup"><span data-stu-id="e9954-107">The batch activation start date time is greater than the current date time.</span></span> <span data-ttu-id="e9954-108">バッチ パラメーターはすべて定義されていますが、バッチは実行されていません (ドキュメントを受理していません)。</span><span class="sxs-lookup"><span data-stu-id="e9954-108">All batch parameters are defined, but the batch is not running (not accepting documents).</span></span>  
  
-   <span data-ttu-id="e9954-109">**アクティブな**: バッチ インスタンスはアクティブ化されており、トランザクション セットを集計しています。</span><span class="sxs-lookup"><span data-stu-id="e9954-109">**Active**: The batch instance has been activated and is aggregating transaction sets.</span></span> <span data-ttu-id="e9954-110">受理/拒否されたトランザクション セットの数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e9954-110">You can view the number of accepted/rejected transaction sets.</span></span>  
  
-   <span data-ttu-id="e9954-111">**リリース**: バッチ リリース条件を満たすと、メッセージ ボックスにリリースされましたが、送信パイプラインによってリリースされていないか、すべてのメッセージを処理する前に、バッチが停止しました。</span><span class="sxs-lookup"><span data-stu-id="e9954-111">**Released**: The batch met the release criteria and was released into the MessageBox, but has not been released by the send pipeline, or that the batch was stopped before processing any messages.</span></span>  
  
-   <span data-ttu-id="e9954-112">**完了**: バッチは EdiSend パイプラインによって送信されました。</span><span class="sxs-lookup"><span data-stu-id="e9954-112">**Completed**: The batch was sent by the EdiSend pipeline.</span></span>  
  
 <span data-ttu-id="e9954-113">バッチが EdiSend パイプラインによって送信されると、UI にあるバッチ レコードを、送信された EDI インターチェンジのレコードに関連付けて、トランザクション セットの詳細を参照できます。</span><span class="sxs-lookup"><span data-stu-id="e9954-113">If the batch was sent by the EdiSend pipeline, you can correlate the batch record in the UI with a record of the sent Edi interchange, and view transaction set details.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9954-114">"完了" 状態のバッチ インスタンスは、1 つのバッチ構成について複数存在することが可能です。</span><span class="sxs-lookup"><span data-stu-id="e9954-114">There may be multiple batch instances with a status of Completed for a batch configuration.</span></span>  
  
 <span data-ttu-id="e9954-115">**バッチ インターチェンジの関連付け**</span><span class="sxs-lookup"><span data-stu-id="e9954-115">**Correlating an Interchange with a Batch**</span></span>  
  
 <span data-ttu-id="e9954-116">BusinessMessageJournal BAM アクティビティにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットを持つ受信 EDI インターチェンジを、同じトランザクション セットを持つ送信バッチ インターチェンジと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e9954-116">The BusinessMessageJournal BAM activity enables [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to correlate a received EDI interchange containing a transaction set with an outgoing batched interchange that contains the same transaction set.</span></span> <span data-ttu-id="e9954-117">実装してこの相関関係情報を使用する方法については、次を参照してください。[送信バッチで受信トランザクション セットを相互に関連付ける](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)です。</span><span class="sxs-lookup"><span data-stu-id="e9954-117">For information about how to implement and use this correlation information, see [Correlating an Incoming Transaction Set with an Outgoing Batch](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9954-118">参照</span><span class="sxs-lookup"><span data-stu-id="e9954-118">See Also</span></span>  
 <span data-ttu-id="e9954-119">[格納されている EDI および AS2 状態レポートのデータ](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="e9954-119">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="e9954-120">[EDI 状態レポートに格納されているデータ](../core/data-stored-for-edi-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="e9954-120">[Data Stored for EDI Status Reports](../core/data-stored-for-edi-status-reports.md) </span></span>  
 [<span data-ttu-id="e9954-121">AS2 状態レポートに格納されているデータ</span><span class="sxs-lookup"><span data-stu-id="e9954-121">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)