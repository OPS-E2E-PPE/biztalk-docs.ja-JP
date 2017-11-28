---
title: "バッチ EDI インターチェンジの分割 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441eafe79de57963dc1df5ac19334542f41a23d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-a-batched-edi-interchange"></a><span data-ttu-id="ef811-102">バッチ EDI インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="ef811-102">Splitting a Batched EDI Interchange</span></span>
> [!NOTE]
>  <span data-ttu-id="ef811-103">このトピックに記載されているすべてのユーザー インターフェイス オプションで使用できる、**ローカル ホスト設定**ページ (**受信者の設定**セクション) の一方向アグリーメント タブの**アグリーメントプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ef811-103">All the user interface options mentioned in this topic are available in the **Local Host Settings** page (**Receiver’s Settings** section) of the one-way agreement tabs in the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="ef811-104">EDI 受信パイプラインの分割は受信 EDI インターチェンジのバッチを設定した場合、**受信バッチ処理オプション**アグリーメント プロパティを**トランザクション セットとして分割されたインターチェンジ**です。</span><span class="sxs-lookup"><span data-stu-id="ef811-104">The EDI receive pipeline splits an incoming EDI interchange batch if you have set the **Inbound batch processing option** agreement property to **Split Interchange as Transaction Sets**.</span></span>  
  
 <span data-ttu-id="ef811-105">EDI 受信パイプラインが受信バッチ EDI インターチェンジを分割するときには、各トランザクション セット/メッセージにつき 1 つの XML ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef811-105">When the EDI receive pipeline splits an incoming batched EDI interchange, it creates one XML file for each EDI transaction set/message.</span></span> <span data-ttu-id="ef811-106">EDI 受信パイプラインは、インターチェンジ全体およびグループ ヘッダーを、インターチェンジから分割された各トランザクション セットのコンテキストに昇格させます。</span><span class="sxs-lookup"><span data-stu-id="ef811-106">The pipeline promotes the entire interchange and group headers into the context of each transaction set split from the interchange.</span></span> <span data-ttu-id="ef811-107">また、ISA6、GS1、GS2 などの特定のインターチェンジおよびグループ ヘッダーを昇格させ、これらのフィールドをルーティングに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ef811-107">It also promotes certain specific interchange and group headers, such as ISA6, GS1, and GS2, so that these fields can be used for routing.</span></span> <span data-ttu-id="ef811-108">ヘッダーのセキュリティ情報をマスクするを選択すると、**セキュリティ/認証/パスワード情報をマスク**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="ef811-108">You can mask the security information in the header by selecting the **Mask security/authorization/password information** property.</span></span>  
  
 <span data-ttu-id="ef811-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でインターチェンジのトランザクション セットへの分割が試行されると、特定の ISA (ISA1 ～ ISA13) または UNB ヘッダー フィールド内のすべてのエラーは、インターチェンジ拒否の原因になります。</span><span class="sxs-lookup"><span data-stu-id="ef811-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to split an interchange into transaction sets, any error in certain ISA (ISA1 through ISA13) or UNB header fields will lead to the interchange being rejected.</span></span> <span data-ttu-id="ef811-110">これは、アグリーメントまたはフォールバック アグリーメントのプロパティで、重複するインターチェンジ制御番号の有無を確認する機能がオンになっている場合に、インターチェンジ制御番号が重複する場合にも該当します。</span><span class="sxs-lookup"><span data-stu-id="ef811-110">This is also the case when the interchange control number is a duplicate, if the check for a duplicate interchange control number is enabled in the agreement or fallback agreement properties.</span></span> <span data-ttu-id="ef811-111">他のインターチェンジのヘッダー フィールド (X12 インターチェンジの ISA1 ～ ISA13 以外) およびグループ ヘッダー フィールド内のエラーでは、インターチェンジ処理の失敗は発生しません。</span><span class="sxs-lookup"><span data-stu-id="ef811-111">An error in other interchange header fields (other than ISA1 through ISA13 for X12 interchange) or in the group header fields would not cause interchange processing to fail.</span></span>  
  
 <span data-ttu-id="ef811-112">場合**エラーのトランザクション セットを中断するトランザクション セットとして分割されたインターチェンジ**がアグリーメント プロパティで選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定エラーが発生した場合、トランザクションが中断されます。</span><span class="sxs-lookup"><span data-stu-id="ef811-112">If **Split Interchange as Transaction Sets - suspend Transaction Sets on Error** is selected in agreement properties, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the transaction set if an error occurs.</span></span> <span data-ttu-id="ef811-113">場合**– のトランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**が選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はインターチェンジを中断します。</span><span class="sxs-lookup"><span data-stu-id="ef811-113">If **Split Interchange as Transaction Sets – suspend Interchange on Error** is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
 <span data-ttu-id="ef811-114">各 XML バッチ要素は MessageBox にルーティングされ、そのバッチ要素をサブスクライブする送信ポートまたはオーケストレーションによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="ef811-114">Each XML batch element is routed to the MessageBox, and processed by the send ports or orchestrations that subscribe to the batch element.</span></span> <span data-ttu-id="ef811-115">インターチェンジ内のトランザクション セットの順序は、分割メッセージとして処理された後は保持されません。</span><span class="sxs-lookup"><span data-stu-id="ef811-115">The ordering of transaction sets in the interchange may not be retained after they are processed as split messages.</span></span> <span data-ttu-id="ef811-116">受信側では、メッセージはインターチェンジに表示された順序に従って処理され、MessageBox に配置されます。ただし、送信側でもそれと同じ順序を維持するには、コンボイまたは順次配送の送信ポートを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef811-116">On the receive side, the messages will be processed in the order that they appear in the interchange, and they will be placed in the MessageBox in that order, but you would have to use convoys or ordered delivery send ports to maintain that order on the send side.</span></span>  
  
 <span data-ttu-id="ef811-117">バッチから分割された要素が送信バッチに含まれる場合、BatchMarker パイプライン コンポーネントは必須プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="ef811-117">If the elements split from a batch will be included in an outgoing batch, the BatchMarker pipeline component promotes the required properties.</span></span> <span data-ttu-id="ef811-118">詳細については、次を参照してください。[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="ef811-118">For more information, see [Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef811-119">参照</span><span class="sxs-lookup"><span data-stu-id="ef811-119">See Also</span></span>  
 <span data-ttu-id="ef811-120">[受信バッチの処理](../core/processing-incoming-batches.md) </span><span class="sxs-lookup"><span data-stu-id="ef811-120">[Processing Incoming Batches](../core/processing-incoming-batches.md) </span></span>  
 [<span data-ttu-id="ef811-121">送信 EDI メッセージをバッチ処理</span><span class="sxs-lookup"><span data-stu-id="ef811-121">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)