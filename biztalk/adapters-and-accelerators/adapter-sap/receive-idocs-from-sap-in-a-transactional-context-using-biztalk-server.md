---
title: BizTalk Server を使用してトランザクション コンテキストでの SAP の Idoc を受信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactional context
- IDOCs, receiving in a transactional context using BizTalk Server
ms.assetid: 6a01bb82-7292-4b70-8ad7-996d389a9365
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58bccbb48603af8bf5a5cc0d12b4c2200e78704
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013365"
---
# <a name="receive-idocs-from-sap-in-a-transactional-context-using-biztalk-server"></a><span data-ttu-id="c6bcc-102">BizTalk Server を使用してトランザクション コンテキストでの SAP の Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-102">Receive IDOCs from SAP in a Transactional Context using BizTalk Server</span></span>
<span data-ttu-id="c6bcc-103">トランザクションのコンテキストで IDOC を受信は、トランザクションのコンテキストで Trfc の受信に似ています。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-103">Receiving IDOC in a transactional context is similar to receiving tRFCs in a transactional context.</span></span> <span data-ttu-id="c6bcc-104">このような場合は、SAP システムから受信した IDOC がの一部として、TID を含む、 *\<TransactionalRfcOperationIdentifier\>* 要素。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-104">In such a case, the IDOC received from the SAP system contains a TID as part of the *\<TransactionalRfcOperationIdentifier\>* element.</span></span> <span data-ttu-id="c6bcc-105">この TID は、アダプターによって、SQL database に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-105">This TID is persisted in a SQL database by the adapter.</span></span> <span data-ttu-id="c6bcc-106">IDOC を送信する SAP システムで、ABAP コードに"COMMIT WORK"ステートメントがある場合は、SAP システムへの応答が送信された後に、TID が SQL データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-106">If the ABAP code in the SAP system that sends the IDOC has a "COMMIT WORK" statement, the TID is deleted from the SQL database after a response is sent back to the SAP system.</span></span>  
  
 <span data-ttu-id="c6bcc-107">IDOC を受信するために必要なオーケストレーションは、IDOC はトランザクションのコンテキストで受信したかどうかに関係なくと似ています。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-107">The orchestration required to receive an IDOC is similar irrespective of whether the IDOC is received in a transactional context or not.</span></span> <span data-ttu-id="c6bcc-108">参照してください[Idoc を SAP から BizTalk Server を使用して受信](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-108">See [Receive IDOCs from SAP by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-idocs-from-sap-using-biztalk-server.md).</span></span> <span data-ttu-id="c6bcc-109">ただし、特定、Idoc がトランザクションのコンテキストで受信したかどうかを確認する追加のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-109">However, you need to perform certain additional tasks to make sure the IDOCs are received in a transactional context.</span></span>  
  
1. <span data-ttu-id="c6bcc-110">デザイン時に、IDOC を受信するため、スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-110">At design time, generate the schema for an IDOC that you want to receive.</span></span>  
  
2. <span data-ttu-id="c6bcc-111">実行時に、バインド プロパティの設定を確認します**TidDatabaseConnectionString**します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-111">At run time, make sure you set the binding property **TidDatabaseConnectionString**.</span></span> <span data-ttu-id="c6bcc-112">このプロパティは、TID を格納する SQL database に接続する接続文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-112">This property takes the connection string to connect to a SQL database to store the TID.</span></span> <span data-ttu-id="c6bcc-113">接続文字列の例は、ようになります。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-113">A sample connection string would look like:</span></span>  
  
   ```  
   Data Source=<myServerAddress>;Initial Catalog=<myDataBase>;User Id=<myUsername>;Password=<myPassword>;  
   ```  
  
    <span data-ttu-id="c6bcc-114">バインディングのプロパティとその設定方法の詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-114">For more information about the binding property and how to set it, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="c6bcc-115">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]しばらくお待ちくださいこの処理には、数分かかることがあります SQL スクリプト、SapAdapter-DbScript-Install.sql、SQL server データベースおよびデータベース オブジェクトを作成する SQL Server の管理者によって実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-115">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard installs a SQL script, SapAdapter-DbScript-Install.sql, which must be run by the SQL Server administrator to create a database and the database objects in SQL Server.</span></span> <span data-ttu-id="c6bcc-116">スクリプトは通常にインストールされて*\<インストール ドライブ\>*: Program FilesMicrosoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-116">The script is typically installed at *\<installation drive\>*:Program FilesMicrosoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
   > 
   >  <span data-ttu-id="c6bcc-117">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Tid を永続化するこれらのオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-117">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses these objects to persist the TIDs.</span></span> <span data-ttu-id="c6bcc-118">そのため、SQL Server 管理者ようにするユーザー名と接続文字列の一部があるストアド プロシージャを実行するための十分な特権を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-118">So, the SQL Server administrator must ensure that the user name provide as part of the connection string has sufficient privileges to execute the stored procedures.</span></span> <span data-ttu-id="c6bcc-119">Windows ユーザーがデータベースにストアド プロシージャを実行するための十分なアクセス許可を持っていれば、Windows 認証のこともできます。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-119">You can also opt for Windows authentication provided the Windows user has sufficient permissions to execute stored procedures in the database.</span></span>  
  
