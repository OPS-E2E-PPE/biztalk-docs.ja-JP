---
title: 決定し、アクティビティ イベント ライター ロールを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73bfe8ff-167a-4bf0-ab87-3926290d52d8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc3ff2fcc8ed4397db8d1eb8d5906cebd5c26af1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385258"
---
# <a name="how-to-determine-and-set-event-writer-roles-for-activities"></a><span data-ttu-id="59080-102">アクティビティのイベント ライター ロールを確認および設定する方法</span><span class="sxs-lookup"><span data-stu-id="59080-102">How to Determine and Set Event Writer Roles for Activities</span></span>
<span data-ttu-id="59080-103">BAM は、アクティビティにイベントを書き込むときに、2 つのセキュリティ モードを提供します。</span><span class="sxs-lookup"><span data-stu-id="59080-103">BAM provides two modes of security when writing events on activities.</span></span> <span data-ttu-id="59080-104">個々 のアクティビティのイベントの書き込みアクセス許可を付与することができますか、展開済みのすべてのアクティビティのイベントの書き込みアクセス許可を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="59080-104">You can grant permissions to write events on individual activities or you can grant permissions to write events on all deployed activities.</span></span>  
  
 <span data-ttu-id="59080-105">アクティビティ レベルのセキュリティは、BAM 定義を展開するときに作成されるアクティビティ イベント ライター ロールによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="59080-105">Activity-level security is provided by activity event writer roles that are created when you deploy a BAM definition.</span></span> <span data-ttu-id="59080-106">たとえば、CreditCard という名前のアクティビティの定義を展開する場合、BAM は bam_CreditCard_EventWriter という名前のイベント ライター ロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="59080-106">For example, if you deploy a definition for an activity named CreditCard, BAM creates an event writer role named bam_CreditCard_EventWriter.</span></span> <span data-ttu-id="59080-107">このロールは、アクティビティのイベントの書き込みアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="59080-107">This role has permissions to write events for the activity.</span></span> <span data-ttu-id="59080-108">ユーザー アクティビティのイベントの書き込みアクセス許可を付与するには、ロールにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="59080-108">To grant a user permissions to write events for the activity, you add the user to the role.</span></span>  
  
 <span data-ttu-id="59080-109">または、スーパー ロール BAM_EVENT_WRITER を持つすべてのアクティビティへの書き込みアクセス許可を追加することで、すべてのアクティビティに eve2nts を記述するユーザー権限を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="59080-109">Alternatively, you can grant users rights to write eve2nts to all activities by adding them to the super role BAM_EVENT_WRITER, which has permissions to write to all activities.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="59080-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="59080-110">Prerequisites</span></span>  
 <span data-ttu-id="59080-111">この手順を実行するには、次の操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="59080-111">To perform this procedure, you must have the following:</span></span>  
  
-   <span data-ttu-id="59080-112">アクティビティが展開されている BAMPrimaryImportDb への接続。</span><span class="sxs-lookup"><span data-stu-id="59080-112">A connection to BAMPrimaryImportDb on which the activity is deployed.</span></span>  
  
-   <span data-ttu-id="59080-113">データベースの DBO アクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="59080-113">DBO permissions on the database.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-role"></a><span data-ttu-id="59080-114">イベント ライター ロールにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="59080-114">To add a user to an event writer role</span></span>  
  
1.  <span data-ttu-id="59080-115">クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="59080-115">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="59080-116">**SQL サーバーへの接続**ダイアログ ボックスで、SQL Server と、適切な認証方式を選択し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="59080-116">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="59080-117">**オブジェクト エクスプ ローラー**ペイン展開**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="59080-117">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="59080-118">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="59080-118">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="59080-119">次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="59080-119">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="59080-120">ドメイン名、ユーザー名、およびアクティビティ名のプレース ホルダーを適切な値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="59080-120">Replace the domain name, user name, and activity name placeholders with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'bam_<activity name>_EventWriter', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="59080-121">ロール名の大文字と小文字は区別されます。</span><span class="sxs-lookup"><span data-stu-id="59080-121">Role names are case-sensitive.</span></span> <span data-ttu-id="59080-122">アクティビティ名は大文字でも、アクティビティを展開するときに使用する場合は、一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59080-122">Activity names are also case-sensitive, that is, they must match the case used when deploying the activity.</span></span>  
  
6.  <span data-ttu-id="59080-123">をクリックして、 **Execute**アイコンがツールバーにコマンドを実行する F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="59080-123">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
### <a name="to-add-a-user-to-an-event-writer-super-role"></a><span data-ttu-id="59080-124">イベント ライター スーパー ロールにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="59080-124">To add a user to an event writer super role</span></span>  
  
1.  <span data-ttu-id="59080-125">クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして**Microsoft SQL Server 2008**、順にクリックします**SQL Server Management Studio**します。</span><span class="sxs-lookup"><span data-stu-id="59080-125">Click **Start**, point to **All Programs**, click **Microsoft SQL Server 2008**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="59080-126">**SQL サーバーへの接続**ダイアログ ボックスで、SQL Server と、適切な認証方式を選択し、順にクリックします**Connect**します。</span><span class="sxs-lookup"><span data-stu-id="59080-126">In the **Connect to SQL Server** dialog box, select the SQL Server and the appropriate authentication method, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="59080-127">**オブジェクト エクスプ ローラー**ペイン展開**データベース**、BAM プライマリ インポート データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="59080-127">In the **Object Explorer** pane expand **Databases**, and then select the BAM Primary Import database.</span></span>  
  
4.  <span data-ttu-id="59080-128">をクリックして、**新しいクエリ**ツールバーのアイコン。</span><span class="sxs-lookup"><span data-stu-id="59080-128">Click the **New Query** icon on the toolbar.</span></span>  
  
5.  <span data-ttu-id="59080-129">次のコマンドをコピーし、クエリ ウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="59080-129">Copy the following commands and paste them into the Query Window.</span></span> <span data-ttu-id="59080-130">ユーザー名とドメインの名前を適切な値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="59080-130">Replace the domain name and user name with the appropriate values.</span></span>  
  
    ```  
    EXEC sp_grantlogin '<domain name>\<user name>’  
    EXEC sp_grantdbaccess '<domain name>\<user name>', 'ActivityLogin'  
    EXEC sp_addrolemember 'BAM_EVENT_WRITER', 'SpecialLogin'  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="59080-131">ロールの名前は大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="59080-131">Role names are case sensitive.</span></span> <span data-ttu-id="59080-132">指定されたイベント ライター ロールを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59080-132">You must specify the event writer role as specified.</span></span>  
  
6.  <span data-ttu-id="59080-133">をクリックして、 **Execute**アイコンがツールバーにコマンドを実行する F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="59080-133">Click the **Execute** icon on the toolbar or press F5 to run the commands.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59080-134">参照</span><span class="sxs-lookup"><span data-stu-id="59080-134">See Also</span></span>  
 [<span data-ttu-id="59080-135">BAM セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="59080-135">Managing BAM Security</span></span>](../core/managing-bam-security.md)