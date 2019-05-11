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
ms.openlocfilehash: 7808b02e5aebcf9f03e06a13ebbbcff8b1f43b0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350126"
---
# <a name="edifact-contrl-acknowledgment"></a><span data-ttu-id="d9393-102">EDIFACT CONTRL 確認</span><span class="sxs-lookup"><span data-stu-id="d9393-102">EDIFACT CONTRL Acknowledgment</span></span>
<span data-ttu-id="d9393-103">CONTRL 受信確認 (ACK) は、EDIFACT でエンコードされたメッセージの技術と機能の両方の受信確認として機能します。</span><span class="sxs-lookup"><span data-stu-id="d9393-103">The CONTRL acknowledgment (ACK) serves as both technical and functional acknowledgment for EDIFACT-encoded messages.</span></span> <span data-ttu-id="d9393-104">技術確認として CONTRL メッセージは、インターチェンジの受信を示します。</span><span class="sxs-lookup"><span data-stu-id="d9393-104">As a technical acknowledgment, the CONTRL message indicates receipt of an interchange.</span></span> <span data-ttu-id="d9393-105">機能確認として CONTRL メッセージの受理または拒否された受信したインターチェンジ、グループ、またはメッセージ、エラーまたはサポートされていない機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d9393-105">As a functional acknowledgment, the CONTRL message indicates acceptance or rejection of the received interchange, group, or message, with a list of errors or unsupported functionality.</span></span>  
  
 <span data-ttu-id="d9393-106">機能確認をとして CONTRL メッセージの全文</span><span class="sxs-lookup"><span data-stu-id="d9393-106">The full CONTRL message serves as the functional ACK.</span></span> <span data-ttu-id="d9393-107">機能確認のセクションでは、技術確認で再利用します。</span><span class="sxs-lookup"><span data-stu-id="d9393-107">Sections of the functional ACK are reused for the technical ACK.</span></span> <span data-ttu-id="d9393-108">送信元パーティまたはグローバル プロパティでは、技術と機能の両方の Ack をパーティのプロパティで選択した、BizTalk Server は 2 つの CONTRL メッセージを生成: 技術 CONTRL 確認と機能 CONTRL 確認</span><span class="sxs-lookup"><span data-stu-id="d9393-108">If you have selected both technical and functional ACKs in the party properties for a sending party or in global properties, BizTalk Server will generate two CONTRL messages: a technical CONTRL ACK and a functional CONTRL ACK.</span></span>  
  
 <span data-ttu-id="d9393-109">CONTRL 確認は、efact _ に準拠している\<バージョン番号\>>_contrl.xsd スキーマ。</span><span class="sxs-lookup"><span data-stu-id="d9393-109">The CONTRL ACK conforms to the EFACT_\<Version number\>_CONTRL.xsd schema.</span></span>  
  
## <a name="technical-acknowledgement"></a><span data-ttu-id="d9393-110">技術確認</span><span class="sxs-lookup"><span data-stu-id="d9393-110">Technical Acknowledgement</span></span>  
 <span data-ttu-id="d9393-111">技術確認を意味するインターチェンジの受信者。</span><span class="sxs-lookup"><span data-stu-id="d9393-111">A technical ACK implies that the recipient of the interchange:</span></span>  
  
-   <span data-ttu-id="d9393-112">対象のインターチェンジが受信します。</span><span class="sxs-lookup"><span data-stu-id="d9393-112">has received the subject interchange;</span></span>  
  
-   <span data-ttu-id="d9393-113">UCI レポート セグメントにコピーされたデータ要素が構文的に正しいことを確認するためにチェックされている件名のインターチェンジの各部を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9393-113">acknowledges the parts of the subject interchange that have been checked in order to ensure that the data elements copied into the reporting UCI segment are syntactically correct;</span></span>  
  
-   <span data-ttu-id="d9393-114">受信確認の送信側または件名のインターチェンジの他の部分の却下を通知する責任を承諾しました</span><span class="sxs-lookup"><span data-stu-id="d9393-114">has accepted responsibility for notifying the sender of acknowledgement or rejection of the other parts of the subject interchange;</span></span>  
  
-   <span data-ttu-id="d9393-115">送信者が通知されますのでことを確認するには妥当な予防措置を実行しています。</span><span class="sxs-lookup"><span data-stu-id="d9393-115">and has taken reasonable precautions in order to ensure that the sender is so notified.</span></span>  
  
