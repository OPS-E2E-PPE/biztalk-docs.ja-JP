---
title: EDIFACT CONTRL 確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8489f89714871f23fec329b44cafb4180f91c874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996899"
---
# <a name="edifact-contrl-acknowledgment"></a><span data-ttu-id="4675f-102">EDIFACT CONTRL 確認</span><span class="sxs-lookup"><span data-stu-id="4675f-102">EDIFACT CONTRL Acknowledgment</span></span>
<span data-ttu-id="4675f-103">CONTRL 確認 (ACK) は、EDIFACT エンコード メッセージの技術確認および機能確認として機能します。</span><span class="sxs-lookup"><span data-stu-id="4675f-103">The CONTRL acknowledgment (ACK) serves as both technical and functional acknowledgment for EDIFACT-encoded messages.</span></span> <span data-ttu-id="4675f-104">技術確認としての CONTRL メッセージは、インターチェンジの受信を示します。</span><span class="sxs-lookup"><span data-stu-id="4675f-104">As a technical acknowledgment, the CONTRL message indicates receipt of an interchange.</span></span> <span data-ttu-id="4675f-105">機能確認としての CONTRL メッセージは、エラーまたはサポートされていない機能の一覧を含んでおり、受信したインターチェンジ、グループ、またはメッセージの受理または拒否を示します。</span><span class="sxs-lookup"><span data-stu-id="4675f-105">As a functional acknowledgment, the CONTRL message indicates acceptance or rejection of the received interchange, group, or message, with a list of errors or unsupported functionality.</span></span>  
  
 <span data-ttu-id="4675f-106">CONTRL メッセージの全文は、機能確認として機能します。</span><span class="sxs-lookup"><span data-stu-id="4675f-106">The full CONTRL message serves as the functional ACK.</span></span> <span data-ttu-id="4675f-107">機能確認の各セクションは、技術確認のために再使用されます。</span><span class="sxs-lookup"><span data-stu-id="4675f-107">Sections of the functional ACK are reused for the technical ACK.</span></span> <span data-ttu-id="4675f-108">送信元パーティまたはグローバル プロパティでは、技術と機能の両方の Ack をパーティのプロパティで選択した、BizTalk Server は 2 つの CONTRL メッセージを生成: 技術 CONTRL 確認と機能 CONTRL 確認</span><span class="sxs-lookup"><span data-stu-id="4675f-108">If you have selected both technical and functional ACKs in the party properties for a sending party or in global properties, BizTalk Server will generate two CONTRL messages: a technical CONTRL ACK and a functional CONTRL ACK.</span></span>  
  
 <span data-ttu-id="4675f-109">CONTRL 確認は、efact _ に準拠している\<バージョン番号\>>_contrl.xsd スキーマ。</span><span class="sxs-lookup"><span data-stu-id="4675f-109">The CONTRL ACK conforms to the EFACT_\<Version number\>_CONTRL.xsd schema.</span></span>  
  
## <a name="technical-acknowledgement"></a><span data-ttu-id="4675f-110">技術確認</span><span class="sxs-lookup"><span data-stu-id="4675f-110">Technical Acknowledgement</span></span>  
 <span data-ttu-id="4675f-111">技術確認は、インターチェンジの受信に関する次の内容を意味します。</span><span class="sxs-lookup"><span data-stu-id="4675f-111">A technical ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="4675f-112">件名のインターチェンジを受信したこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-112">has received the subject interchange;</span></span>  
  
-   <span data-ttu-id="4675f-113">UCI レポート セグメントにコピーされたデータ要素の構文が正しいかどうかがチェックされている件名のインターチェンジの各部を確認したこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-113">acknowledges the parts of the subject interchange that have been checked in order to ensure that the data elements copied into the reporting UCI segment are syntactically correct;</span></span>  
  
-   <span data-ttu-id="4675f-114">件名のインターチェンジの他の部分を受理または拒否したことを送信者に通知する責任を受け入れたこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-114">has accepted responsibility for notifying the sender of acknowledgement or rejection of the other parts of the subject interchange;</span></span>  
  
-   <span data-ttu-id="4675f-115">送信者に確実に通知するための適切な対策を講じていること。</span><span class="sxs-lookup"><span data-stu-id="4675f-115">and has taken reasonable precautions in order to ensure that the sender is so notified.</span></span>  
  
