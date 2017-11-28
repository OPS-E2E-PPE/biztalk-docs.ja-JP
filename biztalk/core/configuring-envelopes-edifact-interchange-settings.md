---
title: "エンベロープの構成 (EDIFACT インターチェンジの設定) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a><span data-ttu-id="e3d5c-102">エンベロープを構成する (EDIFACT インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="e3d5c-102">Configuring Envelopes (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="e3d5c-103">このセクションでは、送信 EDIFACT メッセージのエンベロープを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-103">This section provides instructions on how to configure the envelope for outgoing EDIFACT messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3d5c-104">オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="e3d5c-105">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="e3d5c-106">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3d5c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="e3d5c-107">Prerequisites</span></span>  
 <span data-ttu-id="e3d5c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-interchange-envelope"></a><span data-ttu-id="e3d5c-109">インターチェンジ エンベロープを構成するには</span><span class="sxs-lookup"><span data-stu-id="e3d5c-109">To configure the interchange envelope</span></span>  
  
1.  <span data-ttu-id="e3d5c-110">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-110">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="e3d5c-111">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e3d5c-112">一方向アグリーメント タブの下にある**インターチェンジの設定**セクションで、**エンベロープ**です。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-112">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="e3d5c-113">**処理優先度コード (UNB8)**、1 つの文字の最小値と、最大で 1 つの文字でアルファベット順の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-113">For **Processing priority code (UNB8)**, enter an alphabetical value with a minimum of one character and a maximum of one character.</span></span> <span data-ttu-id="e3d5c-114">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-114">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="e3d5c-115">**通信アグリーメント (UNB10)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-115">For **Communication agreement (UNB10)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="e3d5c-116">このフィールドは省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="e3d5c-116">This is an optional field</span></span>  
  
5.  <span data-ttu-id="e3d5c-117">選択**テスト インジケータ (UNB11)**によって、インターチェンジが生成されることを示すために[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]テスト データは、します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-117">Select **Test indicator (UNB11)** to indicate that the interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is test data.</span></span>  
  
6.  <span data-ttu-id="e3d5c-118">選択**適用の UNA セグメント (文字列サービス通知)**を送信するインターチェンジの UNA セグメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-118">Select **Apply UNA segment (String service advice)** to generate a UNA segment for the interchange to be sent.</span></span> <span data-ttu-id="e3d5c-119">このオプションがオンの場合、 **UNA6**空にすることはできませんと**UNA6 サフィックス**することはできません**None**です。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-119">If this option is checked, then **UNA6** cannot be empty and **UNA 6 Suffix** cannot be **None**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3d5c-120">指定した**UNA6**と**UNA6 サフィックス**で、**文字セットと区切り記号**ページ」の説明に従って[を構成する文字セットと区切り記号 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="e3d5c-120">You specify **UNA6** and **UNA6 Suffix** in the **Charset and Separators** page as described in [Configuring Charset and Separators (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span></span>  
  
7.  <span data-ttu-id="e3d5c-121">選択**適用の UNG セグメント (機能グループ ヘッダー)**送信メッセージの機能グループ ヘッダーにグループ化セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-121">Select **Apply UNG segments (Functional group header)** to create grouping segments in the functional group header in outgoing messages.</span></span>  
  
8.  <span data-ttu-id="e3d5c-122">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e3d5c-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d5c-123">参照</span><span class="sxs-lookup"><span data-stu-id="e3d5c-123">See Also</span></span>  
 [<span data-ttu-id="e3d5c-124">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e3d5c-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)