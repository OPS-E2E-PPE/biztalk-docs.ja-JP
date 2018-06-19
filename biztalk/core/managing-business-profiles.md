---
title: ビジネス プロファイルの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.businessprofile
ms.assetid: cf98c5a4-71bb-440b-8172-717ed0eb8373
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 434979376e679f1098557dc5b55f50e599ed21cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263522"
---
# <a name="managing-business-profiles"></a><span data-ttu-id="1ac6c-102">ビジネス プロファイルの管理</span><span class="sxs-lookup"><span data-stu-id="1ac6c-102">Managing Business Profiles</span></span>
<span data-ttu-id="1ac6c-103">ビジネス プロファイルは、組織内の業務部門を表します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-103">A business profile represents the business divisions within of an organization.</span></span> <span data-ttu-id="1ac6c-104">組織には、さまざまな部門できますあると同じように、パーティがさまざまな[ビジネス プロファイル](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-104">Just like an organization can have various divisions, a party can have various [business profiles](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf).</span></span> 
  
<span data-ttu-id="1ac6c-105">ビジネス プロファイルは、組織の事業部門を表します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-105">A business profile represents a business division in an organization.</span></span> <span data-ttu-id="1ac6c-106">組織に複数の部門 (経理、購買、配送など) が含まれるのと同様に、パーティにも組織の事業部門をそれぞれ表すビジネス プロファイルを複数含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-106">Just like an organization can have many divisions (accounting, purchase, shipping, etc.), a party can have many business profiles, each representing a business division in an organization.</span></span> <span data-ttu-id="1ac6c-107">ビジネス プロファイルのプロパティには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-107">Business profile properties contain the following information:</span></span>  
  
-   <span data-ttu-id="1ac6c-108">ビジネス プロファイル名などの一般的な情報</span><span class="sxs-lookup"><span data-stu-id="1ac6c-108">General information such as business profile name</span></span>  
  
-   <span data-ttu-id="1ac6c-109">ビジネス プロファイルに関連付けることができる一意の ID</span><span class="sxs-lookup"><span data-stu-id="1ac6c-109">Unique identities that can be associated with a business profile</span></span>  
  
-   <span data-ttu-id="1ac6c-110">エンコード (X12 および EDIFACT メッセージ) の設定と[プロトコル設定](../core/protocol-settings.md)(AS2) ビジネス プロファイルを送信または別のパーティからメッセージを受信方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-110">Encoding settings (for X12 and EDIFACT messages) and [protocol settings](../core/protocol-settings.md) (AS2) that defines how the business profile can send or receive messages from another party.</span></span>  
  
<span data-ttu-id="1ac6c-111">このトピックでは、作成、表示、編集、またはビジネス プロファイルを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-111">This topic shows you how to create, view, edit, or delete a business profile.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1ac6c-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="1ac6c-112">Prerequisites</span></span>  
 <span data-ttu-id="1ac6c-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="create-a-business-profile"></a><span data-ttu-id="1ac6c-114">ビジネス プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-114">Create a business profile</span></span>  
  
