---
title: "ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 420517c51fd6c7a6c854afe161a11a58f952db83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a><span data-ttu-id="0756f-102">ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法</span><span class="sxs-lookup"><span data-stu-id="0756f-102">How to Start the Business Rule Composer and Load a Policy</span></span>
<span data-ttu-id="0756f-103">このセクションでは、ビジネス ルール作成ツールの起動方法とポリシーの読み込み方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0756f-103">This section describes how to start the Business Rule Composer and load a policy.</span></span>  
  
### <a name="to-start-the-business-rule-composer"></a><span data-ttu-id="0756f-104">ビジネス ルール作成ツールを起動するには</span><span class="sxs-lookup"><span data-stu-id="0756f-104">To start the Business Rule Composer</span></span>  
  
-   <span data-ttu-id="0756f-105">**開始** メニューのをポイント**すべてのプログラム**、microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="0756f-105">On the **Start** menu, point to **All Programs**, point to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0756f-106">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0756f-106">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="0756f-107">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="0756f-107">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
### <a name="to-load-a-policy"></a><span data-ttu-id="0756f-108">ポリシーを読み込むには</span><span class="sxs-lookup"><span data-stu-id="0756f-108">To load a policy</span></span>  
  
1.  <span data-ttu-id="0756f-109">ビジネス ルール作成ツールでの**ルール ストア** メニューのをクリックして**ロード**です。</span><span class="sxs-lookup"><span data-stu-id="0756f-109">In the Business Rule Composer, on the **Rule Store** menu, click **Load**.</span></span>  
  
2.  <span data-ttu-id="0756f-110">**ルール ストア** ダイアログ ボックスで、 **SQL Server**ドロップダウン リストで、接続する SQL Server™ コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="0756f-110">In the **Rule Store** dialog box, in the **SQL Server** drop-down list, select the SQL Server™ computer to which you want to connect.</span></span>  
  
3.  <span data-ttu-id="0756f-111">**データベース**ドロップダウン リストで、開きたいルール ストアを含むデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="0756f-111">In the **Database** drop-down list, select the database that contains the rule store you want to open.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0756f-112">既定のデータベースがインストールされているルール ストアを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は**BizTalkRuleEngineDb**です。</span><span class="sxs-lookup"><span data-stu-id="0756f-112">The default database for the rule store installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is **BizTalkRuleEngineDb**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0756f-113">新しく作成された SQL Server があるアカウントを使用するかどうか、**パスワードの期限を適用する**と**ユーザーは次回ログイン時にパスワードを変更する必要があります**オプションのセット、ビジネス ルール作成ツールは、ルールへの接続に失敗しますエンジンのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="0756f-113">If you use a newly created SQL Server account that has the **Enforce password expiration** and **User must change password at next login** options set, the business rule composer will fail to connect to the Rule Engine database.</span></span>