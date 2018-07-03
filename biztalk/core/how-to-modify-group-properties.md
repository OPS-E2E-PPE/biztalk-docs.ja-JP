---
title: グループのプロパティを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c13fc05cba9add1fe0a5b6abc28b695e9772da
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005123"
---
# <a name="how-to-modify-group-properties"></a><span data-ttu-id="ffa79-102">グループのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="ffa79-102">How to Modify Group Properties</span></span>
<span data-ttu-id="ffa79-103">ここで示す手順を使用すると、BizTalk Server グループのグローバル プロパティを構成して、署名証明書の選択、キャッシュ更新間隔の変更、および BizTalk Server でサイズの大きいメッセージをどのように処理するかという指定を行えます。</span><span class="sxs-lookup"><span data-stu-id="ffa79-103">You can use this procedure to configure global properties for your BizTalk Server group so that you can select a signing certificate, modify the cache refresh interval, and determine how BizTalk Server will handle large messages.</span></span> <span data-ttu-id="ffa79-104">BizTalk Server グループ プロパティの詳細については、次を参照してください。 [BizTalk グループ](../core/biztalk-groups.md)します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-104">For more information about BizTalk Server group properties, see [BizTalk Groups](../core/biztalk-groups.md).</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="ffa79-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ffa79-105">Prerequisites</span></span>  
 <span data-ttu-id="ffa79-106">ここで示す手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffa79-106">To perform this procedure, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  

### <a name="to-configure-biztalk-group-properties"></a><span data-ttu-id="ffa79-107">BizTalk グループのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="ffa79-107">To configure BizTalk group properties</span></span>  

1. <span data-ttu-id="ffa79-108">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="ffa79-109">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を BizTalk グループを展開し、右クリックして**BizTalk グループ**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-109">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, right-click **BizTalk Group**, and then click **Properties**.</span></span>  

3. <span data-ttu-id="ffa79-110">**グループのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ffa79-110">In the **Group Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |             <span data-ttu-id="ffa79-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ffa79-111">Use this</span></span>             |                                                                                                          <span data-ttu-id="ffa79-112">目的</span><span class="sxs-lookup"><span data-stu-id="ffa79-112">To do this</span></span>                                                                                                           |
   |----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |             <span data-ttu-id="ffa79-113">**名前**</span><span class="sxs-lookup"><span data-stu-id="ffa79-113">**Name**</span></span>             | <span data-ttu-id="ffa79-114">グループ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-114">Type the group name.</span></span> <span data-ttu-id="ffa79-115">グループ名の長さは 128 文字以下にしてください。</span><span class="sxs-lookup"><span data-stu-id="ffa79-115">The group name cannot exceed 128 characters in length.</span></span> <span data-ttu-id="ffa79-116">このボックスに名前が横に表示されます、**グループ**サーバー名および BizTalk 管理データベース名と共に、コンソール ツリー ノード。</span><span class="sxs-lookup"><span data-stu-id="ffa79-116">The name in this box appears next to the **Group** node in the console tree, along with the server name and the BizTalk Management database name.</span></span> |
   |            <span data-ttu-id="ffa79-117">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="ffa79-117">**Server**</span></span>            |                                                                      <span data-ttu-id="ffa79-118">BizTalk 管理データベースが物理的に格納されているサーバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-118">Displays the server on which the BizTalk Management database is physically stored.</span></span>                                                                       |
   |           <span data-ttu-id="ffa79-119">**[データベース]**</span><span class="sxs-lookup"><span data-stu-id="ffa79-119">**Database**</span></span>           |                                                            <span data-ttu-id="ffa79-120">このグループのすべての構成設定が格納されている BizTalk 管理データベースを表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-120">Displays the BizTalk Management database on which all configuration settings for this group are stored.</span></span>                                                            |
   |       <span data-ttu-id="ffa79-121">**SSO サーバー名**</span><span class="sxs-lookup"><span data-stu-id="ffa79-121">**SSO Server name**</span></span>        |       <span data-ttu-id="ffa79-122">このコンピューターでアダプター固有の情報の格納、または情報へのアクセスに使用する、エンタープライズ シングル サインオン (SSO) サーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-122">Type the name of the Enterprise Single Sign-On (SSO) server that this computer will use to store and access adapter-specific information.</span></span> <span data-ttu-id="ffa79-123">これは、SSO データベースへの接続に使用する SSO サーバーの名前です。</span><span class="sxs-lookup"><span data-stu-id="ffa79-123">This is the name of the SSO server used to connect to the SSO database.</span></span>       |
   | <span data-ttu-id="ffa79-124">**BizTalk 管理者グループ**</span><span class="sxs-lookup"><span data-stu-id="ffa79-124">**BizTalk Administrator Group**</span></span>  |                                                  <span data-ttu-id="ffa79-125">インストール後に BizTalk Server 環境を管理する権限が与えられている管理者グループ名を表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-125">Displays the name of the administrators group that has rights to manage the BizTalk Server environment after installation.</span></span>                                                   |
   |   <span data-ttu-id="ffa79-126">**BizTalk Operators グループ**</span><span class="sxs-lookup"><span data-stu-id="ffa79-126">**BizTalk Operators Group**</span></span>    |                                <span data-ttu-id="ffa79-127">構成の表示、クエリの実行、コンピューターの保守と基本的なアプリケーションの監視を行う権限を持つ Operators グループの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-127">Displays the name of the operators group that has rights to view configuration, run queries, and perform computer maintenance and basic application monitoring.</span></span>                                |
   | <span data-ttu-id="ffa79-128">**BizTalk Server B2B Operators**</span><span class="sxs-lookup"><span data-stu-id="ffa79-128">**BizTalk Server B2B Operators**</span></span> |                                                                                         <span data-ttu-id="ffa79-129">B2B Operators グループの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffa79-129">Displays the name of the B2B operators group.</span></span>                                                                                         |


