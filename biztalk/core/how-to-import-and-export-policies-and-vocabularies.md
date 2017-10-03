---
title: "インポートおよびポリシーとボキャブラリをエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17ba7cd8a9fc5d28d1b718e9a47ad6cf2f448ec7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a><span data-ttu-id="517e6-102">ポリシーとボキャブラリをインポートおよびエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="517e6-102">How to Import and Export Policies and Vocabularies</span></span>
<span data-ttu-id="517e6-103">ルール エンジン展開ウィザードを使用して、インポートまたはポリシーまたはボキャブラリをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="517e6-103">You can use the Rules Engine Deployment Wizard to import or export a policy or vocabulary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="517e6-104">最初に、ポリシーまたはボキャブラリによって使用されるすべてのボキャブラリをインポートする必要があります。これを行わないと、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="517e6-104">All vocabularies used by a policy or vocabulary must be imported first or you will get an error.</span></span>  
  
### <a name="to-import-or-export-a-policy-or-vocabulary"></a><span data-ttu-id="517e6-105">ポリシーまたはボキャブラリをインポート/エクスポートするには</span><span class="sxs-lookup"><span data-stu-id="517e6-105">To import or export a policy or vocabulary</span></span>  
  
1.  <span data-ttu-id="517e6-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**ビジネス ルール エンジン展開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-106">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="517e6-107">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="517e6-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="517e6-108">これを行うには、アプリケーションを右クリックし、**管理者として実行**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-108">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="517e6-109">[ようこそ] ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-109">On the welcome page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="517e6-110">**展開タスク** ページで、いずれかを選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**または**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-110">On the **Deployment Task** page, select either **Export Policy/Vocabulary to file from database** or **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="517e6-111">**ポリシー ストア** ページで、ドロップダウン リストからを選択、使用可能な SQL Server コンピューターとデータベース、およびクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-111">On the **Policy Store** page, from the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="517e6-112">**ポリシー/ボキャブラリのエクスポート** ページで、次の操作をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-112">On the **Export Policy/Vocabulary** page, do the following, and then click **Next**.</span></span>  
  
    1.  <span data-ttu-id="517e6-113">選択**ポリシー**または**ボキャブラリ**エクスポート/インポートする対象によって異なります。</span><span class="sxs-lookup"><span data-stu-id="517e6-113">Select **Policy** or **Vocabulary** depending on what you want to export/import.</span></span>  
  
    2.  <span data-ttu-id="517e6-114">**ポリシー/ボキャブラリ**ドロップダウン リストで、目的のポリシー/ボキャブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="517e6-114">From the **Policy/Vocabulary** drop-down list, select the desired policy/vocabulary.</span></span>  
  
    3.  <span data-ttu-id="517e6-115">をクリックして**参照**定義ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="517e6-115">Click **Browse** to select the definition file.</span></span>  
  
6.  <span data-ttu-id="517e6-116">サーバー、データベース、およびポリシーまたはボキャブラリの情報を確認し、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-116">Review the server, database, and policy or vocabulary information, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="517e6-117">インポートまたはエクスポートが完了したらをクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-117">After the import or export is completed, click **Next**.</span></span>  
  
8.  <span data-ttu-id="517e6-118">インポートやエクスポートの完了ステータスを確認し、クリックして**完了**です。</span><span class="sxs-lookup"><span data-stu-id="517e6-118">Review the completion status of the import or export, and then click **Finish**.</span></span>