3. <span data-ttu-id="c6bcc-120">アダプターがインストールされているコンピューターで MSDTC を有効にすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-120">Make sure MSDTC is enabled on the computer where the adapter is installed.</span></span> <span data-ttu-id="c6bcc-121">MSDTC を有効にするのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-121">Perform the following steps to enable MSDTC.</span></span>  
  
   1.  <span data-ttu-id="c6bcc-122">コンポーネント サービス MMC スナップインを起動します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-122">Start the Component Services MMC snap-in.</span></span>  
  
   2.  <span data-ttu-id="c6bcc-123">コンポーネント サービス MMC スナップインで、左側のウィンドウから展開**コンポーネント サービス**、展開**コンピューター**、右クリックして**マイ コンピューター**、 をクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-123">In the Component Services MMC snap-in, from the left pane expand **Component Services**, expand **Computers**, right-click **My Computer**, and click **Properties**.</span></span>  
  
   3.  <span data-ttu-id="c6bcc-124">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして、 **MSDTC**タブ。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-124">In the **My Computer Properties** dialog box, click the **MSDTC** tab.</span></span>  
  
   4.  <span data-ttu-id="c6bcc-125">**トランザクション構成**セクションで、、**セキュリティ構成**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-125">In the **Transaction Configuration** section, click the **Security Configuration** button.</span></span>  
  
   5.  <span data-ttu-id="c6bcc-126">**セキュリティ構成**ダイアログ ボックスで、**ネットワーク DTC アクセス**チェック ボックスをオンし、次のように選択します。、**リモート クライアントを許可する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-126">In the **Security Configuration** dialog box, select the **Network DTC Access** check box and within that, select the **Allow Remote Clients** check box.</span></span>  
  
   6.  <span data-ttu-id="c6bcc-127">**トランザクション マネージャー通信**セクションで、**受信を許可する**と**送信を許可する**チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-127">In the **Transaction Manager Communication** section, select the **Allow Inbound** and **Allow Outbound** check boxes.</span></span>  
  
   7.  <span data-ttu-id="c6bcc-128">**セキュリティの構成**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-128">In the **Security Configuration** dialog box, click **OK**.</span></span>  
  
   8.  <span data-ttu-id="c6bcc-129">をクリックして**はい** ダイアログ ボックス通知、MSDTC サービスが再開されることにします。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-129">Click **Yes** in the dialog box informing that the MSDTC service will be restarted.</span></span> <span data-ttu-id="c6bcc-130">MSDTC サービスが再起動されると、クリックして**OK**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-130">After the MSDTC service is restarted, click **OK** on the dialog box.</span></span>  
  
   9. <span data-ttu-id="c6bcc-131">**マイ コンピューター プロパティ**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-131">In the **My Computer Properties** dialog box, click **OK**.</span></span>  
  
4. <span data-ttu-id="c6bcc-132">既に追加されていない場合、MSDTC を Windows ファイアウォール例外一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-132">Add MSDTC to the Windows Firewall exception list, if not already added.</span></span> <span data-ttu-id="c6bcc-133">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-133">Run the following command.</span></span>  
  
   ```  
   netsh firewall set allowedprogram %windir%\system32\msdtc.exe MSDTC enable  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="c6bcc-134">参照</span><span class="sxs-lookup"><span data-stu-id="c6bcc-134">See Also</span></span>  
[<span data-ttu-id="c6bcc-135">BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="c6bcc-135">Develop BizTalk applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)