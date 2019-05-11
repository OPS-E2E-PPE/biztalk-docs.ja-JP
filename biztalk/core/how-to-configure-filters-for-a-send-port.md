---
title: 送信ポートのフィルターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send ports
- configuring, filters
- managing [send ports], configuring
- send ports, configuring
- send ports, filters
- managing [send ports], filters
ms.assetid: ad13ca8e-bb1d-4449-8163-49dd9d5d92f8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea60468bcdc9652ae7c2855d347ff4f355fadcaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386335"
---
# <a name="how-to-configure-filters-for-a-send-port"></a><span data-ttu-id="6199d-102">送信ポートのフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6199d-102">How to Configure Filters for a Send Port</span></span>
<span data-ttu-id="6199d-103">このトピックでは、使用する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールに送信ポートのフィルターを構成します。</span><span class="sxs-lookup"><span data-stu-id="6199d-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure filters for a send port.</span></span> <span data-ttu-id="6199d-104">単純なメッセージングを作成するためのフィルターまたはコンテンツ ベースのルーティング (CBR) アプリケーションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6199d-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="6199d-105">フィルターは、メッセージのプロパティやフィールド、送信ポートにルーティングするメッセージを決定するための条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="6199d-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port.</span></span> <span data-ttu-id="6199d-106">フィルターは、オーケストレーションが送信ポートにルーティングするメッセージをフィルター処理されません。</span><span class="sxs-lookup"><span data-stu-id="6199d-106">A filter does not filter the messages that an orchestration routes to the send port.</span></span>  
  
 <span data-ttu-id="6199d-107">メッセージ プロパティ、演算子、および演算子を使用して、プロパティに対して検証される値から成る 1 つまたは複数のフィルター式を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6199d-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="6199d-108">たとえば、次のような式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6199d-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="6199d-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="6199d-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="6199d-110">このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="6199d-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="6199d-111">さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6199d-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="6199d-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="6199d-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="6199d-113">SMTP です。MyServer を =</span><span class="sxs-lookup"><span data-stu-id="6199d-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="6199d-114">この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="6199d-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6199d-115">別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。</span><span class="sxs-lookup"><span data-stu-id="6199d-115">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="6199d-116">この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。</span><span class="sxs-lookup"><span data-stu-id="6199d-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6199d-117">アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中に、送信ポートのフィルターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6199d-117">The application developer can configure filters for a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6199d-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="6199d-118">Prerequisites</span></span>  
 <span data-ttu-id="6199d-119">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6199d-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="6199d-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6199d-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port"></a><span data-ttu-id="6199d-121">送信ポートのフィルターを構成するには</span><span class="sxs-lookup"><span data-stu-id="6199d-121">To configure filters for a send port</span></span>  
  
1. <span data-ttu-id="6199d-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6199d-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6199d-123">コンソール ツリーで、BizTalk グループと送信ポート フィルターを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6199d-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure send port filters.</span></span>  
  
3. <span data-ttu-id="6199d-124">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="6199d-124">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Filters**.</span></span>  
  
4. <span data-ttu-id="6199d-125">次の表に示すようにフィルターを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="6199d-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="6199d-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6199d-126">Use this</span></span>|<span data-ttu-id="6199d-127">目的</span><span class="sxs-lookup"><span data-stu-id="6199d-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="6199d-128">**削除**</span><span class="sxs-lookup"><span data-stu-id="6199d-128">**Delete**</span></span>|<span data-ttu-id="6199d-129">クリックすると、選択したフィルター式を削除します。</span><span class="sxs-lookup"><span data-stu-id="6199d-129">Click to delete the selected filter expression.</span></span>|  
   |<span data-ttu-id="6199d-130">**[上へ移動]**</span><span class="sxs-lookup"><span data-stu-id="6199d-130">**Move Up**</span></span>|<span data-ttu-id="6199d-131">選択したプロパティのフィルター式のシーケンス内で移行する をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6199d-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="6199d-132">**[下へ移動]**</span><span class="sxs-lookup"><span data-stu-id="6199d-132">**Move Down**</span></span>|<span data-ttu-id="6199d-133">クリックすると、選択したプロパティをフィルター式のシーケンス内で下へ移動します。</span><span class="sxs-lookup"><span data-stu-id="6199d-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="6199d-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6199d-134">**Property**</span></span>|<span data-ttu-id="6199d-135">一覧で、このフィルター式で使用するメッセージ プロパティをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6199d-135">In the list, click a message property to use in this filter expression.</span></span>|  
   |<span data-ttu-id="6199d-136">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="6199d-136">**Operator**</span></span>|<span data-ttu-id="6199d-137">入力するか、式の演算子を選択します。</span><span class="sxs-lookup"><span data-stu-id="6199d-137">Type or select the operator for the expression.</span></span>|  
   |<span data-ttu-id="6199d-138">**[値]**</span><span class="sxs-lookup"><span data-stu-id="6199d-138">**Value**</span></span>|<span data-ttu-id="6199d-139">プロパティの検証に使用する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6199d-139">Type the value to validate against the property.</span></span> <span data-ttu-id="6199d-140">指定できる値の型は、プロパティの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6199d-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="6199d-141">プロパティの値の種類が受け入れられるを表示するには、プロパティにマウスを移動します。</span><span class="sxs-lookup"><span data-stu-id="6199d-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="6199d-142">使用可能な値は次のとおりです。Int。(整数)これは、整数でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6199d-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="6199d-143">文字列:文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="6199d-143">String: A character string.</span></span> <span data-ttu-id="6199d-144">dateTime:日付や時間。NET でサポートされている形式です。</span><span class="sxs-lookup"><span data-stu-id="6199d-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="6199d-145">詳細についてはします。NET でサポートされる時刻の形式は、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6199d-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
   |<span data-ttu-id="6199d-146">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="6199d-146">**Group by**</span></span>|<span data-ttu-id="6199d-147">選択**と**または**または**これと他のフィルター式の間のリレーションシップを示します。</span><span class="sxs-lookup"><span data-stu-id="6199d-147">Select **And** or **Or** to indicate the relationship between this and other filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6199d-148">参照</span><span class="sxs-lookup"><span data-stu-id="6199d-148">See Also</span></span>  
 [<span data-ttu-id="6199d-149">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="6199d-149">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)