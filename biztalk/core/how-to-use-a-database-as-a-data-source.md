---
title: データ ソースとしてデータベースを使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13b05869501283796d8c1c42f85e2551a4333927
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383605"
---
# <a name="how-to-use-a-database-as-a-data-source"></a><span data-ttu-id="1130c-102">データベースをデータ ソースとして使用する方法</span><span class="sxs-lookup"><span data-stu-id="1130c-102">How to Use a Database as a Data Source</span></span>
<span data-ttu-id="1130c-103">データベースをデータ ソースとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="1130c-103">You can specify a database as a data source.</span></span> <span data-ttu-id="1130c-104">データベースからテーブルまたはテーブルの列を続けて選択し、ファクトとして使用するボキャブラリ定義またはルール上にドラッグできます。</span><span class="sxs-lookup"><span data-stu-id="1130c-104">You can subsequently select a table or table column from the database, and drag it onto a vocabulary definition or rule to use as a fact.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1130c-105">いずれかを使用してデータベース行/テーブルにバインドすることもできます**DataConnection**または**TypedDataTable**から「データ接続」や「データベースのテーブルの行/」を選択して、**データベース バインドの種類**ドロップダウン ボックスの [プロパティ] ウィンドウで、**データベース**ファクト エクスプ ローラーのタブ。</span><span class="sxs-lookup"><span data-stu-id="1130c-105">You can choose to bind to the database row/table using either **DataConnection** or **TypedDataTable** by selecting "Data connection" or "Database table/row" from the **Database binding type** drop-down box in the Property Window for the **Databases** tab of Fact Explorer.</span></span> <span data-ttu-id="1130c-106">**DataConnection**既定によってバインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="1130c-106">**DataConnection** binding is used by default.</span></span>  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a><span data-ttu-id="1130c-107">SQL データベースをデータ ソースとして指定するには</span><span class="sxs-lookup"><span data-stu-id="1130c-107">To specify a SQL database as a data source</span></span>  
  
1.  <span data-ttu-id="1130c-108">[ファクト エクスプ ローラー] ウィンドウ、**データベース**タブです。</span><span class="sxs-lookup"><span data-stu-id="1130c-108">In the Facts Explorer window, click the **Databases** tab.</span></span>  
  
2.  <span data-ttu-id="1130c-109">右クリックし、**サーバー**ノードをクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="1130c-109">Right-click the **Servers** node, and then click **Browse**.</span></span>  
  
3.  <span data-ttu-id="1130c-110">ドロップダウン リストで、利用可能なデータベース サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1130c-110">In the drop-down list, select an available database server.</span></span>  
  
4.  <span data-ttu-id="1130c-111">認証の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="1130c-111">Select an authentication type.</span></span> <span data-ttu-id="1130c-112">SQL Server 認証を選択した場合は、ログイン名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1130c-112">If you select SQL authentication, enter a logon name and password.</span></span> <span data-ttu-id="1130c-113">ユーザーの認証情報を入力したら、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="1130c-113">When you have entered your authentication information, click **OK**.</span></span>  
  
     <span data-ttu-id="1130c-114">![ツリー ブラウザーのデータベースのスクリーン ショット。](../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span><span class="sxs-lookup"><span data-stu-id="1130c-114">![Screenshot of databases of tree brower.](../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")</span></span>  
<span data-ttu-id="1130c-115">データベースの参照</span><span class="sxs-lookup"><span data-stu-id="1130c-115">Browsing a database</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1130c-116">SQL Server データベースのビューはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1130c-116">SQL Server database views are not supported.</span></span>