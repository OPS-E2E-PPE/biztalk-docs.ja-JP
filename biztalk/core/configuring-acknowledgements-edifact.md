---
title: 受信確認 (EDIFACT) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 269acfa79808f133f4332371d98e491fc8a0b2e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991371"
---
# <a name="configuring-acknowledgements-edifact"></a><span data-ttu-id="d5700-102">受信確認の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="d5700-102">Configuring Acknowledgements (EDIFACT)</span></span>
<span data-ttu-id="d5700-103">パートナー アグリーメントでは、どのタイプの確認をパーティに返すかや、どの種類の送信ポートを確認の送信に使用するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d5700-103">In the partner agreement, you can specify what type of acknowledgment to return to a party and what kind of send port to use in sending the acknowledgment.</span></span> <span data-ttu-id="d5700-104">また、確認をバッチ処理するかどうか、どのトランザクション セット参照番号を確認の開始番号にするか、受理されたトランザクション セットに対して SG1/SG4 ループを生成するかどうかも指定します。</span><span class="sxs-lookup"><span data-stu-id="d5700-104">You also specify whether to batch an acknowledgment, what the starting transaction set reference number is for the acknowledgment, and whether SG1/SG4 loops are generated for accepted transaction sets.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5700-105">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="d5700-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="d5700-106">**SG1/SG4 ループ受理されたトランザクション セットを生成する (オフの場合、ループが生成されます UCM.5 が 7 と等しくない場合にのみ)** します。</span><span class="sxs-lookup"><span data-stu-id="d5700-106">**Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span>  
> 
>   <span data-ttu-id="d5700-107">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="d5700-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="d5700-108">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="d5700-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d5700-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="d5700-109">Prerequisites</span></span>  
 <span data-ttu-id="d5700-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5700-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="d5700-111">EDIFACT 確認 (CONTRL) プロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="d5700-111">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="d5700-112">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5700-112">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="d5700-113">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d5700-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d5700-114">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**受信確認**します。</span><span class="sxs-lookup"><span data-stu-id="d5700-114">On a one-way agreement tab, under **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="d5700-115">**EDIFACT ACK (制御) セクション**次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d5700-115">In the **EDIFACT ACK (Control) section**, do the following:</span></span>  
  
    1.  <span data-ttu-id="d5700-116">選択**メッセージの受信 (CONTRL が必要です)** をインターチェンジの送信者に技術確認 (CONTRL) を返します。</span><span class="sxs-lookup"><span data-stu-id="d5700-116">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="d5700-117">場合**メッセージの受信 (CONTRL が必要です)** がオンになっている**メッセージ (CONTRL) メッセージの受信確認をバッチ処理しない**を各受信確認を別々 に送信または受信確認をバッチ処理をオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="d5700-117">If **Receipt of message (CONTRL) expected** is selected, select **Do not batch receipt of message (CONTRL) message** to send each acknowledgment separately, or leave cleared to batch the acknowledgments.</span></span>  
  
    2.  <span data-ttu-id="d5700-118">選択**確認 (CONTRL) が必要です**をインターチェンジの送信者に機能確認 (CONTRL) を返します。</span><span class="sxs-lookup"><span data-stu-id="d5700-118">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="d5700-119">場合**確認 (CONTRL) が必要です**がオンになっている**確認 (CONTRL) をバッチ処理しない**とは別に、各機能確認を送信またはバッチ機能をオフのままにするには受信確認。</span><span class="sxs-lookup"><span data-stu-id="d5700-119">If **Acknowledgement (CONTRL) expected** is selected, select **Do not batch Acknowledgement (CONTRL)** to send each functional acknowledgment separately, or leave cleared to batch the functional acknowledgments.</span></span>  
  
4.  <span data-ttu-id="d5700-120">**トランザクション セットの状態への同意レポート**セクションで、機能 CONTRL 確認、受理されたトランザクション セットの SG1/SG4 のループの生成を強制する選択**SG1/SG4 の生成が受け入れられるをループ処理トランザクション セット (オフの場合、ループが生成されます UCM.5 が 7 と等しくない場合にのみ)** します。</span><span class="sxs-lookup"><span data-stu-id="d5700-120">In the **Transaction set status acceptance reporting** section, to force generation of SG1/SG4 loops in functional CONTRL acknowledgments for accepted transaction sets, select **Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span> <span data-ttu-id="d5700-121">SG1/SG4 のループの詳細については、次を参照してください。[機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)します。</span><span class="sxs-lookup"><span data-stu-id="d5700-121">For more information about SG1/SG4 loops, see [EDIFACT CONTRL Message as Functional Acknowledgment](../core/edifact-contrl-message-as-functional-acknowledgment.md).</span></span>  
  
5.  <span data-ttu-id="d5700-122">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d5700-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5700-123">参照</span><span class="sxs-lookup"><span data-stu-id="d5700-123">See Also</span></span>  
 [<span data-ttu-id="d5700-124">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="d5700-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)