---
title: 送信ポート グループのフィルターを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 632b9232e87448ddb27d71735b09598b1a9fbc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248594"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="cb89a-102">送信ポート グループ用のフィルターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="cb89a-102">How to Configure Filters for a Send Port Group</span></span>
<span data-ttu-id="cb89a-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、送信ポート グループ用のフィルターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to configure one or more filters for a send port group.</span></span> <span data-ttu-id="cb89a-104">フィルターを使用することにより、シンプルなメッセージング アプリケーションや、コンテンツ ベースのルーティング (CBR) アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cb89a-104">You can use filters to create simple messaging or content-based routing (CBR) applications.</span></span> <span data-ttu-id="cb89a-105">フィルターとは、メッセージのプロパティやフィールドに対する条件を設定することにより、どのメッセージを、どの送信ポート グループにルーティングするかを定義するものです。</span><span class="sxs-lookup"><span data-stu-id="cb89a-105">A filter sets conditions for message properties or fields that determine which messages are routed to the send port group.</span></span> <span data-ttu-id="cb89a-106">オーケストレーションによって送信ポート グループにルーティングされるメッセージについては、フィルターは適用されません。</span><span class="sxs-lookup"><span data-stu-id="cb89a-106">A filter does not filter the messages that an orchestration routes to the send port group.</span></span>  
  
 <span data-ttu-id="cb89a-107">フィルター式は、メッセージのプロパティ、演算子、および (演算子を介してプロパティと比較される) 値で構成されます。複数のフィルター式を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb89a-107">You can create one or more filter expressions, which consist of a message property, an operator, and a value that is validated against the property by using the operator.</span></span>  
  
 <span data-ttu-id="cb89a-108">たとえば、次のような式を作成できます。</span><span class="sxs-lookup"><span data-stu-id="cb89a-108">For example, you might create an expression like the following:</span></span>  
  
 <span data-ttu-id="cb89a-109">MSMQ.MsgID = 1</span><span class="sxs-lookup"><span data-stu-id="cb89a-109">MSMQ.MsgID = 1</span></span>  
  
 <span data-ttu-id="cb89a-110">このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-110">With this filter, the send port group would only subscribe to messages having an MSMQ message ID of 1.</span></span>  
  
 <span data-ttu-id="cb89a-111">さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-111">You can create additional expressions and specify that they have an AND or OR relationship with other expressions, for example:</span></span>  
  
 <span data-ttu-id="cb89a-112">MSMQ.MsgID = 1 OR</span><span class="sxs-lookup"><span data-stu-id="cb89a-112">MSMQ.MsgID = 1 OR</span></span>  
  
 <span data-ttu-id="cb89a-113">SMTP.From = MyServer</span><span class="sxs-lookup"><span data-stu-id="cb89a-113">SMTP.From = MyServer</span></span>  
  
 <span data-ttu-id="cb89a-114">この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-114">In this case, the send port group would subscribe to all messages that have either an MSMQ message ID of 1 or that have been sent from the SMTP server named MyServer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb89a-115">別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポート グループにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストール、起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。</span><span class="sxs-lookup"><span data-stu-id="cb89a-115">If you create a filter for a send port group in one application that uses a property schema in another application, and then import the first application into a new BizTalk group, you will not receive a warning that the schema is missing, and filtering will not function when the application is installed and started.</span></span> <span data-ttu-id="cb89a-116">この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。</span><span class="sxs-lookup"><span data-stu-id="cb89a-116">You can correct the problem by importing the application that contains the schema before you install the application that does not contain the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb89a-117">アプリケーション開発者が開発プロセス中に送信ポート グループ用のフィルターを構成するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-117">The application developer can configure filters for a send port group during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb89a-118">前提条件</span><span class="sxs-lookup"><span data-stu-id="cb89a-118">Prerequisites</span></span>  
 <span data-ttu-id="cb89a-119">このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb89a-119">To perform the procedure in this topic, you must be logged on with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span> <span data-ttu-id="cb89a-120">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb89a-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-filters-for-a-send-port-group"></a><span data-ttu-id="cb89a-121">送信ポート グループのフィルターを構成するには</span><span class="sxs-lookup"><span data-stu-id="cb89a-121">To configure filters for a send port group</span></span>  
  
1.  <span data-ttu-id="cb89a-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="cb89a-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="cb89a-123">コンソール ツリーで、BizTalk グループを展開し、送信ポート グループ フィルターを構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-123">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure a send port group filter.</span></span>  
  
