---
title: SQL アダプターを使用した Windows 認証を使用して SQL Server への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45c54b2a-e056-496f-9f10-f19b6a3ca1a6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa19a836d4465b96b663dd4abc5f89500b37e338
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973643"
---
# <a name="connect-to-sql-server-using-windows-authentication-with-the-sql-adapter"></a><span data-ttu-id="cc2d4-102">SQL アダプターを使用した Windows 認証を使用して SQL Server に接続します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-102">Connect to SQL Server using Windows Authentication with the SQL adapter</span></span>
<span data-ttu-id="cc2d4-103">[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]アダプター クライアントが SQL Server との接続を確立するために Windows 認証を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-103">The [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] enables adapter clients to use Windows Authentication to establish a connection with SQL Server.</span></span> <span data-ttu-id="cc2d4-104">Windows 認証を使用するには、アダプター クライアントは、空のユーザー名とパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-104">To use Windows Authentication, adapter clients must enter an empty user name and password.</span></span> 

<span data-ttu-id="cc2d4-105">Visual Studio 内で Windows 認証を使用して SQL Server に接続するを参照してください。 [Consume Adapter Service アドインを使用して Visual Studio での SQL Server への接続](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-105">To connect to SQL Server using Windows Authentication within Visual Studio, see [Connect to SQL Server in Visual Studio using the Consume Adapter Service Add-in](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span></span>  
  
 <span data-ttu-id="cc2d4-106">SQL Server への接続に Windows 認証を使用するアダプターのクライアントを有効にするのには、SQL Server を実行しているコンピューター上のユーザーの Windows 認証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-106">To enable adapter clients to use Windows Authentication to connect to SQL Server, enable Windows Authentication for the user on the computer running SQL Server.</span></span>  

> [!TIP]
> <span data-ttu-id="cc2d4-107">場合は、SQL Server では、SQL Server Management Studio がインストールされていない、[ダウンロード SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)、し、インストールします。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-107">If SQL Server Management Studio is not installed on your SQL Server, you can [Download SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms), and install it.</span></span> 
 
## <a name="add-the-user-in-sql-server"></a><span data-ttu-id="cc2d4-108">SQL Server でユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-108">Add the user in SQL Server</span></span>  
  
1.  <span data-ttu-id="cc2d4-109">SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-109">Open SQL Server Management Studio.</span></span> <span data-ttu-id="cc2d4-110">**サーバーへの接続**を選択します**データベース エンジン**、入力、SQL**サーバー名**、し、サーバーに接続する管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-110">In **Connect to Server**, select **Database Engine**, enter your SQL **Server name**, and enter administrator credentials to connect to the server.</span></span>  

    <span data-ttu-id="cc2d4-111">**[接続]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-111">Select **Connect**.</span></span>
  
2.  <span data-ttu-id="cc2d4-112">**オブジェクト エクスプ ローラー**、SQL Server を展開し、**セキュリティ**、右クリック**ログイン**、し、**新しいログイン**します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-112">In **Object Explorer**, expand the SQL Server, expand **Security**, right-click **Logins**, and then select **New Login**.</span></span>  
  
3.  <span data-ttu-id="cc2d4-113">**ログイン名**、Windows ユーザー名を入力、`domain\username`形式。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-113">For the **Login name**, enter the Windows user name in the `domain\username` format.</span></span>  

    > [!NOTE]
    >* <span data-ttu-id="cc2d4-114">を BizTalk でこのアダプターを使用する場合、ログイン名を入力すると、は、ホスト インスタンス アカウントの id です。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-114">When using this adapter with BizTalk, then the login name you enter, is the identity of the host instance account.</span></span>  
    >
    >* <span data-ttu-id="cc2d4-115">を .NET コードでこのアダプターを使用する場合、ログイン名を入力すると、はそのプロセスの id です。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-115">When using this adapter in .NET code, then the login name you enter, is the identity for that process.</span></span>
  
4.  <span data-ttu-id="cc2d4-116">選択**ユーザー マッピング**(左側のウィンドウ)。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-116">Select **User Mapping** (left pane).</span></span> <span data-ttu-id="cc2d4-117">ユーザーに関連付けるデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-117">Select a database to associate with the user.</span></span> <span data-ttu-id="cc2d4-118">一般的な BizTalk ユーザーは、次のデータベースを関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-118">A typical BizTalk user should be associated with the following databases:</span></span> 

* <span data-ttu-id="cc2d4-119">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="cc2d4-119">BizTalkDTADb</span></span>
* <span data-ttu-id="cc2d4-120">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="cc2d4-120">BizTalkMgmtDb</span></span>
* <span data-ttu-id="cc2d4-121">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="cc2d4-121">BizTalkMsgBoxDb</span></span>
* <span data-ttu-id="cc2d4-122">BTAHL7</span><span class="sxs-lookup"><span data-stu-id="cc2d4-122">BTAHL7</span></span>
* <span data-ttu-id="cc2d4-123">SSODB</span><span class="sxs-lookup"><span data-stu-id="cc2d4-123">SSODB</span></span>

5. <span data-ttu-id="cc2d4-124">**データベース ロールのメンバーシップ**ボックスで、 **db_owner**のすべての BizTalk データベース。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-124">In the **Database role membership for** box, select **db_owner** for all the BizTalk databases.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="cc2d4-125">[サーバーと SQL server データベース ロール](https://msdn.microsoft.com/library/bb669065.aspx)の役割に対する良い情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-125">[Server and Database Roles in SQL Server](https://msdn.microsoft.com/library/bb669065.aspx) provides good info on the roles.</span></span> 
  
6. <span data-ttu-id="cc2d4-126">**[OK]** を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-126">Select **OK** to save your changes.</span></span>
  
   <span data-ttu-id="cc2d4-127">ユーザーを接続して SQL Server を使用する認証にユーザーを追加した後、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、空のユーザー名とパスワードを使用してログを記録します。</span><span class="sxs-lookup"><span data-stu-id="cc2d4-127">After you have added the user, the user can connect and authenticate to SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], logging in with a blank username and password.</span></span>  



## <a name="see-also"></a><span data-ttu-id="cc2d4-128">参照</span><span class="sxs-lookup"><span data-stu-id="cc2d4-128">See Also</span></span>  
 [<span data-ttu-id="cc2d4-129">SQL Server への接続を作成する</span><span class="sxs-lookup"><span data-stu-id="cc2d4-129">Create a connection to SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)