---
title: バックアップおよび SQL Server ログインを復元する方法 |Microsoft Docs
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
ms.openlocfilehash: 87634ca9e9f8bbd3cc7508ce0bcfe54e5154ca0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387109"
---
# <a name="how-to-back-up-and-restore-sql-server-logins"></a><span data-ttu-id="ba354-102">バックアップおよび SQL Server ログインを復元する方法</span><span class="sxs-lookup"><span data-stu-id="ba354-102">How to Back Up and Restore SQL Server Logins</span></span>
<span data-ttu-id="ba354-103">バックアップし、BizTalk Server に関連付けられている SQL Server ログインを復元します。</span><span class="sxs-lookup"><span data-stu-id="ba354-103">Back up and restore SQL Server logins associated with BizTalk Server.</span></span>  
  
## <a name="biztalk-server-sql-server-security-logins"></a><span data-ttu-id="ba354-104">BizTalk Server SQL Server セキュリティ ログイン</span><span class="sxs-lookup"><span data-stu-id="ba354-104">BizTalk Server SQL Server Security Logins</span></span>  
 <span data-ttu-id="ba354-105">以下に示す SQL Server セキュリティ ログインは、BizTalk Server に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="ba354-105">The SQL Server security logins listed below are associated with BizTalk Server.</span></span> <span data-ttu-id="ba354-106">追加のログインを作成した BizTalk Server アプリケーションに関連付けられているがあります。</span><span class="sxs-lookup"><span data-stu-id="ba354-106">You may have additional logins associated with the BizTalk Server applications you have created.</span></span> <span data-ttu-id="ba354-107">ログインをバックアップし、新しいサーバーまたは SQL Server の新しいインスタンスを BizTalk Server データベースを移動する場合、それらを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba354-107">You need to back up the logins and restore them when moving the BizTalk Server databases to a new server or new instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="ba354-108">BizTalk Application Users</span><span class="sxs-lookup"><span data-stu-id="ba354-108">BizTalk Application Users</span></span>  
  
-   <span data-ttu-id="ba354-109">BizTalk 分離ホスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="ba354-109">BizTalk Isolated Host Users</span></span>  
  
-   <span data-ttu-id="ba354-110">BizTalk Server 管理者</span><span class="sxs-lookup"><span data-stu-id="ba354-110">BizTalk Server Administrators</span></span>  
  
-   <span data-ttu-id="ba354-111">BizTalk Server オペレータ</span><span class="sxs-lookup"><span data-stu-id="ba354-111">BizTalk Server Operators</span></span>  
  
-   <span data-ttu-id="ba354-112">SSO 管理者</span><span class="sxs-lookup"><span data-stu-id="ba354-112">SSO Administrators</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="ba354-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="ba354-113">Prerequisites</span></span>  
<span data-ttu-id="ba354-114">メンバーである必要がありますが、**管理者**バックアップおよびログインを復元する場所の SQL Server のセキュリティ ロール。</span><span class="sxs-lookup"><span data-stu-id="ba354-114">You must be a member of the **Administrators** security role on the SQL Server where you backup and restore the logins.</span></span>  
  
## <a name="back-up-a-login-using-a-script"></a><span data-ttu-id="ba354-115">バックアップ スクリプトを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="ba354-115">Back up a login using a script</span></span>  
  
1.  <span data-ttu-id="ba354-116">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ba354-116">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="ba354-117">展開**セキュリティ**の一覧を展開および**ログイン**します。</span><span class="sxs-lookup"><span data-stu-id="ba354-117">Expand **Security**, and expand the list of **Logins**.</span></span>  
  
3.  <span data-ttu-id="ba354-118">バックアップ スクリプトを作成し、選択するログインを右クリックして**ログインをスクリプト**します。</span><span class="sxs-lookup"><span data-stu-id="ba354-118">Right-click the login you want to create a backup script for, and then select **Script Login as**.</span></span>  
  
4.  <span data-ttu-id="ba354-119">選択**Create**、しのいずれかを選択します**新しいクエリ エディター ウィンドウ**、**ファイル**、または**クリップボード**をスクリプトの宛先を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba354-119">Select **CREATE To**, and then select one of **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="ba354-120">コピー先のファイルは、通常、 **.sql**拡張機能。</span><span class="sxs-lookup"><span data-stu-id="ba354-120">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="ba354-121">スクリプトを作成ログインごとに手順 3 からこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ba354-121">Repeat this procedure from Step 3 for each login you want to script.</span></span> <span data-ttu-id="ba354-122">一覧を参照してください。 BizTalk Server 関連ログイン スクリプトを作成する必要がありますを決定するログイン。</span><span class="sxs-lookup"><span data-stu-id="ba354-122">Refer to the list of BizTalk Server related logins to determine which logins you need to script.</span></span>  
  
## <a name="restore-a-login-from-a-script"></a><span data-ttu-id="ba354-123">スクリプトからログインを復元します。</span><span class="sxs-lookup"><span data-stu-id="ba354-123">Restore a login from a script</span></span>  
  
1.  <span data-ttu-id="ba354-124">**SQL Server Management Studio** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ba354-124">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="ba354-125">**ファイル**] メニューの [**オープン**スクリプト化されたログインを含むファイル。</span><span class="sxs-lookup"><span data-stu-id="ba354-125">On the **File** menu, **Open** the file containing the scripted login.</span></span>  
  
3.  <span data-ttu-id="ba354-126">ログインを作成するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba354-126">Execute the script to create the login.</span></span>