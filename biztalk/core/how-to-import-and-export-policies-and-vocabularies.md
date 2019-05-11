---
title: インポートおよびポリシーとボキャブラリをエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, exporting
- Rule Engine Deployment Wizard
- policies, importing
- vocabularies, exporting
- vocabularies, importing
ms.assetid: c427f686-5908-4f72-9e72-46a5497274ac
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 801ac848efe183a778bbd6a1155c96f4ab41f6c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384968"
---
# <a name="how-to-import-and-export-policies-and-vocabularies"></a><span data-ttu-id="24a0e-102">インポートおよびポリシーとボキャブラリをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="24a0e-102">How to Import and Export Policies and Vocabularies</span></span>
<span data-ttu-id="24a0e-103">ルール エンジン展開ウィザードを使用して、インポートまたはポリシーまたはボキャブラリをエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="24a0e-103">You can use the Rules Engine Deployment Wizard to import or export a policy or vocabulary.</span></span>  

> [!NOTE]
>  <span data-ttu-id="24a0e-104">ポリシーまたはボキャブラリによって使用されるすべてのボキャブラリを最初にインポートする必要があります。 またはエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="24a0e-104">All vocabularies used by a policy or vocabulary must be imported first or you will get an error.</span></span>  

### <a name="to-import-or-export-a-policy-or-vocabulary"></a><span data-ttu-id="24a0e-105">インポートまたはポリシーまたはボキャブラリをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="24a0e-105">To import or export a policy or vocabulary</span></span>  

1. <span data-ttu-id="24a0e-106">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-106">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="24a0e-107">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="24a0e-107">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="24a0e-108">これを行うには、アプリケーションを右クリックし、**管理者として実行**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-108">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="24a0e-109">[ようこそ] ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-109">On the welcome page, click **Next**.</span></span>  

3. <span data-ttu-id="24a0e-110">**展開タスク** ページで、いずれかを選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**または**インポート ポリシー/ボキャブラリをファイルからデータベースに発行および**、し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-110">On the **Deployment Task** page, select either **Export Policy/Vocabulary to file from database** or **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  

4. <span data-ttu-id="24a0e-111">**ポリシー ストア**ページで、ドロップダウン リストから選択します、利用可能な SQL Server コンピューターと、データベースをクリック**次**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-111">On the **Policy Store** page, from the drop-down lists, select an available SQL Server computer and database, and then click **Next**.</span></span>  

5. <span data-ttu-id="24a0e-112">**ポリシー/ボキャブラリのエクスポート** ページで、以下を実行してをクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="24a0e-112">On the **Export Policy/Vocabulary** page, do the following, and then click **Next**.</span></span>  

   1.  <span data-ttu-id="24a0e-113">選択**ポリシー**または**ボキャブラリ**エクスポート/インポートする対象によって異なります。</span><span class="sxs-lookup"><span data-stu-id="24a0e-113">Select **Policy** or **Vocabulary** depending on what you want to export/import.</span></span>  

   2.  <span data-ttu-id="24a0e-114">**ポリシー/ボキャブラリ**ドロップダウン リストで、目的のポリシー/ボキャブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-114">From the **Policy/Vocabulary** drop-down list, select the desired policy/vocabulary.</span></span>  

   3.  <span data-ttu-id="24a0e-115">クリックして**参照**定義ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-115">Click **Browse** to select the definition file.</span></span>  

6. <span data-ttu-id="24a0e-116">サーバー、データベース、およびポリシーまたはボキャブラリの情報を確認し、クリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-116">Review the server, database, and policy or vocabulary information, and then click **Next**.</span></span>  

7. <span data-ttu-id="24a0e-117">インポートまたはエクスポートが完了した後にをクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-117">After the import or export is completed, click **Next**.</span></span>  

8. <span data-ttu-id="24a0e-118">インポートまたはエクスポートの完了ステータスを確認し、クリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="24a0e-118">Review the completion status of the import or export, and then click **Finish**.</span></span>