## <a name="functional-acknowledgement"></a><span data-ttu-id="4675f-116">機能確認</span><span class="sxs-lookup"><span data-stu-id="4675f-116">Functional Acknowledgement</span></span>  
 <span data-ttu-id="4675f-117">機能確認は、インターチェンジの受信に関する次の内容を意味します。</span><span class="sxs-lookup"><span data-stu-id="4675f-117">A functional ACK implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="4675f-118">確認したインターチェンジの参照レベルを受信していること。</span><span class="sxs-lookup"><span data-stu-id="4675f-118">has received the referenced levels(s) of the interchange acknowledged;</span></span>  
  
- <span data-ttu-id="4675f-119">確認した参照レベルに、インターチェンジの後続処理を妨げるような致命的な構文エラーがないことをチェックしたこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-119">has checked that there are no fatal syntactic errors in the acknowledged referenced level that prevents further processing of the interchange;</span></span>  
  
- <span data-ttu-id="4675f-120">サービス セグメントの確認部分すべてが意味的に正しい (エラーが報告されていない) ことをチェックしたこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-120">has checked that all acknowledged parts of service segments are semantically correct (if no errors are reported);</span></span>  
  
- <span data-ttu-id="4675f-121">サービス セグメントの確認した参照レベル内で要求されたアクションに準拠すること。</span><span class="sxs-lookup"><span data-stu-id="4675f-121">will comply with the actions requested in the acknowledged referenced-levels of the service segments;</span></span>  
  
- <span data-ttu-id="4675f-122">前述の構文的なエラーまたはセマンティック エラーが関連部分で後から検出された場合、または、送信された CONTRL メッセージ内でその部分が確認された後でなんらかの他の理由によりこの部分の処理ができない場合に、CONTRL メッセージの送信以外の方法で送信者に通知する責任を受け入れたこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-122">has accepted responsibility for notifying the sender by other means than sending a CONTRL message if any syntactic or semantic errors as described above, are later detected in the relevant part, or the part cannot be processed for some other reason after the part has been acknowledged in a submitted CONTRL message;</span></span>  
  
- <span data-ttu-id="4675f-123">このようなエラーを検出し、送信者に通知するための適切な対策を講じていること。</span><span class="sxs-lookup"><span data-stu-id="4675f-123">and has taken reasonable precautions in order to ensure that such errors are detected and that the sender is notified.</span></span>  
  
  <span data-ttu-id="4675f-124">拒否は、インターチェンジの受信に関する次の内容を意味します。</span><span class="sxs-lookup"><span data-stu-id="4675f-124">Rejection implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="4675f-125">CONTRL メッセージに示されている理由により、件名のインターチェンジまたはその関連部分を確認できないこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-125">cannot acknowledge the subject interchange, or the relevant parts of it, for reasons indicated in the CONTRL message;</span></span>  
  
- <span data-ttu-id="4675f-126">件名のインターチェンジの拒否された部分に含まれているビジネス情報に対し、それ以上のアクションを行わないこと。</span><span class="sxs-lookup"><span data-stu-id="4675f-126">and will not take any further action on business information contained in the rejected part of the subject interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4675f-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4675f-127">In This Section</span></span>  
  
-   [<span data-ttu-id="4675f-128">技術確認としての EDIFACT CONTRL メッセージ</span><span class="sxs-lookup"><span data-stu-id="4675f-128">EDIFACT CONTRL Message as Technical Acknowledgment</span></span>](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [<span data-ttu-id="4675f-129">機能確認としての EDIFACT CONTRL メッセージ</span><span class="sxs-lookup"><span data-stu-id="4675f-129">EDIFACT CONTRL Message as Functional Acknowledgment</span></span>](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a><span data-ttu-id="4675f-130">参照</span><span class="sxs-lookup"><span data-stu-id="4675f-130">See Also</span></span>  
 [<span data-ttu-id="4675f-131">EDI 受信確認構造</span><span class="sxs-lookup"><span data-stu-id="4675f-131">EDI Acknowledgment Structure</span></span>](../core/edi-acknowledgment-structure.md)