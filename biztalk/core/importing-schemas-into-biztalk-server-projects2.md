---
title: "Visual Studio に JD Edwards EnterpriseOne のスキーマをインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acd61cc8ab63d6859a8e10afb76f93c2f8cb2150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="ba57c-102">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="ba57c-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="ba57c-103">ここでは、JD Edwards EnterpriseOne サーバーのブラウズ、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトへのスキーマのインポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-103">This section discusses browsing a JD Edwards EnterpriseOne server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba57c-104">arglist を設定したことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="ba57c-105">オーケストレーションでスキーマを生成する前に、jdearglist.txt を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-105">You must update jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="ba57c-106">詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-106">For more information, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba57c-107">Jdearglist を変更するたびにそのビジネス オブジェクトのスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="ba57c-108">JD Edwards EnterpriseOne ポートを作成後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトから Microsoft アダプター ウィザードを起動することで JD Edwards EnterpriseOne をブラウズできます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-108">After creating the JD Edwards EnterpriseOne port, you can browse JD Edwards EnterpriseOne by launching the Microsoft Adapter Wizard from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
## <a name="import-schemas-into-visual-studio"></a><span data-ttu-id="ba57c-109">Visual Studio にスキーマをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ba57c-109">Import schemas into Visual Studio</span></span>
  
1.  <span data-ttu-id="ba57c-110">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="ba57c-111">名前を右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをポイントし、**追加**を選択して**生成した項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-111">Right-click the name of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="ba57c-112">をクリックして**追加**を開くには、**アダプターの追加ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-112">Click **Add** to open the **Add Adapter Wizard**.</span></span>  
  
4.  <span data-ttu-id="ba57c-113">**アダプターの選択** ページで、スキーマをインポートするアダプターの名前を選択して (たとえば、 **JDEEnterpriseOne**)。</span><span class="sxs-lookup"><span data-stu-id="ba57c-113">On the **Select Adapter** page, select the name of the adapter for which you want to import schemas (for example, **JDEEnterpriseOne**).</span></span>  
  
5.  <span data-ttu-id="ba57c-114">**SQL Server**ボックスで、SQL server を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-114">In the **SQL Server** box, select a SQL server.</span></span>  
  
6.  <span data-ttu-id="ba57c-115">**データベース**ボックスで、データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-115">In the **Database** box, select a database.</span></span>  
  
     <span data-ttu-id="ba57c-116">既定のデータベースは、SQL サーバーと同じデータベースです。</span><span class="sxs-lookup"><span data-stu-id="ba57c-116">The default database is the same one as your SQL server.</span></span>  
  
7.  <span data-ttu-id="ba57c-117">**ポート**ボックスで SQL サーバーを選択し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-117">In the **Port** box, select a SQL server, and then click **Next**.</span></span>  
  
     <span data-ttu-id="ba57c-118">JD Edwards EnterpriseOne システムがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-118">The JD Edwards EnterpriseOne system displays in the browser.</span></span>  
  
8.  <span data-ttu-id="ba57c-119">以下に示す手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-119">Continue with the next procedure below.</span></span>  
  
 <span data-ttu-id="ba57c-120">アダプターの追加ウィザードに、定義済みのすべてのシステムのツリーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-120">The Add Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="ba57c-121">JD Edwards EnterpriseOne には多くのモジュールがあります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-121">JD Edwards EnterpriseOne has many modules.</span></span> <span data-ttu-id="ba57c-122">モジュールは名前の最初の 3 文字に従ってグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-122">The modules are grouped together according to the first three characters of their name.</span></span>  
  
-   <span data-ttu-id="ba57c-123">階層の最初のレベルはモジュール名のすべての 3 文字プレフィックスのリストです。</span><span class="sxs-lookup"><span data-stu-id="ba57c-123">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
-   <span data-ttu-id="ba57c-124">2 番目のレベルは同じ 3 文字プレフィックスを共有するすべてのモジュールのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-124">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
-   <span data-ttu-id="ba57c-125">最後のレベルはモジュールに属するビジネス関数のリストを示します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-125">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="ba57c-126">サービス アイコンを展開すると、サービスの操作を閲覧できます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-126">When you expand the services icon, you can view its operations.</span></span>  
  
 <span data-ttu-id="ba57c-127">操作を展開すると、入出力引数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-127">Expanding an operation displays the input/output arguments.</span></span> <span data-ttu-id="ba57c-128">入出力引数を展開すると、引数のデータ型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-128">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba57c-129">サーバー オブジェクト定義が変更されると、スキーマを再生成し、そのデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-129">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba57c-130">スキーマの生成後に jdearglist.txt を変更した場合、スキーマを再生成してそのデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba57c-130">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="ba57c-131">Jdearglist.txt の詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-131">For more information on jdearglist.txt, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
## <a name="select-the-schemas"></a><span data-ttu-id="ba57c-132">スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-132">Select the schemas</span></span>  
  
1.  <span data-ttu-id="ba57c-133">**[インポートするサービス**] ページの最上位のノードを展開し、**ビジネス オブジェクト**ノードまたは**ビジネス サービス**ノード。</span><span class="sxs-lookup"><span data-stu-id="ba57c-133">In the **Select Services to Import** page, expand the top level node of the **Business Objects** node or the **Business Services** node.</span></span>  
  
2.  <span data-ttu-id="ba57c-134">インポート、およびをクリックする項目の横にチェック ボックスをオンに**OK**です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-134">Select the check box next to the items that you want to import, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ba57c-135">選択した JD Edwards EnterpriseOne の項目について生成されたスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba57c-135">Schemas generated for the selected JD Edwards EnterpriseOne items are imported into your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba57c-136">AddressBook (N0100041) を使用する場合、フィールド名は**cActionCode**です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="ba57c-137">アクションは XML ファイル自体の一部です。</span><span class="sxs-lookup"><span data-stu-id="ba57c-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="ba57c-138">コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ba57c-138">The codes are:</span></span>  
  
-   <span data-ttu-id="ba57c-139">A は追加 (Add) を表します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-139">A for Add</span></span>  
  
-   <span data-ttu-id="ba57c-140">C は変更 (Change) を表します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-140">C for Change</span></span>  
  
-   <span data-ttu-id="ba57c-141">D は削除 (Delete) を表します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-141">D for Delete</span></span>  
  
-   <span data-ttu-id="ba57c-142">I は問い合わせ (Inquiry) を表します。</span><span class="sxs-lookup"><span data-stu-id="ba57c-142">I for Inquiry</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ba57c-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="ba57c-143">Next step</span></span>
[<span data-ttu-id="ba57c-144">メッセージ コンテキストのプロパティの使用</span><span class="sxs-lookup"><span data-stu-id="ba57c-144">Use Message Context Properties</span></span>](../core/using-message-context-properties1.md)