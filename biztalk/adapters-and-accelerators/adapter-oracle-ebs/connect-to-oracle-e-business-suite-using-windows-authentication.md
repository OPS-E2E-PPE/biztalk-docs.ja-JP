---
title: "Windows 認証を使用して Oracle E-business Suite への接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0937dfd9-4a94-4d65-a42c-3c5019eefde2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fef7c954b1384a31c2185d21b3dc4c529c561c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-e-business-suite-using-windows-authentication"></a><span data-ttu-id="73a99-102">Windows 認証を使用して Oracle E-business Suite への接続します。</span><span class="sxs-lookup"><span data-stu-id="73a99-102">Connect to Oracle E-Business Suite using Windows Authentication</span></span>
<span data-ttu-id="73a99-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite への接続を確立するために Windows 認証を使用するアダプターのクライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73a99-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle E-Business Suite.</span></span> <span data-ttu-id="73a99-104">Windows 認証を使用するには、アダプター クライアント ユーザー名の「/」を指定して、パスワードを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="73a99-104">To use Windows Authentication adapter clients must specify a “/” for user name and leave the password blank.</span></span> <span data-ttu-id="73a99-105">Windows 認証を使用して Oracle E-business Suite への接続に関する詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。</span><span class="sxs-lookup"><span data-stu-id="73a99-105">For more information about connecting to the Oracle E-Business Suite using Windows Authentication, see [Connect to the Oracle E-Business Suite in Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).</span></span>  

## <a name="what-you-need-to-know"></a><span data-ttu-id="73a99-106">おく必要があります。</span><span class="sxs-lookup"><span data-stu-id="73a99-106">What you need to know</span></span>  
 <span data-ttu-id="73a99-107">Windows 認証を使用するのには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="73a99-107">To use Windows Authentication, you must do the following:</span></span>  
  
-   <span data-ttu-id="73a99-108">場合、 **ClientCredentialType**プロパティに設定されている**データベース**、指定「/」のままにして、ユーザー名の Oracle E-business Suite への接続に空白のパスワード。</span><span class="sxs-lookup"><span data-stu-id="73a99-108">If the **ClientCredentialType** property is set to **Database**, specify “/” for the user name and leave the password blank to connect to the Oracle E-Business Suite.</span></span>  
  
-   <span data-ttu-id="73a99-109">場合、 **ClientCredentialType**プロパティに設定されている**EBusiness**、接続する Oracle E-business Suite 資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="73a99-109">If the **ClientCredentialType** property is set to **EBusiness**, specify the Oracle E-Business Suite credentials to connect.</span></span> <span data-ttu-id="73a99-110">また、指定する必要がありますの「/」、 **OracleUserName**バインディング プロパティ、およびのままにして、 **OraclePassword**プロパティは空白をバインドします。</span><span class="sxs-lookup"><span data-stu-id="73a99-110">Also, you must specify “/” for the **OracleUserName** binding property and leave the **OraclePassword** binding property blank.</span></span>  

## <a name="enable-windows-authentication"></a><span data-ttu-id="73a99-111">Windows 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="73a99-111">Enable Windows Authentication</span></span>  
 <span data-ttu-id="73a99-112">アダプター クライアントを Windows 認証を使用して Oracle データベースへの接続を有効にするには、Oracle データベースを実行しているコンピューターで、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="73a99-112">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1.  <span data-ttu-id="73a99-113">確認して、`sqlnet.ora`両方のクライアントとサーバーで使用可能なファイルを`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`、次のエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="73a99-113">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  <span data-ttu-id="73a99-114">SYSDBA として Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="73a99-114">Connect to the Oracle database as SYSDBA.</span></span>  
  
3.  <span data-ttu-id="73a99-115">Oracle データベース内の外部のユーザーとして Windows ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="73a99-115">Create the Windows user as an external user in Oracle database.</span></span> <span data-ttu-id="73a99-116">ユーザー名が大文字である必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="73a99-116">Note that the user name must be in upper case.</span></span>  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  <span data-ttu-id="73a99-117">ユーザーに特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="73a99-117">Grant privileges to the user.</span></span>  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME>”;  
    ```  
  
5.  <span data-ttu-id="73a99-118">Oracle E-business Suite 成果物は、アプリのスキーマで使用できます。</span><span class="sxs-lookup"><span data-stu-id="73a99-118">The Oracle E-Business Suite artifacts are available under the APPS schema.</span></span> <span data-ttu-id="73a99-119">Oracle E-business Suite の成果物にアクセスする Windows 認証を使用してログインを新しく作成したユーザーを有効にするには、アプリケーション スキーマに、ユーザーのスキーマを変更してください。</span><span class="sxs-lookup"><span data-stu-id="73a99-119">To enable the newly created user, logging in using Windows Authentication, to access the Oracle E-Business Suite artifacts, the user’s schema must be changed to the APPS schema.</span></span> <span data-ttu-id="73a99-120">次の SQL コマンドを追加するには、ユーザーがログオンしたときに、アプリにユーザーの既定のスキーマを変更するログオン スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="73a99-120">You can add the following SQL command to the logon script that changes the user’s default schema to APPS when the user logs on.</span></span>  
  
    ```  
    alter session set current_schema=APPS;  
    ```  
  
6.  <span data-ttu-id="73a99-121">アプリのスキーマにユーザーのスキーマを変更する場合でもまだいないことができますを参照しを使用してメタデータを生成中に Oracle E-business Suite の成果物を表示する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="73a99-121">Even though you changed the schema of the user to APPS schema, you will still not be able to see Oracle E-Business Suite artifacts while browsing and generating metadata using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="73a99-122">これは、新しく作成したユーザーがアプリケーション スキーマのアクセス許可を持たないためです。</span><span class="sxs-lookup"><span data-stu-id="73a99-122">This is because the newly created user does not have permissions for the APPS schema.</span></span> <span data-ttu-id="73a99-123">新しく作成されたユーザーのアプリ スキーマの権限を指定することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="73a99-123">Make sure you provided permission for the APPS schema for the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a99-124">参照</span><span class="sxs-lookup"><span data-stu-id="73a99-124">See Also</span></span>  
<span data-ttu-id="73a99-125">[Oracle クライアント E-business Suite アダプターを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="73a99-125">[Configure the Oracle client for the E-Business Suite adapter](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-oracle-client-for-the-e-business-suite-adapter.md) </span></span>  
[<span data-ttu-id="73a99-126">Oracle E-business Suite 接続 URI を作成します。</span><span class="sxs-lookup"><span data-stu-id="73a99-126">Create the Oracle E-Business Suite connection URI</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md)  
 [<span data-ttu-id="73a99-127">Oracle E-business Suite への接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="73a99-127">Create a connection to Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)