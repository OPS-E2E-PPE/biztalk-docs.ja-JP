---
title: バックアップおよび SQL Server ログインを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 847c3a3d-0d97-415b-893e-4ba173085bae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54fa6a51a27f82add8a96c613e36f5ed7ce88e87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248554"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a><span data-ttu-id="3c0df-102">SQL Server ログインのバックアップ方法と復元方法</span><span class="sxs-lookup"><span data-stu-id="3c0df-102">How to Back Up and Restore SQL Server Logins</span></span>
<span data-ttu-id="3c0df-103">バックアップを作成し、BizTalk Server に関連付けられている SQL Server ログインを復元します。</span><span class="sxs-lookup"><span data-stu-id="3c0df-103">Back up and restore SQL Server logins associated with BizTalk Server.</span></span>  
  
## <a name="biztalk-server-sql-server-security-logins"></a><span data-ttu-id="3c0df-104">BizTalk Server SQL Server セキュリティ ログイン</span><span class="sxs-lookup"><span data-stu-id="3c0df-104">BizTalk Server SQL Server Security Logins</span></span>  
 <span data-ttu-id="3c0df-105">下記の SQL Server セキュリティ ログインは BizTalk Server と関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="3c0df-105">The SQL Server security logins listed below are associated with BizTalk Server.</span></span> <span data-ttu-id="3c0df-106">さらに、作成した BizTalk Server アプリケーションと関連付けられたログインが存在することもあります。</span><span class="sxs-lookup"><span data-stu-id="3c0df-106">You may have additional logins associated with the BizTalk Server applications you have created.</span></span> <span data-ttu-id="3c0df-107">BizTalk Server データベースを新しいサーバーか SQL Server の新しいインスタンスに移動するときは、ログインをバックアップし復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c0df-107">You need to back up the logins and restore them when moving the BizTalk Server databases to a new server or new instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="3c0df-108">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="3c0df-108">BizTalk Application Users</span></span>  
  
-   <span data-ttu-id="3c0df-109">BizTalk 分離ホスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="3c0df-109">BizTalk Isolated Host Users</span></span>  
  
-   <span data-ttu-id="3c0df-110">BizTalk Server 管理者</span><span class="sxs-lookup"><span data-stu-id="3c0df-110">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="3c0df-111">BizTalk Server オペレータ</span><span class="sxs-lookup"><span data-stu-id="3c0df-111">BizTalk Server Operators</span></span>  
  
-   <span data-ttu-id="3c0df-112">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="3c0df-112">SSO Administrators</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="3c0df-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="3c0df-113">Prerequisites</span></span>  
<span data-ttu-id="3c0df-114">メンバーである必要がある必要があります、**管理者**バックアップおよびログインを復元する場所の SQL Server のセキュリティ ロール。</span><span class="sxs-lookup"><span data-stu-id="3c0df-114">You must be a member of the **Administrators** security role on the SQL Server where you backup and restore the logins.</span></span>  
  
## <a name="back-up-a-login-using-a-script"></a><span data-ttu-id="3c0df-115">スクリプトを使用してログインをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="3c0df-115">Back up a login using a script</span></span>  
  
1.  <span data-ttu-id="3c0df-116">開いている**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="3c0df-116">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="3c0df-117">展開**セキュリティ**の一覧を展開および**ログイン**です。</span><span class="sxs-lookup"><span data-stu-id="3c0df-117">Expand **Security**, and expand the list of **Logins**.</span></span>  
  
3.  <span data-ttu-id="3c0df-118">では、バックアップ スクリプトを作成し、選択するログインを右クリックして**ログインをスクリプト**です。</span><span class="sxs-lookup"><span data-stu-id="3c0df-118">Right-click the login you want to create a backup script for, and then select **Script Login as**.</span></span>  
  
4.  <span data-ttu-id="3c0df-119">選択**Create**のいずれかを選択し、**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**スクリプトの宛先を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c0df-119">Select **CREATE To**, and then select one of **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="3c0df-120">通常、変換先は、ファイルが、 **.sql**拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="3c0df-120">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="3c0df-121">スクリプト化するログインごとに手順 3. 以降を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="3c0df-121">Repeat this procedure from Step 3 for each login you want to script.</span></span> <span data-ttu-id="3c0df-122">スクリプト化が必要なログインを決定するには、BizTalk Server 関連ログインの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c0df-122">Refer to the list of BizTalk Server related logins to determine which logins you need to script.</span></span>  
  
## <a name="restore-a-login-from-a-script"></a><span data-ttu-id="3c0df-123">スクリプトからログインを復元します。</span><span class="sxs-lookup"><span data-stu-id="3c0df-123">Restore a login from a script</span></span>  
  
1.  <span data-ttu-id="3c0df-124">開いている**SQL Server Management Studio**です。</span><span class="sxs-lookup"><span data-stu-id="3c0df-124">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="3c0df-125">**ファイル**] メニューの [**開く**をスクリプト化されたログインを含むファイルです。</span><span class="sxs-lookup"><span data-stu-id="3c0df-125">On the **File** menu, **Open** the file containing the scripted login.</span></span>  
  
3.  <span data-ttu-id="3c0df-126">ログインを作成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c0df-126">Execute the script to create the login.</span></span>