## <a name="functional-acknowledgement"></a><span data-ttu-id="d9393-116">機能確認</span><span class="sxs-lookup"><span data-stu-id="d9393-116">Functional Acknowledgement</span></span>  
 <span data-ttu-id="d9393-117">意味する機能確認インターチェンジの受信者。</span><span class="sxs-lookup"><span data-stu-id="d9393-117">A functional ACK implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="d9393-118">受信したインターチェンジの受信確認; の参照のレベル (s)</span><span class="sxs-lookup"><span data-stu-id="d9393-118">has received the referenced levels(s) of the interchange acknowledged;</span></span>  
  
- <span data-ttu-id="d9393-119">さらには、インターチェンジの処理を確認した参照レベルで致命的な構文エラーがないことをチェックしました。</span><span class="sxs-lookup"><span data-stu-id="d9393-119">has checked that there are no fatal syntactic errors in the acknowledged referenced level that prevents further processing of the interchange;</span></span>  
  
- <span data-ttu-id="d9393-120">オンにする (エラーが報告されていない) 場合にセグメントが意味的サービスの確認部分すべてが修正;</span><span class="sxs-lookup"><span data-stu-id="d9393-120">has checked that all acknowledged parts of service segments are semantically correct (if no errors are reported);</span></span>  
  
- <span data-ttu-id="d9393-121">受信確認を送った参照レベル サービス セグメントの要求されたアクションに準拠します。</span><span class="sxs-lookup"><span data-stu-id="d9393-121">will comply with the actions requested in the acknowledged referenced-levels of the service segments;</span></span>  
  
- <span data-ttu-id="d9393-122">構文またはセマンティック エラー、前述のようが後で検出された場合、一部または関連の部分では、CONTRL メッセージの送信を処理できません何らかの理由により、一部がよりも、他の方法で送信者を通知する責任を承諾しました送信された CONTRL メッセージの受信確認を受け取りました</span><span class="sxs-lookup"><span data-stu-id="d9393-122">has accepted responsibility for notifying the sender by other means than sending a CONTRL message if any syntactic or semantic errors as described above, are later detected in the relevant part, or the part cannot be processed for some other reason after the part has been acknowledged in a submitted CONTRL message;</span></span>  
  
- <span data-ttu-id="d9393-123">このようなエラーが検出されると、送信者に通知することを確認するには妥当な予防措置を実行しているとします。</span><span class="sxs-lookup"><span data-stu-id="d9393-123">and has taken reasonable precautions in order to ensure that such errors are detected and that the sender is notified.</span></span>  
  
  <span data-ttu-id="d9393-124">意味する拒否インターチェンジの受信者。</span><span class="sxs-lookup"><span data-stu-id="d9393-124">Rejection implies that the recipient of the interchange:</span></span>  
  
- <span data-ttu-id="d9393-125">対象のインターチェンジ、または CONTRL メッセージに示されている上の理由から、関連する部分を確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9393-125">cannot acknowledge the subject interchange, or the relevant parts of it, for reasons indicated in the CONTRL message;</span></span>  
  
- <span data-ttu-id="d9393-126">件名のインターチェンジの拒否された部分に含まれるビジネス情報に、さらにアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="d9393-126">and will not take any further action on business information contained in the rejected part of the subject interchange.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9393-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d9393-127">In This Section</span></span>  
  
-   [<span data-ttu-id="d9393-128">技術確認としての EDIFACT CONTRL メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9393-128">EDIFACT CONTRL Message as Technical Acknowledgment</span></span>](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [<span data-ttu-id="d9393-129">機能確認としての EDIFACT CONTRL メッセージ</span><span class="sxs-lookup"><span data-stu-id="d9393-129">EDIFACT CONTRL Message as Functional Acknowledgment</span></span>](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a><span data-ttu-id="d9393-130">参照</span><span class="sxs-lookup"><span data-stu-id="d9393-130">See Also</span></span>  
 [<span data-ttu-id="d9393-131">EDI 受信確認構造</span><span class="sxs-lookup"><span data-stu-id="d9393-131">EDI Acknowledgment Structure</span></span>](../core/edi-acknowledgment-structure.md)