---
title: "BizTalk Server を使用して、トランザクションのコンテキストでの SAP からの Idoc を受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd886cfb0e8ba175c22b5d55f12a4866a68921e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a><span data-ttu-id="6bc5d-102">BizTalk Server を使用して、トランザクションのコンテキストでの SAP からの Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-102">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>
<span data-ttu-id="6bc5d-103">IDOC を受信して、トランザクションのコンテキストでは、トランザクションのコンテキストで tRFCs の受信に似ています。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-103">Receiving IDOC in a transactional context is similar to receiving tRFCs in a transactional context.</span></span> <span data-ttu-id="6bc5d-104">このような場合は、SAP システムから受信した IDOC が含まれています、TID には一部として、  *\<TransactionalRfcOperationIdentifier >*要素。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-104">In such a case, the IDOC received from the SAP system contains a TID as part of the *\<TransactionalRfcOperationIdentifier>* element.</span></span> <span data-ttu-id="6bc5d-105">この TID はアダプターによって、SQL データベースに永続化されます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-105">This TID is persisted in a SQL database by the adapter.</span></span> <span data-ttu-id="6bc5d-106">IDOC を送信する SAP システム内の ABAP コードに"COMMIT WORK"ステートメントがある場合、TID は、SAP システムへの応答が送信された後、SQL データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-106">If the ABAP code in the SAP system that sends the IDOC has a "COMMIT WORK" statement, the TID is deleted from the SQL database after a response is sent back to the SAP system.</span></span>  
  
 <span data-ttu-id="6bc5d-107">IDOC を受信するために必要なオーケストレーションは、IDOC をトランザクションのコンテキストで受信したかいないかどうかに関係なくと似ています。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-107">The orchestration required to receive an IDOC is similar irrespective of whether the IDOC is received in a transactional context or not.</span></span> <span data-ttu-id="6bc5d-108">参照してください[Idoc を SAP から BizTalk Server を使用して、受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-108">See [Receive IDOCs from SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="6bc5d-109">ただし、トランザクションのコンテキストで、Idoc を受け取るかどうかを確認する特定のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-109">However, you need to perform certain additional tasks to make sure the IDOCs are received in a transactional context.</span></span>  
  
1.  <span data-ttu-id="6bc5d-110">デザイン時に、IDOC を受信するため、スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-110">At design time, generate the schema for an IDOC that you want to receive.</span></span>  
  
2.  <span data-ttu-id="6bc5d-111">実行時に、必ずバインディング プロパティを設定してください**TidDatabaseConnectionString**です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-111">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="6bc5d-112">このプロパティは、TID を格納する SQL データベースに接続する接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-112">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="6bc5d-113">サンプルの接続文字列は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-113">A sample connection string would look like:</span></span>  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     <span data-ttu-id="6bc5d-114">バインディング プロパティとその設定方法の詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-114">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6bc5d-115">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードをインストールする SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL Server でデータベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-115">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="6bc5d-116">インストールされている通常の*\<インストール ドライブ >*: プログラム FilesMicrosoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-116">The script is typically installed at *\<installation drive>*:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
    >   
    >  <span data-ttu-id="6bc5d-117">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Tid を永続化するこれらのオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-117">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="6bc5d-118">そのため、SQL Server の管理者ことを確認、ユーザー名、接続文字列の一部がストアド プロシージャを実行するための十分な特権を持つように指定します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-118">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="6bc5d-119">Windows ユーザーがデータベースにストアド プロシージャを実行するための十分なアクセス許可を持っていれば、Windows 認証のこともできます。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-119">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3.  <span data-ttu-id="6bc5d-120">アダプターがインストールされているコンピューターで MSDTC を有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-120">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="6bc5d-121">MSDTC を有効にするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-121">Perform the following steps to enable MSDTC.</span></span>  
  
    1.  <span data-ttu-id="6bc5d-122">コンポーネント サービス MMC スナップインを起動します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-122">Start the Component Services MMC snap-in.</span></span>  
  
    2.  <span data-ttu-id="6bc5d-123">コンポーネント サービス MMC スナップインで、左側のウィンドウから、展開**コンポーネント サービス**、展開**コンピューター**を右クリックして**マイ コンピューター**、 をクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-123">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="6bc5d-124">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**タブです。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-124">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
    4.  <span data-ttu-id="6bc5d-125">**トランザクション構成**セクションで、をクリックして、**セキュリティ構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-125">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
    5.  <span data-ttu-id="6bc5d-126">**セキュリティ構成**ダイアログ ボックスで、**ネットワーク DTC アクセス**チェック ボックスをオンし、をクリックして、**リモート クライアントを許可する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-126">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
    6.  <span data-ttu-id="6bc5d-127">**トランザクション マネージャー通信** セクションで、select、**受信を許可する**と**送信を許可する**チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-127">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
    7.  <span data-ttu-id="6bc5d-128">**セキュリティの構成**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-128">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
    8.  <span data-ttu-id="6bc5d-129">をクリックして**はい**ダイアログ ボックスに通知、MSDTC サービスが再開されることにします。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-129">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="6bc5d-130">MSDTC サービスを再起動すると、をクリックして**OK**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-130">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
    9. <span data-ttu-id="6bc5d-131">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-131">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="6bc5d-132">既に追加されていない場合、Windows ファイアウォールの例外一覧に MSDTC を追加します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-132">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="6bc5d-133">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-133">Run the following command.</span></span>  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6bc5d-134">参照</span><span class="sxs-lookup"><span data-stu-id="6bc5d-134">See Also</span></span>  
[<span data-ttu-id="6bc5d-135">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="6bc5d-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)