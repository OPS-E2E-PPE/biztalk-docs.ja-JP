---
title: (X12) 受信確認の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cd9497c6367ae757206ba91d60575476fbfd05e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356319"
---
# <a name="configuring-acknowledgements-x12"></a><span data-ttu-id="944a8-102">受信確認の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="944a8-102">Configuring Acknowledgements (X12)</span></span>
<span data-ttu-id="944a8-103">パートナー アグリーメントで、パートナーから受信した X12 エンコード インターチェンジへの応答として、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で確認を生成する方法、およびパーティーに返す確認の種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="944a8-103">In the partner agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="944a8-104">また、確認をバッチ処理するかどうかと、受理されたトランザクション セットに AK2 ループを生成するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="944a8-104">You can also specify whether to batch an acknowledgement and whether AK2 loops are generated for accepted transaction sets.</span></span> <span data-ttu-id="944a8-105">このセクションでは、これらの操作の実行手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="944a8-105">This section provides instructions on how to do so.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="944a8-106">ここで説明する受信確認プロパティは、HIPAA の受信確認にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="944a8-106">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="944a8-107">オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="944a8-107">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="944a8-108">**受理されたトランザクション セットの AK2 ループを含める (オフの場合、ループが生成されます AK501 が A と等しくない場合にのみ)** します。</span><span class="sxs-lookup"><span data-stu-id="944a8-108">**Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span>  
> 
>   <span data-ttu-id="944a8-109">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="944a8-109">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="944a8-110">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="944a8-110">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="944a8-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="944a8-111">Prerequisites</span></span>  
 <span data-ttu-id="944a8-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="944a8-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="944a8-113">X12 確認のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="944a8-113">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="944a8-114">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="944a8-114">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="944a8-115">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="944a8-115">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="944a8-116">一方向アグリーメント タブで、[**インターチェンジの設定**、] をクリックして**受信確認**します。</span><span class="sxs-lookup"><span data-stu-id="944a8-116">On a one-way agreement tab, under **Interchange Settings**, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="944a8-117">選択**TA1 が必要**をインターチェンジの送信者に技術 (TA1) 確認を返します。</span><span class="sxs-lookup"><span data-stu-id="944a8-117">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="944a8-118">選択した場合、選択**TA1 をバッチ処理しない**とは別に、各技術確認を送信したり、チェック ボックスを技術確認をバッチ処理をオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="944a8-118">If selected, select **Do not batch TA1** to send each technical acknowledgment separately, or leave the check box cleared to batch the technical acknowledgments.</span></span>  
  
4.  <span data-ttu-id="944a8-119">選択**997 が必要**機能 (997) 確認をインターチェンジの送信者に戻ります。</span><span class="sxs-lookup"><span data-stu-id="944a8-119">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="944a8-120">選択した場合、選択**997 をバッチ処理しない**とは別に、各機能確認を送信したり、チェック ボックスを機能確認をバッチ処理をオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="944a8-120">If selected, select **Do not batch 997** to send each functional acknowledgment separately, or leave the check box cleared to batch the functional acknowledgments.</span></span>  
  
5.  <span data-ttu-id="944a8-121">受理されたトランザクション セットの 997 確認で AK2 ループの生成を有効にするのには、選択**受理されたトランザクション セットに含める AK2 ループ (オフの場合、ループが生成されます AK501 が A と等しくない場合にのみ)** します。</span><span class="sxs-lookup"><span data-stu-id="944a8-121">To enable generation of AK2 loops in 997 acknowledgments for accepted transaction sets, select **Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span> <span data-ttu-id="944a8-122">AK2 ループの詳細については、次を参照してください。 [X12 997 受信確認](../core/x12-997-acknowledgment.md)します。</span><span class="sxs-lookup"><span data-stu-id="944a8-122">For more information about AK2 loops, see [X12 997 Acknowledgment](../core/x12-997-acknowledgment.md).</span></span>  
  
6.  <span data-ttu-id="944a8-123">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="944a8-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944a8-124">参照</span><span class="sxs-lookup"><span data-stu-id="944a8-124">See Also</span></span>  
 [<span data-ttu-id="944a8-125">インターチェンジの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="944a8-125">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)