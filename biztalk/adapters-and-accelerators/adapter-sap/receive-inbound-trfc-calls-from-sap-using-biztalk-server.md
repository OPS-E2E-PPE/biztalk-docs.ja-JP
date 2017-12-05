---
title: "BizTalk Server を使用して SAP から受信 tRFC の呼び出しを受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tRFC calls, receiving using BizTalk Server
- tRFCs, sample
ms.assetid: 500eedea-3d27-478c-a64c-903a1fa2b02f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 588e135507a2d186d9d8006836f5bdfb2940eb32
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="receive-inbound-trfc-calls-from-sap-using-biztalk-server"></a><span data-ttu-id="17067-102">BizTalk Server を使用して SAP から受信 tRFC の呼び出しを受信します。</span><span class="sxs-lookup"><span data-stu-id="17067-102">Receive Inbound tRFC Calls from SAP using BizTalk Server</span></span>
<span data-ttu-id="17067-103">TRFC サーバーの呼び出しは、トランザクションの RFC サーバー呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="17067-103">A tRFC server call is a transactional RFC server call.</span></span> <span data-ttu-id="17067-104">トランザクションのコンテキストでの RFC の受信に必要なオーケストレーションは、SAP システムから送信されるその他の受信 RFC を受信するオーケストレーションに似ています。</span><span class="sxs-lookup"><span data-stu-id="17067-104">The orchestration required to receive an RFC in a transactional context is similar to the orchestration to receive any other inbound RFC sent from an SAP system.</span></span> <span data-ttu-id="17067-105">ただし、Rfc がトランザクションのコンテキストで受信したかどうかを確認する特定のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17067-105">However, you need to perform certain additional tasks to make sure the RFCs are received in a transactional context.</span></span> <span data-ttu-id="17067-106">SAP システムを使用して、受信の RFC の受信の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[BizTalk Server を使用して、SAP からの受信 RFC 呼び出しの受信](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="17067-106">For more information about receiving an inbound RFC from the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Receive Inbound RFC Calls from SAP by using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="17067-107">方法の詳細については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、SAP システムからの着信 tRFC の呼び出しの受信をサポートを参照してください[SAP で tRFCs に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="17067-107">For more information about how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports receiving inbound tRFC calls from an SAP system, see [Operations on tRFCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-trfcs-in-sap.md).</span></span>  
  
 <span data-ttu-id="17067-108">SAP システムから送信された着信の tRFC の受信は、次の相違点と、着信 RFC の受信と同様です。</span><span class="sxs-lookup"><span data-stu-id="17067-108">Receiving an inbound tRFC sent from an SAP system is similar to receiving an inbound RFC, with the following differences:</span></span>  
  
1.  <span data-ttu-id="17067-109">スキーマの生成中に、デザイン時に必ず選択してから tRFC、 **TRFC**ノード。</span><span class="sxs-lookup"><span data-stu-id="17067-109">At design time, while generating the schema, make sure you select the tRFC from under the **TRFC** node.</span></span>  
  
2.  <span data-ttu-id="17067-110">実行時に、必ずバインディング プロパティを設定してください**TidDatabaseConnectionString**です。</span><span class="sxs-lookup"><span data-stu-id="17067-110">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="17067-111">このプロパティは、TID を格納する SQL データベースに接続する接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="17067-111">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="17067-112">サンプルの接続文字列は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="17067-112">A sample connection string would look like:</span></span>  
  
    ```  
    Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
    ```  
  
     <span data-ttu-id="17067-113">バインディング プロパティとその設定方法の詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="17067-113">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="17067-114">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードをインストールする SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL Server でデータベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17067-114">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="17067-115">インストールされている通常の*\<インストール ドライブ\>: プログラム FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]*です。</span><span class="sxs-lookup"><span data-stu-id="17067-115">The script is typically installed at *\<installation drive\>:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]*.</span></span>  
    >   
    >  <span data-ttu-id="17067-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Tid を永続化するこれらのオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="17067-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="17067-117">そのため、SQL Server の管理者ことを確認、ユーザー名、接続文字列の一部がストアド プロシージャを実行するための十分な特権を持つように指定します。</span><span class="sxs-lookup"><span data-stu-id="17067-117">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="17067-118">Windows ユーザーがデータベースにストアド プロシージャを実行するための十分なアクセス許可を持っていれば、Windows 認証のこともできます。</span><span class="sxs-lookup"><span data-stu-id="17067-118">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3.  <span data-ttu-id="17067-119">アダプターがインストールされているコンピューターで MSDTC を有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17067-119">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="17067-120">MSDTC を有効にするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="17067-120">Perform the following steps to enable MSDTC.</span></span>  
  
    1.  <span data-ttu-id="17067-121">コンポーネント サービス MMC スナップインを起動します。</span><span class="sxs-lookup"><span data-stu-id="17067-121">Start the Component Services MMC snap-in.</span></span>  
  
    2.  <span data-ttu-id="17067-122">コンポーネント サービス MMC スナップインで、左側のウィンドウから、展開**コンポーネント サービス**、展開**コンピューター**を右クリックして**マイ コンピューター**、 をクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="17067-122">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="17067-123">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**タブです。</span><span class="sxs-lookup"><span data-stu-id="17067-123">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
    4.  <span data-ttu-id="17067-124">**トランザクション構成**セクションで、をクリックして、**セキュリティ構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="17067-124">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
    5.  <span data-ttu-id="17067-125">**セキュリティ構成**ダイアログ ボックスで、**ネットワーク DTC アクセス**チェック ボックスをオンし、をクリックして、**リモート クライアントを許可する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="17067-125">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
    6.  <span data-ttu-id="17067-126">**トランザクション マネージャー通信** セクションで、select、**受信を許可する**と**送信を許可する**チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="17067-126">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
    7.  <span data-ttu-id="17067-127">**セキュリティの構成**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="17067-127">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
    8.  <span data-ttu-id="17067-128">をクリックして**はい**ダイアログ ボックスに通知、MSDTC サービスが再開されることにします。</span><span class="sxs-lookup"><span data-stu-id="17067-128">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="17067-129">MSDTC サービスを再起動すると、をクリックして**OK**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="17067-129">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
    9. <span data-ttu-id="17067-130">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="17067-130">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="17067-131">既に追加されていない場合、Windows ファイアウォールの例外一覧に MSDTC を追加します。</span><span class="sxs-lookup"><span data-stu-id="17067-131">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="17067-132">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="17067-132">Run the following command.</span></span>  
  
    ```  
    netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="17067-133">TRFC の受信呼び出しは、「トランザクション」のコンテキスト内の SAP システムから Idoc を受信中に使用されます。</span><span class="sxs-lookup"><span data-stu-id="17067-133">An inbound tRFC call is used while receiving IDOCs from the SAP system in a "transactional" context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17067-134">参照</span><span class="sxs-lookup"><span data-stu-id="17067-134">See Also</span></span>  
[<span data-ttu-id="17067-135">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="17067-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)