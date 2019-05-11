---
title: 送信ポート グループのフィルターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c5d54608da91f76337cba13390baf5ded2b27d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341478"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="be6a4-102">送信ポート グループのフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="be6a4-102">How to Configure Filters for a Send Port Group</span></span>
<span data-ttu-id="be6a4-103">このトピックでは、使用する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールに送信ポート グループの 1 つまたは複数のフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure one or more filters for a send port group.</span></span> <span data-ttu-id="be6a4-104">単純なメッセージングを作成するためのフィルターまたはコンテンツ ベースのルーティング (CBR) アプリケーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="be6a4-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="be6a4-105">フィルターは、メッセージのプロパティやフィールド、送信ポート グループにルーティングするメッセージを決定するための条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port group.</span></span> <span data-ttu-id="be6a4-106">フィルターは、オーケストレーションが送信ポート グループにルーティングするメッセージをフィルター処理されません。</span><span class="sxs-lookup"><span data-stu-id="be6a4-106">A filter does not filter the messages that an orchestration routes to the send port group.</span></span>  
  
 <span data-ttu-id="be6a4-107">メッセージ プロパティ、演算子、および演算子を使用して、プロパティに対して検証される値から成る 1 つまたは複数のフィルター式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="be6a4-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="be6a4-108">たとえば、次のような式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be6a4-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="be6a4-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="be6a4-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="be6a4-110">このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="be6a4-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="be6a4-111">さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="be6a4-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="be6a4-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="be6a4-113">SMTP です。MyServer を =</span><span class="sxs-lookup"><span data-stu-id="be6a4-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="be6a4-114">この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="be6a4-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be6a4-115">フィルターは正しく機能をスキーマが存在しない場合は、警告が表示されましていない別のアプリケーションでプロパティ スキーマを使用する 1 つのアプリケーションで、送信ポート グループのフィルターを作成し、新しい BizTalk グループに最初のアプリケーションをインポートすると、ときに、アプリケーションをインストールして開始します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-115">If you create a filter for a send port group in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="be6a4-116">この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。</span><span class="sxs-lookup"><span data-stu-id="be6a4-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be6a4-117">アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中に、送信ポート グループ用のフィルターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="be6a4-117">The application developer can configure filters for a send port group during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be6a4-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="be6a4-118">Prerequisites</span></span>  
 <span data-ttu-id="be6a4-119">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be6a4-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="be6a4-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="be6a4-121">送信ポート グループのフィルターを構成するには</span><span class="sxs-lookup"><span data-stu-id="be6a4-121">To configure filters for a send port group</span></span>  
  
1. <span data-ttu-id="be6a4-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="be6a4-123">コンソール ツリーで、BizTalk グループと、送信ポート グループ フィルターを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure a send port group filter.</span></span>  
  
3. <span data-ttu-id="be6a4-124">クリックして**送信ポート グループ**は、送信ポート グループを右クリックし、**プロパティ**、順にクリックします**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-124">Click **Send Port Groups**, right-click the send port group, click **Properties**, and then click **Filters**.</span></span>  
  
4. <span data-ttu-id="be6a4-125">次の表に示すようにフィルターを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="be6a4-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="be6a4-126">Use this</span></span>|<span data-ttu-id="be6a4-127">目的</span><span class="sxs-lookup"><span data-stu-id="be6a4-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="be6a4-128">**削除**</span><span class="sxs-lookup"><span data-stu-id="be6a4-128">**Delete**</span></span>|<span data-ttu-id="be6a4-129">クリックすると、選択したフィルター式を削除します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-129">Click to delete the selected filter expression.</span></span>|  
   |<span data-ttu-id="be6a4-130">**[上へ移動]**</span><span class="sxs-lookup"><span data-stu-id="be6a4-130">**Move Up**</span></span>|<span data-ttu-id="be6a4-131">選択したプロパティのフィルター式のシーケンス内で移行する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be6a4-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="be6a4-132">**[下へ移動]**</span><span class="sxs-lookup"><span data-stu-id="be6a4-132">**Move Down**</span></span>|<span data-ttu-id="be6a4-133">クリックすると、選択したプロパティをフィルター式のシーケンス内で下へ移動します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="be6a4-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="be6a4-134">**Property**</span></span>|<span data-ttu-id="be6a4-135">一覧で、このフィルター式で使用するメッセージ プロパティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="be6a4-135">In the list, click a message property to use in this filter expression.</span></span>|  
   |<span data-ttu-id="be6a4-136">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="be6a4-136">**Operator**</span></span>|<span data-ttu-id="be6a4-137">入力するか、式の演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-137">Type or select the operator for the expression.</span></span>|  
   |<span data-ttu-id="be6a4-138">**[値]**</span><span class="sxs-lookup"><span data-stu-id="be6a4-138">**Value**</span></span>|<span data-ttu-id="be6a4-139">プロパティの検証に使用する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-139">Type the value to validate against the property.</span></span> <span data-ttu-id="be6a4-140">指定できる値の型は、プロパティの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="be6a4-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="be6a4-141">プロパティの値の種類が受け入れられるを表示するには、プロパティにマウスを移動します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="be6a4-142">使用可能な値は次のとおりです。Int。(整数)これは、整数でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="be6a4-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="be6a4-143">文字列:文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-143">String: A character string.</span></span> <span data-ttu-id="be6a4-144">dateTime:日付や時間。NET でサポートされている形式です。</span><span class="sxs-lookup"><span data-stu-id="be6a4-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="be6a4-145">詳細についてはします。NET でサポートされる時刻の形式は、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be6a4-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
   |<span data-ttu-id="be6a4-146">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="be6a4-146">**Group by**</span></span>|<span data-ttu-id="be6a4-147">選択**と**または**または**フィルター式の間のリレーションシップを示します。</span><span class="sxs-lookup"><span data-stu-id="be6a4-147">Select **And** or **Or** to indicate the relationship between filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be6a4-148">参照</span><span class="sxs-lookup"><span data-stu-id="be6a4-148">See Also</span></span>  
 [<span data-ttu-id="be6a4-149">送信ポート グループの作成および構成</span><span class="sxs-lookup"><span data-stu-id="be6a4-149">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)