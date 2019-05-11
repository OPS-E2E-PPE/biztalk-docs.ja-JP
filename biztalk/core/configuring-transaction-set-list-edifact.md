---
title: トランザクション セットの構成 (EDIFACT) の一覧 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5768fc6dcf0e5569acb1d07db38fedc301fb566b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390624"
---
# <a name="configuring-transaction-set-list-edifact"></a><span data-ttu-id="6fe5d-102">トランザクション セットの一覧の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="6fe5d-102">Configuring Transaction Set List (EDIFACT)</span></span>
<span data-ttu-id="6fe5d-103">BizTalk Server では、含まれているまたは EDI インターチェンジを処理中に除外する必要がありますは常にトランザクション セットの一覧を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-103">BizTalk Server enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="6fe5d-104">このセクションでは、一覧の設定については、トランザクションを作成する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6fe5d-105">プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6fe5d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="6fe5d-106">Prerequisites</span></span>  
 <span data-ttu-id="6fe5d-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="6fe5d-108">一覧の設定をトランザクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="6fe5d-108">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="6fe5d-109">EDIFACT エンコード アグリーメントを」の説明に従って作成[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-109">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="6fe5d-110">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6fe5d-111">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-111">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="6fe5d-112">選択**一覧からトランザクション セットのサポート**オプションを常に処理する必要があるトランザクション セットの一覧を作成する場合。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-112">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fe5d-113">特定のトランザクションの種類、インターチェンジを受信する場合は、このオプションを使用すると、APERAK があるとします。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-113">You would use this option if you typically receive interchanges with specific transaction types, say APERAK.</span></span> <span data-ttu-id="6fe5d-114">その場合は、ことを一覧にトランザクションの種類の他の種類のトランザクション セットが処理されないようにまったくを追加します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-114">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="6fe5d-115">選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-115">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fe5d-116">さまざまなトランザクションの種類でインターチェンジを受信する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-116">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="6fe5d-117">トランザクションの種類を追加する場合、すべてのトランザクションを受け取りませんリストに設定します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-117">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="6fe5d-118">空のセルをクリックして、 **UNH2.1**列ドロップダウンの選択からトランザクション セットの種類の除外の対象をサポートするとします。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-118">Click the empty cell in the **UNH2.1** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="6fe5d-119">トランザクションの種類を一覧から削除するトランザクションの種類の行を選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-119">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="6fe5d-120">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6fe5d-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe5d-121">参照</span><span class="sxs-lookup"><span data-stu-id="6fe5d-121">See Also</span></span>  
 [<span data-ttu-id="6fe5d-122">トランザクション セットの設定を構成する (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="6fe5d-122">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)