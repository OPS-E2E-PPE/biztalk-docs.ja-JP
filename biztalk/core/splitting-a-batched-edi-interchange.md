---
title: バッチ EDI インターチェンジの分割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a771d499116093b36605d2e3d518774a5b5994c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243231"
---
# <a name="splitting-a-batched-edi-interchange"></a><span data-ttu-id="19187-102">バッチ EDI インターチェンジの分割</span><span class="sxs-lookup"><span data-stu-id="19187-102">Splitting a Batched EDI Interchange</span></span>
> [!NOTE]
>  <span data-ttu-id="19187-103">このトピックで説明されているすべてのユーザー インターフェイスのオプションが表示されます、**ローカル ホスト設定**ページ (**受信者の設定**セクション) の一方向アグリーメント タブの**アグリーメントプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="19187-103">All the user interface options mentioned in this topic are available in the **Local Host Settings** page (**Receiver’s Settings** section) of the one-way agreement tabs in the **Agreement Properties** dialog box.</span></span>  
  
 <span data-ttu-id="19187-104">EDI 受信パイプラインの分割、受信 EDI インターチェンジのバッチを設定した場合、**受信バッチ処理オプション**アグリーメント プロパティを**インターチェンジをトランザクション セットとして分割**します。</span><span class="sxs-lookup"><span data-stu-id="19187-104">The EDI receive pipeline splits an incoming EDI interchange batch if you have set the **Inbound batch processing option** agreement property to **Split Interchange as Transaction Sets**.</span></span>  
  
 <span data-ttu-id="19187-105">EDI 受信パイプラインが受信バッチ EDI インターチェンジを分割、各 EDI トランザクション セット/メッセージの 1 つの XML ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="19187-105">When the EDI receive pipeline splits an incoming batched EDI interchange, it creates one XML file for each EDI transaction set/message.</span></span> <span data-ttu-id="19187-106">パイプラインはインターチェンジ全体を昇格し、各トランザクションのコンテキストにグループ ヘッダーは、インターチェンジから分割を設定します。</span><span class="sxs-lookup"><span data-stu-id="19187-106">The pipeline promotes the entire interchange and group headers into the context of each transaction set split from the interchange.</span></span> <span data-ttu-id="19187-107">また、ISA6、GS1、GS2 などの特定のインターチェンジおよびグループ ヘッダーを昇格させ、これらのフィールドをルーティングに使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="19187-107">It also promotes certain specific interchange and group headers, such as ISA6, GS1, and GS2, so that these fields can be used for routing.</span></span> <span data-ttu-id="19187-108">ヘッダーのセキュリティ情報をマスクするを選択すると、**セキュリティ/認証/パスワード情報をマスク**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="19187-108">You can mask the security information in the header by selecting the **Mask security/authorization/password information** property.</span></span>  
  
 <span data-ttu-id="19187-109">ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]しようと、インターチェンジのトランザクションに分割すると設定すると、エラーを特定の ISA (ISA1 ~ ISA13) または UNB ヘッダー フィールドは、インターチェンジ拒否につながります。</span><span class="sxs-lookup"><span data-stu-id="19187-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] attempts to split an interchange into transaction sets, any error in certain ISA (ISA1 through ISA13) or UNB header fields will lead to the interchange being rejected.</span></span> <span data-ttu-id="19187-110">これは、ケースにもインターチェンジ制御番号が重複するアグリーメントまたはフォールバック アグリーメントのプロパティで、重複するインターチェンジ制御番号のチェックが有効になっている場合。</span><span class="sxs-lookup"><span data-stu-id="19187-110">This is also the case when the interchange control number is a duplicate, if the check for a duplicate interchange control number is enabled in the agreement or fallback agreement properties.</span></span> <span data-ttu-id="19187-111">その他のインターチェンジのヘッダー フィールド内のエラー (X12 の ISA1 ~ ISA13 以外のインターチェンジ) またはグループ ヘッダー フィールドは、インターチェンジの処理が失敗します。</span><span class="sxs-lookup"><span data-stu-id="19187-111">An error in other interchange header fields (other than ISA1 through ISA13 for X12 interchange) or in the group header fields would not cause interchange processing to fail.</span></span>  
  
 <span data-ttu-id="19187-112">場合**エラーのトランザクション セットを中断するトランザクション セットとして分割されたインターチェンジ**がアグリーメントのプロパティで選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定エラーが発生した場合、トランザクションが中断されます。</span><span class="sxs-lookup"><span data-stu-id="19187-112">If **Split Interchange as Transaction Sets - suspend Transaction Sets on Error** is selected in agreement properties, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the transaction set if an error occurs.</span></span> <span data-ttu-id="19187-113">場合 **– のトランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**が選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="19187-113">If **Split Interchange as Transaction Sets – suspend Interchange on Error** is selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
 <span data-ttu-id="19187-114">各 XML バッチ要素は、MessageBox にルーティングし、送信ポートまたはバッチ要素をサブスクライブするオーケストレーションによって処理します。</span><span class="sxs-lookup"><span data-stu-id="19187-114">Each XML batch element is routed to the MessageBox, and processed by the send ports or orchestrations that subscribe to the batch element.</span></span> <span data-ttu-id="19187-115">分割メッセージとして処理された後、インターチェンジ内のトランザクション セットの順序を保持されません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19187-115">The ordering of transaction sets in the interchange may not be retained after they are processed as split messages.</span></span> <span data-ttu-id="19187-116">受信側でメッセージをインターチェンジに表示されるとその順序でメッセージ ボックス内に配置されますが、コンボイを使用する必要がありますまたは順次配送の送信ポート、送信側で順序を維持する順序で処理されます。</span><span class="sxs-lookup"><span data-stu-id="19187-116">On the receive side, the messages will be processed in the order that they appear in the interchange, and they will be placed in the MessageBox in that order, but you would have to use convoys or ordered delivery send ports to maintain that order on the send side.</span></span>  
  
 <span data-ttu-id="19187-117">バッチから分割された要素は、送信バッチに含まれているが場合、BatchMarker パイプライン コンポーネントは、必要なプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="19187-117">If the elements split from a batch will be included in an outgoing batch, the BatchMarker pipeline component promotes the required properties.</span></span> <span data-ttu-id="19187-118">詳細については、次を参照してください。[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="19187-118">For more information, see [Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19187-119">参照</span><span class="sxs-lookup"><span data-stu-id="19187-119">See Also</span></span>  
 <span data-ttu-id="19187-120">[受信バッチの処理](../core/processing-incoming-batches.md) </span><span class="sxs-lookup"><span data-stu-id="19187-120">[Processing Incoming Batches](../core/processing-incoming-batches.md) </span></span>  
 [<span data-ttu-id="19187-121">送信 EDI メッセージのバッチ処理</span><span class="sxs-lookup"><span data-stu-id="19187-121">Batching Outgoing EDI Messages</span></span>](../core/batching-outgoing-edi-messages.md)