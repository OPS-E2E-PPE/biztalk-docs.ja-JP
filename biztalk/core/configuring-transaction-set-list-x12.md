---
title: "トランザクション セットの構成一覧 (X12) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b11ea09c7c3156aea18b95d758228e55994901
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-transaction-set-list-x12"></a><span data-ttu-id="cc019-102">トランザクション セットの一覧の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="cc019-102">Configuring Transaction Set List (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cc019-103"> では、EDI インターチェンジの処理中に常に含めるまたは除外する必要のあるトランザクション セットの一覧を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cc019-103"> enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="cc019-104">ここでは、トランザクション セットの一覧を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc019-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc019-105">ここで説明する設定は、HIPAA インターチェンジにも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="cc019-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc019-106">プロパティは無効では、このページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。</span><span class="sxs-lookup"><span data-stu-id="cc019-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc019-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="cc019-107">Prerequisites</span></span>  
 <span data-ttu-id="cc019-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc019-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="cc019-109">トランザクション セットの一覧を構成するには</span><span class="sxs-lookup"><span data-stu-id="cc019-109">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="cc019-110">X12 エンコード アグリーメント」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)です。</span><span class="sxs-lookup"><span data-stu-id="cc019-110">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="cc019-111">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="cc019-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cc019-112">一方向アグリーメント タブの下にある**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**です。</span><span class="sxs-lookup"><span data-stu-id="cc019-112">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="cc019-113">選択**一覧からトランザクション セットのサポート**を常に処理する必要があるトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="cc019-113">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc019-114">通常、特定のトランザクションの種類を持つインターチェンジ (850 など) を受信する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="cc019-114">You would use this option if you typically receive interchanges with specific transaction types, say 850.</span></span> <span data-ttu-id="cc019-115">そのような場合は、そのトランザクションの種類を一覧に追加し、他の種類のトランザクション セットがまったく処理されないようにします。</span><span class="sxs-lookup"><span data-stu-id="cc019-115">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="cc019-116">選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="cc019-116">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc019-117">このオプションは、トランザクションの種類が変化したインターチェンジを受信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="cc019-117">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="cc019-118">この場合、トランザクション セットを取得しない一覧にトランザクションの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc019-118">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="cc019-119">空のセルをクリックして、 **ST01**列しトランザクション セットを除外の対象をサポートする種類のドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc019-119">Click the empty cell in the **ST01** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="cc019-120">削除するトランザクションの種類の一覧からトランザクションの種類の行を選択し、 をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="cc019-120">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="cc019-121">をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cc019-121">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc019-122">参照</span><span class="sxs-lookup"><span data-stu-id="cc019-122">See Also</span></span>  
 [<span data-ttu-id="cc019-123">トランザクション セットの構成設定 (X12)</span><span class="sxs-lookup"><span data-stu-id="cc019-123">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)