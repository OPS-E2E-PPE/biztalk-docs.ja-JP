---
title: "識別子 (AS2) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac5f85187a49f3ab5248f12aceba74731ed7e915
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-identifiers-as2"></a><span data-ttu-id="11296-102">識別子の構成 (AS2)</span><span class="sxs-lookup"><span data-stu-id="11296-102">Configuring Identifiers (AS2)</span></span>
<span data-ttu-id="11296-103">パートナー アグリーメントで、送信パーティおよび受信パーティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11296-103">In the partner agreement, you must specify the sender and receiver parties.</span></span> <span data-ttu-id="11296-104">これらの値は、受信メッセージおよび送信メッセージのアグリーメントの解決にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="11296-104">These values are also used for agreement resolution for the inbound or outbound messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11296-105">オフにした場合、このページで、次のプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="11296-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="11296-106">**AS2To** **追加のアグリーメント リゾルバー**セクションです。</span><span class="sxs-lookup"><span data-stu-id="11296-106">**AS2To** under **Additional Agreement Resolvers** section.</span></span>  
>   
>  <span data-ttu-id="11296-107">プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。</span><span class="sxs-lookup"><span data-stu-id="11296-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="11296-108">たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。</span><span class="sxs-lookup"><span data-stu-id="11296-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11296-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="11296-109">Prerequisites</span></span>  
 <span data-ttu-id="11296-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="11296-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-identifier-properties"></a><span data-ttu-id="11296-111">識別子のプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="11296-111">To configure the identifier properties</span></span>  
  
1.  <span data-ttu-id="11296-112">AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。</span><span class="sxs-lookup"><span data-stu-id="11296-112">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="11296-113">既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="11296-113">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="11296-114">一方向アグリーメント タブで、をクリックして**識別子**です。</span><span class="sxs-lookup"><span data-stu-id="11296-114">On a one-way agreement tab, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="11296-115">**AS2-から** ページで、AS2 メッセージを送信する取引先の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11296-115">In the **AS2-From** page, specify the name of the trading partner sending the AS2 message.</span></span>  
  
4.  <span data-ttu-id="11296-116">**AS2-に** ページで、AS2 メッセージを受信する取引先の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11296-116">In the **AS2-To** page, specify the name of the trading partner receiving the AS2 message.</span></span>  
  
5.  <span data-ttu-id="11296-117">下にある、**追加のアグリーメント リゾルバー**  セクションの**AS2To**プロパティ、メッセージを受信する取引先の追加の別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="11296-117">Under the **Additional Agreement Resolvers** section, for the **AS2To** property, enter an additional alias for the partner that receives the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11296-118">このプロパティは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="11296-118">This property is optional.</span></span> <span data-ttu-id="11296-119">このプロパティは下位互換用に使用されます。</span><span class="sxs-lookup"><span data-stu-id="11296-119">This property is available for backward compatibility.</span></span> <span data-ttu-id="11296-120">BizTalk Server 2006 R2 または BizTalk Server 2009 から [!INCLUDE[prague](../includes/prague-md.md)] にパーティ定義を移行した場合、以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパーティ名は、このプロパティの値として含められます。</span><span class="sxs-lookup"><span data-stu-id="11296-120">When a party definition is migrated from BizTalk Server 2006 R2 or BizTalk Server 2009 to [!INCLUDE[prague](../includes/prague-md.md)], the name of the party in the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is included as a value for this property.</span></span> <span data-ttu-id="11296-121">これにより、アグリーメントの解決が実行され、既存のアプリケーションおよび取引先の定義を [!INCLUDE[prague](../includes/prague-md.md)] で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="11296-121">This ensures that the agreement resolution happens and the existing applications and partner definitions can be used with [!INCLUDE[prague](../includes/prague-md.md)].</span></span>  
  
6.  <span data-ttu-id="11296-122">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="11296-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11296-123">参照</span><span class="sxs-lookup"><span data-stu-id="11296-123">See Also</span></span>  
 [<span data-ttu-id="11296-124">AS2 アグリーメント プロパティの構成</span><span class="sxs-lookup"><span data-stu-id="11296-124">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)