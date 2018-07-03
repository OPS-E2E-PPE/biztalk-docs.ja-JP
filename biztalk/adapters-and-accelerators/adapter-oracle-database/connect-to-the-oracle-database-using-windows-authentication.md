---
title: Windows 認証を使用して Oracle データベースへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73b42a1b-1105-4278-bf8a-62cf0cffb08f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c984a62275c58f50b0c360a5f46040a6022b459
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007755"
---
# <a name="connect-to-the-oracle-database-using-windows-authentication"></a><span data-ttu-id="39a23-102">Windows 認証を使用して Oracle データベースへの接続します。</span><span class="sxs-lookup"><span data-stu-id="39a23-102">Connect to the Oracle Database Using Windows Authentication</span></span>
<span data-ttu-id="39a23-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]により、クライアントは、Oracle データベースとの接続を確立するために Windows 認証を使用するアダプター。</span><span class="sxs-lookup"><span data-stu-id="39a23-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] enables adapter clients to use Windows Authentication to establish a connection with the Oracle database.</span></span> <span data-ttu-id="39a23-104">Windows 認証を使用するアダプターのクライアントを指定する必要があります「/」は、ユーザー名とパスワードが空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="39a23-104">To use Windows Authentication, the adapter clients must specify “/” for user name and leave the password blank.</span></span> <span data-ttu-id="39a23-105">Windows 認証を使用して Oracle データベースへの接続に関する詳細については、次を参照してください。 [Consume Adapter Service を使用して Visual Studio での Oracle データベースへの接続](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="39a23-105">For more information about connecting to the Oracle database using Windows Authentication, see [Connect to Oracle Database in Visual Studio using the Consume Adapter Service](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md).</span></span>  
  
 <span data-ttu-id="39a23-106">Oracle データベースへの接続に Windows 認証を使用するアダプターのクライアントを有効にするには、Oracle データベースを実行するコンピューターで、次のタスクを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="39a23-106">To enable adapter clients to use Windows Authentication to connect to an Oracle database, you must perform the following tasks on the computer running the Oracle database.</span></span>  
  
1. <span data-ttu-id="39a23-107">確認します、`sqlnet.ora`クライアントと、サーバーに、使用可能なファイル`ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`、次のエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="39a23-107">Make sure that the `sqlnet.ora` file on both the client and the server, available under `ORACLE_BASE\ORACLE_HOME\network\admin\sqlnet.ora`, has the following entry:</span></span>  
  
   ```  
   SQLNET.AUTHENTICATION_SERVICES= (NTS)  
   ```  
  
2. <span data-ttu-id="39a23-108">SYSDBA として Oracle データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="39a23-108">Connect to the Oracle database as SYSDBA.</span></span>  
  
3. <span data-ttu-id="39a23-109">Oracle データベースで外部ユーザーとして Windows ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="39a23-109">Create the Windows user as an external user in the Oracle database.</span></span> <span data-ttu-id="39a23-110">ユーザー名が大文字である必要がありますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="39a23-110">Note that the user name must be in upper case.</span></span>  
  
   ```  
   CREATE USER “OPS$<DOMAIN_NAME>\<USER_NAME\>” IDENTIFIED EXTERNALLY;  
   ```  
  
4. <span data-ttu-id="39a23-111">ユーザーに特権を付与します。</span><span class="sxs-lookup"><span data-stu-id="39a23-111">Grant privileges to the user.</span></span>  
  
   ```  
   GRANT CONNECT,RESOURCE TO “OPS$<DOMAIN_NAME>\<USER_NAME\>”;  
   ```  
  
5. <span data-ttu-id="39a23-112">新しく作成したユーザーの Oracle のデータベース成果物へのアクセスに Windows 認証を使用してログインを有効にするには、SCOTT スキーマにユーザーのスキーマを変更できます。</span><span class="sxs-lookup"><span data-stu-id="39a23-112">To enable the newly created user, logging in using Windows Authentication, to access the Oracle database artifacts, you can change the user’s schema to the SCOTT schema.</span></span> <span data-ttu-id="39a23-113">次の SQL コマンドを追加するには、ユーザーがログオンしたときに、SCOTT にユーザーの既定のスキーマを変更するログオン スクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="39a23-113">You can add the following SQL command to the logon script that changes the user’s default schema to SCOTT when the user logs on.</span></span>  
  
   ```  
   alter session set current_schema=SCOTT;  
   ```  
  
6. <span data-ttu-id="39a23-114">SCOTT スキーマに、ユーザーのスキーマを変更する場合でも引き続きいないできなく参照とを使用してメタデータを生成中に Oracle データベースのアイテムを表示する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="39a23-114">Even though you changed the schema of the user to the SCOTT schema, you will still not be able to see the Oracle database artifacts while browsing and generating metadata using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="39a23-115">これは、新しく作成したユーザーに SCOTT スキーマに対するアクセス許可があるないためにです。</span><span class="sxs-lookup"><span data-stu-id="39a23-115">This is because the newly created user does not have permissions for the SCOTT schema.</span></span> <span data-ttu-id="39a23-116">新しく作成したユーザーに SCOTT スキーマに対する権限を提供することを確認します。</span><span class="sxs-lookup"><span data-stu-id="39a23-116">Make sure you provided permission for the SCOTT schema to the newly created user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a23-117">参照</span><span class="sxs-lookup"><span data-stu-id="39a23-117">See Also</span></span>  
 <span data-ttu-id="39a23-118">[Oracle データベース アダプターの Oracle クライアントを構成します。](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="39a23-118">[Configure the Oracle Client for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md) </span></span>  
[<span data-ttu-id="39a23-119">Oracle データベースへの接続の作成</span><span class="sxs-lookup"><span data-stu-id="39a23-119">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)