3.  <span data-ttu-id="cb89a-124">をクリックして**送信ポート グループ**、送信ポート グループを右クリックし、をクリックして**プロパティ**、クリックして**フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="cb89a-124">Click **Send Port Groups**, right-click the send port group, click **Properties**, and then click **Filters**.</span></span>  
  
4.  <span data-ttu-id="cb89a-125">次の表に示すようにフィルターを構成し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cb89a-125">Configure filters as described in the following table, and then click **OK**.</span></span>  
  
    |<span data-ttu-id="cb89a-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cb89a-126">Use this</span></span>|<span data-ttu-id="cb89a-127">目的</span><span class="sxs-lookup"><span data-stu-id="cb89a-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cb89a-128">**Del**</span><span class="sxs-lookup"><span data-stu-id="cb89a-128">**Delete**</span></span>|<span data-ttu-id="cb89a-129">選択したフィルター式を削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-129">Click to delete the selected filter expression.</span></span>|  
    |<span data-ttu-id="cb89a-130">**[上へ移動]**</span><span class="sxs-lookup"><span data-stu-id="cb89a-130">**Move Up**</span></span>|<span data-ttu-id="cb89a-131">選択したプロパティを、フィルター式のシーケンス内で前方に移動する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-131">Click to move the selected property ahead in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="cb89a-132">**[下へ移動]**</span><span class="sxs-lookup"><span data-stu-id="cb89a-132">**Move Down**</span></span>|<span data-ttu-id="cb89a-133">選択したプロパティを、フィルター式のシーケンス内で後方に移動する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-133">Click to move the selected property down in the filter expression sequence.</span></span>|  
    |<span data-ttu-id="cb89a-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="cb89a-134">**Property**</span></span>|<span data-ttu-id="cb89a-135">フィルター式に使用するメッセージ プロパティを一覧から選んでクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb89a-135">In the list, click a message property to use in this filter expression.</span></span>|  
    |<span data-ttu-id="cb89a-136">**演算子**</span><span class="sxs-lookup"><span data-stu-id="cb89a-136">**Operator**</span></span>|<span data-ttu-id="cb89a-137">式の演算子を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-137">Type or select the operator for the expression.</span></span>|  
    |<span data-ttu-id="cb89a-138">**値**</span><span class="sxs-lookup"><span data-stu-id="cb89a-138">**Value**</span></span>|<span data-ttu-id="cb89a-139">プロパティに対して検証する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-139">Type the value to validate against the property.</span></span> <span data-ttu-id="cb89a-140">使用できる値の型は、プロパティの種類により異なります。</span><span class="sxs-lookup"><span data-stu-id="cb89a-140">The accepted value type varies according to the type of property.</span></span> <span data-ttu-id="cb89a-141">プロパティにマウス カーソルを合わせると、そのプロパティ値に使用できる型を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cb89a-141">To see what type of value is accepted for a property, hover your mouse over the property.</span></span> <span data-ttu-id="cb89a-142">使用可能な値は次のとおり: Int: (整数) の整数でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="cb89a-142">Acceptable values are as follows: Int: (Integer) This must be a whole number.</span></span> <span data-ttu-id="cb89a-143">接続文字列: 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-143">String: A character string.</span></span> <span data-ttu-id="cb89a-144">dateTime: 日付/時間。NET でサポートされている形式です。</span><span class="sxs-lookup"><span data-stu-id="cb89a-144">dateTime: A date and/or time in .NET-supported format.</span></span> <span data-ttu-id="cb89a-145">.NET でサポートされる時刻形式の詳細については、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb89a-145">For more information about .NET-supported time formats, see "DateTimeFormatInfo Class" in .NET Frameworks Help.</span></span>|  
    |<span data-ttu-id="cb89a-146">**グループ化**</span><span class="sxs-lookup"><span data-stu-id="cb89a-146">**Group by**</span></span>|<span data-ttu-id="cb89a-147">選択**と**または**または**フィルター式の間のリレーションシップを示します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-147">Select **And** or **Or** to indicate the relationship between filter expressions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb89a-148">参照</span><span class="sxs-lookup"><span data-stu-id="cb89a-148">See Also</span></span>  
 [<span data-ttu-id="cb89a-149">作成して、送信ポート グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb89a-149">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)