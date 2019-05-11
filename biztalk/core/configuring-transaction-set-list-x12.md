---
title: トランザクション セットの構成一覧 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f277318-90e9-4ad3-843a-e6128837fa2b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17e26aac714f05867dab69b6812c109681a47915
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355069"
---
# <a name="configuring-transaction-set-list-x12"></a><span data-ttu-id="58541-102">トランザクション セットの一覧の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="58541-102">Configuring Transaction Set List (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="58541-103">含まれるか、EDI インターチェンジを処理中に除外する必要がありますは常にトランザクション セットの一覧を定義できます。</span><span class="sxs-lookup"><span data-stu-id="58541-103">enables you to define a list of transaction sets that must always be included or excluded while processing an EDI interchange.</span></span> <span data-ttu-id="58541-104">このセクションでは、一覧の設定については、トランザクションを作成する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="58541-104">This section provides instructions on how to create the transaction set list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58541-105">ここで説明する設定は、HIPAA インターチェンジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="58541-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58541-106">プロパティは無効になりませんこのページをオフにした場合でも、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、。契約です。</span><span class="sxs-lookup"><span data-stu-id="58541-106">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58541-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="58541-107">Prerequisites</span></span>  
 <span data-ttu-id="58541-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="58541-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-a-transaction-set-list"></a><span data-ttu-id="58541-109">一覧の設定をトランザクションを構成するには</span><span class="sxs-lookup"><span data-stu-id="58541-109">To configure a transaction set list</span></span>  
  
1.  <span data-ttu-id="58541-110">X12 エンコード アグリーメントを」の説明に従って作成[全般設定を構成する (X12)](../core/configuring-general-settings-x12.md)します。</span><span class="sxs-lookup"><span data-stu-id="58541-110">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="58541-111">既存のアグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="58541-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="58541-112">一方向アグリーメント タブで、**トランザクション セットの設定**セクションで、**トランザクション セットの一覧**します。</span><span class="sxs-lookup"><span data-stu-id="58541-112">On a one-way agreement tab, under **Transaction Set Settings** section, click **Transaction Set List**.</span></span>  
  
3.  <span data-ttu-id="58541-113">選択**一覧からトランザクション セットのサポート**オプションを常に処理する必要があるトランザクション セットの一覧を作成する場合。</span><span class="sxs-lookup"><span data-stu-id="58541-113">Select **Support Transaction Sets from the List** option if you want to create a list of transaction sets that must always be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58541-114">特定のトランザクションの種類、たとえば 850 インターチェンジを受信する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="58541-114">You would use this option if you typically receive interchanges with specific transaction types, say 850.</span></span> <span data-ttu-id="58541-115">その場合は、ことを一覧にトランザクションの種類の他の種類のトランザクション セットが処理されないようにまったくを追加します。</span><span class="sxs-lookup"><span data-stu-id="58541-115">In that case, you add that transaction type to the list so that the transaction sets of other types are not processed at all.</span></span>  
  
4.  <span data-ttu-id="58541-116">選択**一覧からトランザクション セットを除外する**を処理する必要がないトランザクション セットの一覧を作成する場合はオプションです。</span><span class="sxs-lookup"><span data-stu-id="58541-116">Select **Exclude Transaction Sets from the List** option if you want to create a list of transaction sets that must not be processed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58541-117">さまざまなトランザクションの種類でインターチェンジを受信する場合は、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="58541-117">You would use this option if you typically receive interchanges with varied transaction types.</span></span> <span data-ttu-id="58541-118">トランザクションの種類を追加する場合、すべてのトランザクションを受け取りませんリストに設定します。</span><span class="sxs-lookup"><span data-stu-id="58541-118">In that case, you add those transaction type to the list for which you do not get any transaction sets.</span></span>  
  
5.  <span data-ttu-id="58541-119">空のセルをクリックして、 **ST01**列ドロップダウンの選択からトランザクション セットの種類の除外の対象をサポートするとします。</span><span class="sxs-lookup"><span data-stu-id="58541-119">Click the empty cell in the **ST01** column and from the drop-down select the transaction set type you want to support on exclude.</span></span>  
  
6.  <span data-ttu-id="58541-120">トランザクションの種類を一覧から削除するトランザクションの種類の行を選択し、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="58541-120">To delete a transaction type from the list, select the row for the transaction type, and click **Delete**.</span></span>  
  
7.  <span data-ttu-id="58541-121">をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="58541-121">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58541-122">参照</span><span class="sxs-lookup"><span data-stu-id="58541-122">See Also</span></span>  
 [<span data-ttu-id="58541-123">トランザクション セットの設定の構成 (X12)</span><span class="sxs-lookup"><span data-stu-id="58541-123">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)