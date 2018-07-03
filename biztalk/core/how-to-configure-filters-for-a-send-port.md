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
ms.openlocfilehash: ae9c522f982ca82bf865bcfe6c4b481b0133ec7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988179"
---
# <a name="how-to-configure-filters-for-a-send-port"></a><span data-ttu-id="be9ae-102">送信ポートのフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="be9ae-102">How to Configure Filters for a Send Port</span></span>
<span data-ttu-id="be9ae-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、送信ポートのフィルターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure filters for a send port.</span></span> <span data-ttu-id="be9ae-104">フィルターを使用することにより、シンプルなメッセージング アプリケーションや、コンテンツ ベースのルーティング (CBR) アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="be9ae-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="be9ae-105">フィルターとは、どのメッセージをどの送信ポートにルーティングするかを定義した、メッセージのプロパティやフィールドに対する条件設定です。</span><span class="sxs-lookup"><span data-stu-id="be9ae-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port.</span></span> <span data-ttu-id="be9ae-106">オーケストレーションによって送信ポートにルーティングされるメッセージについては、フィルターでは制御できません。</span><span class="sxs-lookup"><span data-stu-id="be9ae-106">A filter does not filter the messages that an orchestration routes to the send port.</span></span>  
  
 <span data-ttu-id="be9ae-107">フィルター式は、メッセージのプロパティ、演算子、および (演算子を介してプロパティと比較される) 値で構成されます。複数のフィルター式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="be9ae-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="be9ae-108">たとえば、次のような式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="be9ae-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="be9ae-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="be9ae-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="be9ae-110">このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="be9ae-111">さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="be9ae-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="be9ae-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="be9ae-113">SMTP.From = MyServer</span><span class="sxs-lookup"><span data-stu-id="be9ae-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="be9ae-114">この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be9ae-115">別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。</span><span class="sxs-lookup"><span data-stu-id="be9ae-115">If you create a filter for a send port in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="be9ae-116">この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。</span><span class="sxs-lookup"><span data-stu-id="be9ae-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be9ae-117">アプリケーション開発者が開発プロセス中に送信ポート用のフィルターを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-117">The application developer can configure filters for a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be9ae-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="be9ae-118">Prerequisites</span></span>  
 <span data-ttu-id="be9ae-119">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be9ae-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="be9ae-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port"></a><span data-ttu-id="be9ae-121">送信ポートのフィルターを構成するには</span><span class="sxs-lookup"><span data-stu-id="be9ae-121">To configure filters for a send port</span></span>  
  
1. <span data-ttu-id="be9ae-122">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="be9ae-123">コンソール ツリーで、BizTalk グループを展開し、送信ポート フィルターを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure send port filters.</span></span>  
  
3. <span data-ttu-id="be9ae-124">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**フィルター**します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-124">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Filters**.</span></span>  
  
4. <span data-ttu-id="be9ae-125">次の表に示すようにフィルターを構成し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="be9ae-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="be9ae-126">Use this</span></span>|<span data-ttu-id="be9ae-127">目的</span><span class="sxs-lookup"><span data-stu-id="be9ae-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="be9ae-128">**削除**</span><span class="sxs-lookup"><span data-stu-id="be9ae-128">**Delete**</span></span>|<span data-ttu-id="be9ae-129">選択したフィルター式を削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-129">Click to delete the selected filter expression.</span></span>|  
   |<span data-ttu-id="be9ae-130">**[上へ移動]**</span><span class="sxs-lookup"><span data-stu-id="be9ae-130">**Move Up**</span></span>|<span data-ttu-id="be9ae-131">選択したプロパティを、フィルター式のシーケンス内で前方に移動する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="be9ae-132">**[下へ移動]**</span><span class="sxs-lookup"><span data-stu-id="be9ae-132">**Move Down**</span></span>|<span data-ttu-id="be9ae-133">選択したプロパティを、フィルター式のシーケンス内で後方に移動する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
   |<span data-ttu-id="be9ae-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="be9ae-134">**Property**</span></span>|<span data-ttu-id="be9ae-135">フィルター式に使用するメッセージ プロパティを一覧から選んでクリックします。</span><span class="sxs-lookup"><span data-stu-id="be9ae-135">In the list, click a message property to use in this filter expression.</span></span>|  
   |<span data-ttu-id="be9ae-136">**[演算子]**</span><span class="sxs-lookup"><span data-stu-id="be9ae-136">**Operator**</span></span>|<span data-ttu-id="be9ae-137">式の演算子を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-137">Type or select the operator for the expression.</span></span>|  
   |<span data-ttu-id="be9ae-138">**[値]**</span><span class="sxs-lookup"><span data-stu-id="be9ae-138">**Value**</span></span>|<span data-ttu-id="be9ae-139">プロパティに対して検証する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-139">Type the value to validate against the property.</span></span> <span data-ttu-id="be9ae-140">使用できる値の型は、プロパティの種類により異なります。</span><span class="sxs-lookup"><span data-stu-id="be9ae-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="be9ae-141">プロパティにマウス カーソルを合わせると、そのプロパティ値に使用できる型を確認できます。</span><span class="sxs-lookup"><span data-stu-id="be9ae-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="be9ae-142">使用可能な値は次のとおり: Int: (整数) この整数である必要があります。</span><span class="sxs-lookup"><span data-stu-id="be9ae-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="be9ae-143">文字列: 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-143">String: A character string.</span></span> <span data-ttu-id="be9ae-144">dateTime: 日付や時間。NET でサポートされている形式です。</span><span class="sxs-lookup"><span data-stu-id="be9ae-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="be9ae-145">.NET でサポートされる時刻形式の詳細については、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be9ae-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
   |<span data-ttu-id="be9ae-146">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="be9ae-146">**Group by**</span></span>|<span data-ttu-id="be9ae-147">選択**と**または**または**これと他のフィルター式の間のリレーションシップを示します。</span><span class="sxs-lookup"><span data-stu-id="be9ae-147">Select **And** or **Or** to indicate the relationship between this and other filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be9ae-148">参照</span><span class="sxs-lookup"><span data-stu-id="be9ae-148">See Also</span></span>  
 [<span data-ttu-id="be9ae-149">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="be9ae-149">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)