---
title: エンベロープの構成 (EDIFACT インターチェンジの設定) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80957d82a70b0fca8a11ace428f87496b45dcb31
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993595"
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a><span data-ttu-id="9fc37-102">エンベロープを構成する (EDIFACT インターチェンジの設定)</span><span class="sxs-lookup"><span data-stu-id="9fc37-102">Configuring Envelopes (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="9fc37-103">このセクションでは、送信 EDIFACT メッセージのエンベロープを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-103">This section provides instructions on how to configure the envelope for outgoing EDIFACT messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fc37-104">オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。</span><span class="sxs-lookup"><span data-stu-id="9fc37-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="9fc37-105">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="9fc37-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="9fc37-106">たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。</span><span class="sxs-lookup"><span data-stu-id="9fc37-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9fc37-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="9fc37-107">Prerequisites</span></span>  
 <span data-ttu-id="9fc37-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fc37-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-interchange-envelope"></a><span data-ttu-id="9fc37-109">インターチェンジ エンベロープを構成するには</span><span class="sxs-lookup"><span data-stu-id="9fc37-109">To configure the interchange envelope</span></span>  
  
1. <span data-ttu-id="9fc37-110">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-110">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="9fc37-111">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="9fc37-112">一方向アグリーメント タブで、**インターチェンジの設定**セクションで、**エンベロープ**します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-112">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="9fc37-113">**処理優先度コード (UNB8)**、1 つの文字の最小値、1 つの文字のアルファベット順の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-113">For **Processing priority code (UNB8)**, enter an alphabetical value with a minimum of one character and a maximum of one character.</span></span> <span data-ttu-id="9fc37-114">このフィールドの入力は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9fc37-114">This is an optional field.</span></span>  
  
4. <span data-ttu-id="9fc37-115">**通信アグリーメント (UNB10)**、1 つの文字の最小値、最大 35 文字の英数字を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-115">For **Communication agreement (UNB10)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="9fc37-116">このフィールドは省略可能です。 </span><span class="sxs-lookup"><span data-stu-id="9fc37-116">This is an optional field</span></span>  
  
5. <span data-ttu-id="9fc37-117">選択**テスト インジケーター (UNB11)** で、インターチェンジが生成されることを示す[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がテスト データ。</span><span class="sxs-lookup"><span data-stu-id="9fc37-117">Select **Test indicator (UNB11)** to indicate that the interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is test data.</span></span>  
  
6. <span data-ttu-id="9fc37-118">選択**適用の UNA セグメント (文字列サービス通知)** を送信するインターチェンジの UNA セグメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-118">Select **Apply UNA segment (String service advice)** to generate a UNA segment for the interchange to be sent.</span></span> <span data-ttu-id="9fc37-119">このオプションがオンの場合、 **UNA6**空にすることはできませんと**UNA6 サフィックス**することはできません**None**します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-119">If this option is checked, then **UNA6** cannot be empty and **UNA 6 Suffix** cannot be **None**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9fc37-120">指定した**UNA6**と**UNA6 サフィックス**で、**文字セットと区切り記号**」の説明に従ってページ[を構成する文字セットと区切り記号 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="9fc37-120">You specify **UNA6** and **UNA6 Suffix** in the **Charset and Separators** page as described in [Configuring Charset and Separators (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span></span>  
  
7. <span data-ttu-id="9fc37-121">選択**適用の UNG セグメント (機能グループ ヘッダー)** 送信メッセージの機能グループ ヘッダーにグループ化セグメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9fc37-121">Select **Apply UNG segments (Functional group header)** to create grouping segments in the functional group header in outgoing messages.</span></span>  
  
8. <span data-ttu-id="9fc37-122">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9fc37-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc37-123">参照</span><span class="sxs-lookup"><span data-stu-id="9fc37-123">See Also</span></span>  
 [<span data-ttu-id="9fc37-124">インターチェンジの設定の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="9fc37-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)