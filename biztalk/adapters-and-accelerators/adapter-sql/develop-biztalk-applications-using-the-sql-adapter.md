---
title: SQL アダプターを使用して BizTalk アプリケーションを開発 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5471f28e-bce1-4295-b56d-954690e60749
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9963764a298246c5a236d10b6010feee8497278f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226106"
---
# <a name="develop-biztalk-applications-using-the-sql-adapter"></a><span data-ttu-id="ca082-102">SQL アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="ca082-102">Develop BizTalk applications using the SQL adapter</span></span>
<span data-ttu-id="ca082-103">BizTalk アプリケーションの開発で BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="ca082-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate XML schema.</span></span> <span data-ttu-id="ca082-104">スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca082-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="ca082-105">CBR は、ここで、SQL Server に送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca082-105">CBR can be used in scenarios where the messages being sent to SQL Server do not require any intensive processing.</span></span> <span data-ttu-id="ca082-106">たとえば、受信ポートでのみ、特定の種類のメッセージを受信することがわかっている場合は、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca082-106">For example, if you know that the receive port will receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="ca082-107">、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ca082-107">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ca082-108">このセクションで、SQL Server を使用して操作を実行する BizTalk オーケストレーションを使用してに関する情報を提供する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ca082-108">This section provides information about using BizTalk orchestrations to perform operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ca082-109">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF バインドと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="ca082-109">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca082-110">使用する、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="ca082-110">To use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="ca082-111">バインドのプロパティを設定する方法については、次を参照してください。 [SQL アダプターのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="ca082-111">For information about how to set binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca082-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ca082-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ca082-113">SQL アダプターを使用して SQL アプリケーションを作成するための必要条件</span><span class="sxs-lookup"><span data-stu-id="ca082-113">Prerequisites to create SQL applications using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md) 
  
-   [<span data-ttu-id="ca082-114">SQL アダプタを BizTalk アプリケーションを開発する構成要素</span><span class="sxs-lookup"><span data-stu-id="ca082-114">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md) 
  
-   [<span data-ttu-id="ca082-115">Insert、Update、Delete、およびテーブルとビューを SQL アダプターでの操作の選択</span><span class="sxs-lookup"><span data-stu-id="ca082-115">Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="ca082-116">SQL アダプターを使用して大規模なデータ型を持つテーブルとビューの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-116">Run Operations on Tables and Views with Large Data Types using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/run-operations-on-tables-and-views-with-large-data-types-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="ca082-117">BizTalk Server を使用して、SQL Server でストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-117">Execute Stored Procedures in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="ca082-118">単一の XML パラメーターを持つストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-118">Execute Stored Procedures With a Single XML Parameter</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-with-a-single-xml-parameter-in-sql-using-biztalk.md)  
  
-   [<span data-ttu-id="ca082-119">ストアド プロシージャを持つ BizTalk server を使用して SQL Server で、FOR XML 句を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-119">Execute Stored Procedures Having a FOR XML Clause in SQL Server using BizTalk server</span></span>](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="ca082-120">BizTalk Server を使用して SQL Server 上の複合操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-120">Run Composite Operations on SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="ca082-121">BizTalk Server を使用して SQL Server のスカラー関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="ca082-121">Invoke Scalar Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-using-biztalk-server.md)  
  
-   [<span data-ttu-id="ca082-122">BizTalk Server を使用して SQL Server でのテーブル値関数を呼び出す</span><span class="sxs-lookup"><span data-stu-id="ca082-122">Invoke Table-Valued Functions in SQL Server by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-using-biztalk-server.md) 
  
-   [<span data-ttu-id="ca082-123">BizTalk Server を使用して ExecuteReader、ExecuteScalar、または ExecuteNonQuery 操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca082-123">Performing ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)  
  
-   [<span data-ttu-id="ca082-124">BizTalk Server と SQL アダプタを使用して、SQL Server のポーリング</span><span class="sxs-lookup"><span data-stu-id="ca082-124">Polling SQL Server by Using the SQL Adapter with BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)  
  
-   [<span data-ttu-id="ca082-125">BizTalk Server を使用して、SQL クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="ca082-125">Receive SQL Query Notifications by Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca082-126">参照</span><span class="sxs-lookup"><span data-stu-id="ca082-126">See Also</span></span>  
[<span data-ttu-id="ca082-127">SQL アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="ca082-127">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)