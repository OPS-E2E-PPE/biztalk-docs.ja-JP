---
title: "Windows 認証を使用して Oracle データベースへの接続 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b1dd0a6e11a1755bb69782f88f1a5a4b8b0067
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a><span data-ttu-id="12343-102">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="12343-102">Connect to the Oracle Database Using Windows Authentication</span></span>
<span data-ttu-id="12343-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースとの接続を確立するために Windows 認証を使用するアダプターのクライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12343-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle database.</span></span> <span data-ttu-id="12343-104">Windows 認証を使用するアダプターのクライアントを指定する必要があります「/」は、ユーザー名とパスワードの空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="12343-104">To use Windows Authentication, the adapter clients must specify “/” for user name and leave the password blank.</span></span> <span data-ttu-id="12343-105">Windows 認証を使用して Oracle データベースへの接続に関する詳細については、次を参照してください。[アダプター サービスの使用を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)です。</span><span class="sxs-lookup"><span data-stu-id="12343-105">For more information about connecting to the Oracle database using Windows Authentication, see [Connect to Oracle Database in Visual Studio using the Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).</span></span>  
  
 <span data-ttu-id="12343-106">アダプター クライアントを Windows 認証を使用して Oracle データベースへの接続を有効にするには、Oracle データベースを実行しているコンピューターで、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="12343-106">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1.  <span data-ttu-id="12343-107">確認して、`sqlnet.ora`両方のクライアントとサーバーで使用可能なファイルを`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`、次のエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="12343-107">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
    ```  
    SQLNET.AUTHENTICATION_SERVICES= (NTS)  
    ```  
  
2.  <span data-ttu-id="12343-108">SYSDBA として Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="12343-108">Connect to the Oracle database as SYSDBA.</span></span>  
  
3.  <span data-ttu-id="12343-109">Oracle データベース内の外部のユーザーとして Windows ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="12343-109">Create the Windows user as an external user in the Oracle database.</span></span> <span data-ttu-id="12343-110">ユーザー名が大文字である必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="12343-110">Note that the user name must be in upper case.</span></span>  
  
    ```  
    CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME>” IDENTIFIED EXTERNALLY;  
    ```  
  
4.  <span data-ttu-id="12343-111">ユーザーに特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="12343-111">Grant privileges to the user.</span></span>  
  
    ```  
    GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME>”;  
    ```  
  
5.  <span data-ttu-id="12343-112">Oracle データベース アイテムにアクセスする Windows 認証を使用してログインを新しく作成したユーザーを有効にするには、SCOTT スキーマに、ユーザーのスキーマを変更できます。</span><span class="sxs-lookup"><span data-stu-id="12343-112">To enable the newly created user, logging in using Windows Authentication, to access the Oracle database artifacts, you can change the user’s schema to the SCOTT schema.</span></span> <span data-ttu-id="12343-113">次の SQL コマンドを追加するには、ユーザーがログオンしたときに、SCOTT にユーザーの既定のスキーマを変更するログオン スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="12343-113">You can add the following SQL command to the logon script that changes the user’s default schema to SCOTT when the user logs on.</span></span>  
  
    ```  
    alter session set current_schema=SCOTT;  
    ```  
  
6.  <span data-ttu-id="12343-114">SCOTT スキーマにユーザーのスキーマを変更する場合でもまだないことができますを参照しを使用してメタデータを生成中に Oracle データベース アイテムを表示する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="12343-114">Even though you changed the schema of the user to the SCOTT schema, you will still not be able to see the Oracle database artifacts while browsing and generating metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="12343-115">これは、新しく作成したユーザーに SCOTT スキーマに対するアクセス許可があるないためです。</span><span class="sxs-lookup"><span data-stu-id="12343-115">This is because the newly created user does not have permissions for the SCOTT schema.</span></span> <span data-ttu-id="12343-116">新しく作成されたユーザーに SCOTT スキーマの権限を提供することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="12343-116">Make sure you provided permission for the SCOTT schema to the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12343-117">参照</span><span class="sxs-lookup"><span data-stu-id="12343-117">See Also</span></span>  
 <span data-ttu-id="12343-118">[Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="12343-118">[Configure the Oracle Client for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span></span>  
[<span data-ttu-id="12343-119">Oracle データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="12343-119">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)