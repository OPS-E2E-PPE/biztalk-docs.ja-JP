---
title: "トランザクション セットの構成 (EDIFACT) のリスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f6b4d9a5aae6c8758d3a6d4f46d18f9a820fabd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-transaction-set-list-edifact"></a><span data-ttu-id="d632a-102">トランザクション セットの一覧の構成 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="d632a-102">Configuring Transaction Set List (EDIFACT)</span></span>
[!INCLUDE[prague](../includes/prague-md.md)]<span data-ttu-id="d632a-103"> では、EDI インターチェンジの処理中に常に含めるまたは除外する必要のあるトランザクション セットの一覧を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d632a-103"> enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="d632a-104">ここでは、トランザクション セットの一覧を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d632a-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d632a-105">プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="d632a-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d632a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d632a-106">Prerequisites</span></span>  
 <span data-ttu-id="d632a-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d632a-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="d632a-108">トランザクション セットの一覧を構成するには</span><span class="sxs-lookup"><span data-stu-id="d632a-108">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="d632a-109">EDIFACT」の説明に従ってエンコード アグリーメントを作成する[を構成する一般的な設定 (EDIFACT)](../core/configuring-general-settings-edifact.md)です。</span><span class="sxs-lookup"><span data-stu-id="d632a-109">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="d632a-110">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="d632a-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d632a-111">一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**です。</span><span class="sxs-lookup"><span data-stu-id="d632a-111">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="d632a-112">選択**一覧からトランザクション セットのサポート**を常に処理する必要があるトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="d632a-112">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d632a-113">通常、特定のトランザクションの種類を持つインターチェンジ (APERAK など) を受信する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d632a-113">You would use this option if you typically receive interchanges with specific transaction types, say APERAK.</span></span> <span data-ttu-id="d632a-114">そのような場合は、そのトランザクションの種類を一覧に追加し、他の種類のトランザクション セットがまったく処理されないようにします。</span><span class="sxs-lookup"><span data-stu-id="d632a-114">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="d632a-115">選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="d632a-115">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d632a-116">このオプションは、トランザクションの種類が変化したインターチェンジを受信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d632a-116">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="d632a-117">この場合、トランザクション セットを取得しない一覧にトランザクションの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="d632a-117">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="d632a-118">空のセルをクリックして、 **UNH2.1**列しトランザクション セットを除外の対象をサポートする種類のドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d632a-118">Click the empty cell in the **UNH2.1** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="d632a-119">削除するトランザクションの種類の一覧からトランザクションの種類の行を選択し、 をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="d632a-119">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="d632a-120">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d632a-120">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d632a-121">参照</span><span class="sxs-lookup"><span data-stu-id="d632a-121">See Also</span></span>  
 [<span data-ttu-id="d632a-122">トランザクション セットの構成設定 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="d632a-122">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)