1.  <span data-ttu-id="1ac6c-115">**BizTalk Server 管理コンソール**BizTalk グループを展開し、選択、**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-115">In **BizTalk Server Administration**, expand the BizTalk group, and select **Parties**.</span></span> 
2. <span data-ttu-id="1ac6c-116">**パーティとビジネス プロファイル**] ウィンドウで、パーティを右クリックして選択**新規**、し、[**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-116">In the **Parties and Business Profiles** pane, right-click a party, select **New**, and then select **Business Profile**.</span></span>  
  
3.  <span data-ttu-id="1ac6c-117">**全般** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-117">In the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="1ac6c-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1ac6c-118">Use this</span></span>|<span data-ttu-id="1ac6c-119">目的</span><span class="sxs-lookup"><span data-stu-id="1ac6c-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1ac6c-120">**名前**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-120">**Name**</span></span>|<span data-ttu-id="1ac6c-121">ビジネス プロファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-121">Enter a business profile name.</span></span>|  
    |<span data-ttu-id="1ac6c-122">**Description**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-122">**Description**</span></span>|<span data-ttu-id="1ac6c-123">ビジネス プロファイルの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-123">Enter a description for the business profile.</span></span>|  
    |<span data-ttu-id="1ac6c-124">**追加のプロパティ – 名前/値**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-124">**Additional Properties – Name / Value**</span></span>|<span data-ttu-id="1ac6c-125">パーティに関する任意の情報を格納する、名前と値の組み合わせを入力します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-125">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="1ac6c-126">名前と値の組み合わせは、必要な数だけ追加できます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-126">You can add as many name-value pairs as you want.</span></span> <span data-ttu-id="1ac6c-127">**注:** なんらかの処理の名前と値のペアが、BizTalk Server によって使用されません。 このデータは、情報提供のみを目的のはします。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-127">**Note:**  The name-value pairs are not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>|  
    |<span data-ttu-id="1ac6c-128">**Del**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-128">**Delete**</span></span>|<span data-ttu-id="1ac6c-129">選択すると、選択した名前と値のペアを削除します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-129">Select to delete the selected name-value pair.</span></span>|  
  
4.  <span data-ttu-id="1ac6c-130">必要に応じて、ビジネス プロファイルのビジネス ID を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-130">If required, add business identities for the business profiles.</span></span> <span data-ttu-id="1ac6c-131">**アイデンティティ** タブで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-131">In the **Identities** tab, do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ac6c-132">この段階でビジネス ID を追加するのは、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-132">Adding business identities at this stage is not mandatory.</span></span> <span data-ttu-id="1ac6c-133">ビジネス プロファイルのアグリーメントの一部として後で、ビジネス id を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-133">You can add the business identities later, as part of an agreement for the business profile.</span></span> <span data-ttu-id="1ac6c-134">ビジネスを今すぐ識別の追加を選択した場合は使用中に、このビジネス プロファイルのアグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-134">If you chose to add the business identifies now, they are available while creating an agreement for this business profile.</span></span>  
  
    |<span data-ttu-id="1ac6c-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1ac6c-135">Use this</span></span>|<span data-ttu-id="1ac6c-136">目的</span><span class="sxs-lookup"><span data-stu-id="1ac6c-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="1ac6c-137">**名前**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-137">**Name**</span></span>|<span data-ttu-id="1ac6c-138">空のセルを選択し、ドロップダウン グリッドから、組織に固有のビジネス id を提供する認証機関を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-138">Select the empty cell, and from the drop-down grid, select an authenticating body that provides unique business identities to organizations.</span></span> <span data-ttu-id="1ac6c-139">たとえば、 **D-U-N、S (Dun & Bradstreet)** です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-139">For example, **D-U-N-S (Dun & Bradstreet)**.</span></span> <span data-ttu-id="1ac6c-140">2 つのビジネス パートナーで、相互に合意したビジネス ID を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-140">Two business partners can opt for a mutually agreed business identity.</span></span> <span data-ttu-id="1ac6c-141">そのようなシナリオでは、次のように選択します。**相互定義**(EDIFACT) の場合または **(X12) を相互定義**(X12) 用です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-141">For such scenarios, select **Mutually Defined** (for EDIFACT) or **Mutually Defined (X12)** (for X12).</span></span>|  
    |<span data-ttu-id="1ac6c-142">**Qualifier**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-142">**Qualifier**</span></span>|<span data-ttu-id="1ac6c-143">選択した値に基づく定義済みの値が表示されます**名前**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-143">Displays a predefined value based on the value you selected for **Name**.</span></span>|  
    |<span data-ttu-id="1ac6c-144">**値**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-144">**Value**</span></span>|<span data-ttu-id="1ac6c-145">ビジネス ID の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-145">Enter a value for the business identity.</span></span> <span data-ttu-id="1ac6c-146">ビジネス ID の値を提供するときは、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-146">You must make the following considerations while providing a value for business identities.</span></span><br /><br /> <span data-ttu-id="1ac6c-147">-を所定のパーティに対して同じ id の名前と id 値の組み合わせを使用して 1 つ以上のビジネス プロファイルを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-147">-   For a given party, you can have more than one business profile using the same combination of identity name and identity value.</span></span> <span data-ttu-id="1ac6c-148">たとえばを使用したパーティの 2 つのビジネス プロファイルを持つことができます**名前**として **(X12) を相互定義**と**値**として**THEM**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-148">For example, you can have two business profiles for a party with **Name** as **Mutually Defined (X12)** and **Value** as **THEM**.</span></span><br /><span data-ttu-id="1ac6c-149">-パーティ間で、同じ id の名前と id 値の組み合わせを使用して 2 つのビジネス プロファイルを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-149">-   Across parties, you cannot have two business profiles using the same combination of identity name and identity value.</span></span>|  
    |<span data-ttu-id="1ac6c-150">**[削除]**</span><span class="sxs-lookup"><span data-stu-id="1ac6c-150">**Remove**</span></span>|<span data-ttu-id="1ac6c-151">選択した id の削除を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-151">Select to remove the selected identity.</span></span>|  
  
5.  <span data-ttu-id="1ac6c-152">必要に応じて、X12 でエンコードされたメッセージ、EDIFACT でエンコードされたメッセージ、または AS2 トランスポート プロトコル設定用のプロトコル設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-152">If required, add the protocol settings for X12-encoded messages, EDIFACT-encoded messages, or the protocol settings for AS2 transport.</span></span> <span data-ttu-id="1ac6c-153">参照してください[ビジネス プロファイルのプロパティを構成する](../core/configuring-business-profile-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-153">See [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
6.  <span data-ttu-id="1ac6c-154">選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-154">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="1ac6c-155">どちらの操作では、設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-155">Either action validates the settings.</span></span>  
  
## <a name="view-or-change-a-business-profile"></a><span data-ttu-id="1ac6c-156">表示またはビジネス プロファイルの変更</span><span class="sxs-lookup"><span data-stu-id="1ac6c-156">View or change a business profile</span></span>  
  
1.  <span data-ttu-id="1ac6c-157">**BizTalk Server 管理コンソール****パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-157">In **BizTalk Server Administration**, select **Parties**.</span></span> 

2. <span data-ttu-id="1ac6c-158">**パーティとビジネス プロファイル** ウィンドウで、その下にあるビジネス プロファイルを表示するパーティのノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-158">In the **Parties and Business Profiles** pane, expand a party node to see the business profiles under it.</span></span> <span data-ttu-id="1ac6c-159">クリックして、編集するビジネス プロファイルを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-159">Right-click a business profile you want to edit, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="1ac6c-160">**プロファイル プロパティ** ダイアログ ボックス、またはプロファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-160">In the **Profile Properties** dialog box, view or edit the profile.</span></span> <span data-ttu-id="1ac6c-161">さまざまなページで指定できる値について、**プロファイル プロパティ**ダイアログ ボックスを参照してください[ビジネス プロファイル プロパティを設定する](../core/configuring-business-profile-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-161">For information on the values that can be specified on the different pages in the **Profile Properties** dialog box, see [Configuring Business Profile Properties](../core/configuring-business-profile-properties.md).</span></span>  
  
4.  <span data-ttu-id="1ac6c-162">選択**適用**、プロパティを受け入れるかを選択する**OK**構成設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-162">Select **Apply** to accept the properties, or select **OK** to complete the configuration setting.</span></span> <span data-ttu-id="1ac6c-163">どちらの操作では、設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-163">Either action validates the settings.</span></span>  

## <a name="delete-a-business-profile"></a><span data-ttu-id="1ac6c-164">ビジネス プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-164">Delete a business profile</span></span>  
  
1.  <span data-ttu-id="1ac6c-165">**BizTalk Server 管理コンソール****パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-165">In **BizTalk Server Administration**, select **Parties**.</span></span>  
  
3.  <span data-ttu-id="1ac6c-166">**パーティとビジネス プロファイル** ウィンドウで、その下にあるビジネス プロファイルを表示するパーティのノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-166">In the **Parties and Business Profiles** pane, expand a party node to see the business profiles under it.</span></span>  
  
4.  <span data-ttu-id="1ac6c-167">クリックして、削除するビジネス プロファイルを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-167">Right-click the business profile you want to delete, and then select **Delete**.</span></span> 
  
5.  <span data-ttu-id="1ac6c-168">**ビジネス プロファイル削除の確認**ダイアログ ボックスで、**はい**ビジネス プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="1ac6c-168">In the **Confirm delete business profile** dialog box, select **Yes** to delete the business profile.</span></span>  


## <a name="see-also"></a><span data-ttu-id="1ac6c-169">参照</span><span class="sxs-lookup"><span data-stu-id="1ac6c-169">See Also</span></span>  
 [<span data-ttu-id="1ac6c-170">EDI および AS2 ソリューションの管理</span><span class="sxs-lookup"><span data-stu-id="1ac6c-170">Managing EDI and AS2 Solutions</span></span>](../core/managing-edi-and-as2-solutions.md)