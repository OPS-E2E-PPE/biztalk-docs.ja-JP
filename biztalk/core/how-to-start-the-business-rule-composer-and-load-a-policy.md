---
title: ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, loading
- opening, Busines Rule Composer
- Business Rule Composer, policies
- Business Rule Composer, opening
ms.assetid: 34a6034d-90b3-4ce0-9770-3790763affe3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27739c126ab4b713d13d3fb3dc86c0cc6fea1cc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333884"
---
# <a name="how-to-start-the-business-rule-composer-and-load-a-policy"></a><span data-ttu-id="55539-102">ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法</span><span class="sxs-lookup"><span data-stu-id="55539-102">How to Start the Business Rule Composer and Load a Policy</span></span>
<span data-ttu-id="55539-103">このセクションでは、ビジネス ルール作成ツールを起動し、ポリシーの読み込みする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55539-103">This section describes how to start the Business Rule Composer and load a policy.</span></span>  
  
### <a name="to-start-the-business-rule-composer"></a><span data-ttu-id="55539-104">ビジネス ルール作成ツールを開始するには</span><span class="sxs-lookup"><span data-stu-id="55539-104">To start the Business Rule Composer</span></span>  
  
- <span data-ttu-id="55539-105">**開始**メニューで、**すべてのプログラム**、microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="55539-105">On the **Start** menu, point to **All Programs**, point to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **Business Rule Composer**.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="55539-106">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="55539-106">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="55539-107">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="55539-107">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
### <a name="to-load-a-policy"></a><span data-ttu-id="55539-108">ポリシーを読み込めません</span><span class="sxs-lookup"><span data-stu-id="55539-108">To load a policy</span></span>  
  
1.  <span data-ttu-id="55539-109">ビジネス ルール作成ツールで、上、**ルール ストア** メニューのをクリックして**ロード**します。</span><span class="sxs-lookup"><span data-stu-id="55539-109">In the Business Rule Composer, on the **Rule Store** menu, click **Load**.</span></span>  
  
2.  <span data-ttu-id="55539-110">**ルール ストア** ダイアログ ボックスで、 **SQL Server**ドロップダウン リストで、接続する SQL Server™ コンピューターを選択します。</span><span class="sxs-lookup"><span data-stu-id="55539-110">In the **Rule Store** dialog box, in the **SQL Server** drop-down list, select the SQL Server™ computer to which you want to connect.</span></span>  
  
3.  <span data-ttu-id="55539-111">**データベース**ドロップダウン リストで、開きたいルール ストアを含むデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="55539-111">In the **Database** drop-down list, select the database that contains the rule store you want to open.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55539-112">既定のデータベースがインストールされているルール ストアを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は**BizTalkRuleEngineDb**します。</span><span class="sxs-lookup"><span data-stu-id="55539-112">The default database for the rule store installed by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is **BizTalkRuleEngineDb**.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="55539-113">持つ、新しく作成された SQL Server アカウントを使用するかどうか、**パスワードの有効期限を適用する**と**ユーザーは次回ログイン時にパスワードを変更する必要があります**オプション セットでは、ビジネス ルール作成ツールは、ルールへの接続に失敗しますエンジンのデータベースです。</span><span class="sxs-lookup"><span data-stu-id="55539-113">If you use a newly created SQL Server account that has the **Enforce password expiration** and **User must change password at next login** options set, the business rule composer will fail to connect to the Rule Engine database.</span></span>