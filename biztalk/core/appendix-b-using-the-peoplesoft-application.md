---
title: "付録 b: PeopleSoft アプリケーションの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ff5c7b2b15c709064174371f1fcab9beb95e42d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-b-using-the-peoplesoft-application"></a><span data-ttu-id="5a514-102">付録 b: PeopleSoft アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="5a514-102">Appendix B: Using the PeopleSoft Application</span></span>
<span data-ttu-id="5a514-103">このセクションでは、オーケストレーションのテストに役立つ、PeopleSoft のさまざまな領域の使用法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a514-103">This section describes using different areas of PeopleSoft that could be useful in your orchestration testing.</span></span>  
  
 <span data-ttu-id="5a514-104">受信ポートとして PeopleSoft を使用している場合、PeopleTools を使用して XML ドキュメントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a514-104">When you use PeopleSoft for receive ports, you use PeopleTools to create an XML document.</span></span> <span data-ttu-id="5a514-105">PeopleSoft を操作するために何も特別なものは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5a514-105">Nothing special is required to interact with PeopleSoft.</span></span> <span data-ttu-id="5a514-106">イベントのできる必要がありますへのアクセス、 **http\\\\:\<ホスト >:\<ポート >** PeopleSoft からイベントをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="5a514-106">For an event, you must be able to access to an **http\\\\:\<host>:\<port>** to listen for events from PeopleSoft.</span></span> <span data-ttu-id="5a514-107">ホストやポートを使用できない場合は、PeopleSoft Integration Broker を構成することによって、特定の HTTP ホストおよびポートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5a514-107">If a host and port is not available to you, you can set up a specific HTTP host and port by configuring the PeopleSoft Integration Broker.</span></span>  
  
 <span data-ttu-id="5a514-108">完了、PeopleSoft のテストの受信ポートを[を生成する XML、または PeopleSoft のスキーマ](../core/generating-xml-or-schema-in-peoplesoft.md)PeopleSoft 環境で何かを変更して PeopleSoft イベントをトリガーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a514-108">To complete the testing of a PeopleSoft receive port, [Generating XML or Schema in PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) discusses how to trigger a PeopleSoft event by changing something in a PeopleSoft environment.</span></span> <span data-ttu-id="5a514-109">この変更により XML ファイルが有効になり、ファイルはオーケストレーションで監視対象として設定したフォルダーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5a514-109">The change activates an XML file that is sent to the folder you set in the orchestration to be monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a514-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5a514-110">In This Section</span></span>  
  
-   [<span data-ttu-id="5a514-111">PeopleSoft で XML またはスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="5a514-111">Generating XML or Schema in PeopleSoft</span></span>](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [<span data-ttu-id="5a514-112">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a514-112">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)