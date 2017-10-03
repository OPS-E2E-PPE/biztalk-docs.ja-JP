---
title: "判断し、アクティビティ イベント ライター ロールを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9fa663d395fc36205e137da374f17cb9470521
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a><span data-ttu-id="d34e7-102">アクティビティのイベント ライター ロールを確認および設定する方法</span><span class="sxs-lookup"><span data-stu-id="d34e7-102">How to Determine and Set Event Writer Roles for Activities</span></span>
<span data-ttu-id="d34e7-103">アクティビティにイベントを書き込む場合、BAM は 2 つのセキュリティ モードを提供します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-103">BAM provides two modes of security when writing events on activities.</span></span> <span data-ttu-id="d34e7-104">個別のアクティビティへのイベントの書き込みアクセス許可を与えることも、展開されているすべてのアクティビティへのイベントの書き込みアクセス許可を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-104">You can grant permissions to write events on individual activities or you can grant permissions to write events on all deployed activities.</span></span>  
  
 <span data-ttu-id="d34e7-105">アクティビティ レベルのセキュリティは、BAM 定義を展開するときに作成されるアクティビティ イベント ライター ロールで提供されます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-105">Activity-level security is provided by activity event writer roles that are created when you deploy a BAM definition.</span></span> <span data-ttu-id="d34e7-106">たとえば、CreditCard という名前のアクティビティの定義を展開すると、BAM は、bam_CreditCard_EventWriter という名前のイベント ライター ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-106">For example, if you deploy a definition for an activity named CreditCard, BAM creates an event writer role named bam_CreditCard_EventWriter.</span></span> <span data-ttu-id="d34e7-107">このロールは、アクティビティにイベントを書き込むためのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="d34e7-107">This role has permissions to write events for the activity.</span></span> <span data-ttu-id="d34e7-108">アクティビティにイベントを書き込むためのアクセス許可をユーザーに与えるには、ユーザーをこのロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-108">To grant a user permissions to write events for the activity, you add the user to the role.</span></span>  
  
 <span data-ttu-id="d34e7-109">代わりに、スーパー ロール BAM_EVENT_WRITER にすべてのアクティビティへの書き込みアクセス許可を持つに追加して、すべての活動に eve2nts を書き込み権限をユーザーに付与できます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-109">Alternatively, you can grant users rights to write eve2nts to all activities by adding them to the super role BAM_EVENT_WRITER, which has permissions to write to all activities.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d34e7-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="d34e7-110">Prerequisites</span></span>  
 <span data-ttu-id="d34e7-111">この手順を実行するには、以下の条件が揃っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d34e7-111">To perform this procedure, you must have the following:</span></span>  
  
-   <span data-ttu-id="d34e7-112">アクティビティが展開されている BAMPrimaryImportDb への接続</span><span class="sxs-lookup"><span data-stu-id="d34e7-112">A connection to BAMPrimaryImportDb on which the activity is deployed.</span></span>  
  
-   <span data-ttu-id="d34e7-113">データベースへの DBO アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d34e7-113">DBO permissions on the database.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a><span data-ttu-id="d34e7-114">イベント ライター ロールにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="d34e7-114">To add a user to an event writer role</span></span>  
  
1.  <span data-ttu-id="d34e7-115">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d34e7-115">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d34e7-116">**SQL Server への接続**ダイアログ ボックスでは、SQL Server および適切な認証方法を選択し、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="d34e7-116">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="d34e7-117">**オブジェクト エクスプ ローラー**ペインを展開**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-117">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="d34e7-118">クリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="d34e7-118">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="d34e7-119">次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-119">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="d34e7-120">ドメイン名、ユーザー名、およびアクティビティ名のプレースホルダーを適切な値で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-120">Replace the domain name, user name, and activity name placeholders with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d34e7-121">ロール名の大文字と小文字は区別されます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-121">Role names are case-sensitive.</span></span> <span data-ttu-id="d34e7-122">アクティビティ名も大文字と小文字が区別されます。つまり、アクティビティ名は、アクティビティを展開するときに使用した大文字小文字と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d34e7-122">Activity names are also case-sensitive, that is, they must match the case used when deploying the activity.</span></span>  
  
6.  <span data-ttu-id="d34e7-123">クリックして、 **Execute**アイコン、ツールバーまたはコマンドを実行する場合は F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-123">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a><span data-ttu-id="d34e7-124">イベント ライター スーパー ロールにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="d34e7-124">To add a user to an event writer super role</span></span>  
  
1.  <span data-ttu-id="d34e7-125">をクリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリック**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="d34e7-125">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="d34e7-126">**SQL Server への接続**ダイアログ ボックスでは、SQL Server および適切な認証方法を選択し、をクリックして**接続**です。</span><span class="sxs-lookup"><span data-stu-id="d34e7-126">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="d34e7-127">**オブジェクト エクスプ ローラー**ペインを展開**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-127">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="d34e7-128">クリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="d34e7-128">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="d34e7-129">次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-129">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="d34e7-130">ドメイン名およびユーザー名を適切な値で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d34e7-130">Replace the domain name and user name with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d34e7-131">ロールの名前は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-131">Role names are case sensitive.</span></span> <span data-ttu-id="d34e7-132">イベント ライター ロールは指定されているとおりに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d34e7-132">You must specify the event writer role as specified.</span></span>  
  
6.  <span data-ttu-id="d34e7-133">クリックして、 **Execute**アイコン、ツールバーまたはコマンドを実行する場合は F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d34e7-133">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34e7-134">参照</span><span class="sxs-lookup"><span data-stu-id="d34e7-134">See Also</span></span>  
 [<span data-ttu-id="d34e7-135">BAM セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="d34e7-135">Managing BAM Security</span></span>](../core/managing-bam-security.md)