4. <span data-ttu-id="ffa79-130">**データベース** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ffa79-130">On the **Databases** tab, do the following:</span></span>  


   |   <span data-ttu-id="ffa79-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ffa79-131">Use this</span></span>    |                                                           <span data-ttu-id="ffa79-132">目的</span><span class="sxs-lookup"><span data-stu-id="ffa79-132">To do this</span></span>                                                            |
   |---------------|---------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="ffa79-133">**データベース**</span><span class="sxs-lookup"><span data-stu-id="ffa79-133">**Databases**</span></span> | <span data-ttu-id="ffa79-134">アプリケーションのすべてのデータベースの名前と、データベースが存在するサーバーの名前を、構成時の指定どおりに表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-134">Displays the names of all databases in the application and the servers on which they reside, as specified during configuration.</span></span> |


5. <span data-ttu-id="ffa79-135">**証明書** タブで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="ffa79-135">On the **Certificate** tab, do the following, and then click **OK**:</span></span>  

   |<span data-ttu-id="ffa79-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ffa79-136">Use this</span></span>|<span data-ttu-id="ffa79-137">目的</span><span class="sxs-lookup"><span data-stu-id="ffa79-137">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="ffa79-138">**共通名**</span><span class="sxs-lookup"><span data-stu-id="ffa79-138">**Common Name**</span></span>|<span data-ttu-id="ffa79-139">選択した証明書の説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-139">Displays a description of the selected certificate.</span></span>|  
   |<span data-ttu-id="ffa79-140">**拇印**</span><span class="sxs-lookup"><span data-stu-id="ffa79-140">**Thumbprint**</span></span>|<span data-ttu-id="ffa79-141">このグループから送信されるメッセージのデジタル署名に使用される秘密キー証明書の拇印を表示します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-141">Displays the thumbprint of the private key certificate that is used to digitally sign outbound messages from this group.</span></span> <span data-ttu-id="ffa79-142">証明書の拇印には、形式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数の数字 (0 ~ 9 の数) または a ~ F の文字があります。</span><span class="sxs-lookup"><span data-stu-id="ffa79-142">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
   |<span data-ttu-id="ffa79-143">**証明書を削除します。**</span><span class="sxs-lookup"><span data-stu-id="ffa79-143">**Remove certificate**</span></span>|<span data-ttu-id="ffa79-144">表示されている証明書を削除する場合にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffa79-144">Click to remove the displayed certificate.</span></span>|  
   |<span data-ttu-id="ffa79-145">**[参照]**</span><span class="sxs-lookup"><span data-stu-id="ffa79-145">**Browse**</span></span>|<span data-ttu-id="ffa79-146">表示するをクリックして、**証明書の選択**ダイアログ ボックスで、グループで使用する現在のユーザーまたは個人用ストアの署名証明を選択します。</span><span class="sxs-lookup"><span data-stu-id="ffa79-146">Click to display the **Select Certificate** dialog box, where you select the signature certificate for the current user or personal store you want to use with the group.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="ffa79-147">参照</span><span class="sxs-lookup"><span data-stu-id="ffa79-147">See Also</span></span>  
 <span data-ttu-id="ffa79-148">[グループの管理](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ffa79-148">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="ffa79-149">[BizTalk グループ](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="ffa79-149">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="ffa79-150">[サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="ffa79-150">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="ffa79-151">[1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="ffa79-151">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 [<span data-ttu-id="ffa79-152">グループからサーバーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="ffa79-152">How to Remove a Server from a Group</span></span>](../core/how-to-remove-a-server-from-a-group.md)