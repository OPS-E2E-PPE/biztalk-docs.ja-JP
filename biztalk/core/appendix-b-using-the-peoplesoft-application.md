---
title: 付録 B:PeopleSoft アプリケーションの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PeopleSoft, using
- using PeopleSoft application
ms.assetid: 36475836-1d23-4bb4-a3c1-cdd3fff28476
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a4b82fa41f4df874d5e0a92d53f0b1122dfb5bf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359266"
---
# <a name="appendix-b-using-the-peoplesoft-application"></a><span data-ttu-id="64096-102">付録 B:PeopleSoft アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="64096-102">Appendix B: Using the PeopleSoft Application</span></span>
<span data-ttu-id="64096-103">このセクションでは、オーケストレーションのテストに役立つ可能性がある PeopleSoft のさまざまな領域を使用して説明します。</span><span class="sxs-lookup"><span data-stu-id="64096-103">This section describes using different areas of PeopleSoft that could be useful in your orchestration testing.</span></span>  
  
 <span data-ttu-id="64096-104">PeopleSoft 受信ポートを使用する場合、PeopleTools を使用する、XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="64096-104">When you use PeopleSoft for receive ports, you use PeopleTools to create an XML document.</span></span> <span data-ttu-id="64096-105">PeopleSoft を操作する特別なものが必要です。</span><span class="sxs-lookup"><span data-stu-id="64096-105">Nothing special is required to interact with PeopleSoft.</span></span> <span data-ttu-id="64096-106">イベント、する必要がありますへのアクセスに、 **http\\\\:\<ホスト\>:\<ポート\>** PeopleSoft からのイベントをリッスンするようにします。</span><span class="sxs-lookup"><span data-stu-id="64096-106">For an event, you must be able to access to an **http\\\\:\<host\>:\<port\>** to listen for events from PeopleSoft.</span></span> <span data-ttu-id="64096-107">ホストとポートを利用できない場合に、PeopleSoft Integration Broker を構成することによって、特定の HTTP ホストとポートを設定できます。</span><span class="sxs-lookup"><span data-stu-id="64096-107">If a host and port is not available to you, you can set up a specific HTTP host and port by configuring the PeopleSoft Integration Broker.</span></span>  
  
 <span data-ttu-id="64096-108">完了する、PeopleSoft のテストの受信ポート、[を生成する XML またはスキーマで PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) PeopleSoft 環境で何かを変更して PeopleSoft イベントをトリガーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64096-108">To complete the testing of a PeopleSoft receive port, [Generating XML or Schema in PeopleSoft](../core/generating-xml-or-schema-in-peoplesoft.md) discusses how to trigger a PeopleSoft event by changing something in a PeopleSoft environment.</span></span> <span data-ttu-id="64096-109">変更は、監視対象となる、オーケストレーションで設定したフォルダーに送信される XML ファイルをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="64096-109">The change activates an XML file that is sent to the folder you set in the orchestration to be monitored.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="64096-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="64096-110">In This Section</span></span>  
  
-   [<span data-ttu-id="64096-111">PeopleSoft での XML またはスキーマの生成</span><span class="sxs-lookup"><span data-stu-id="64096-111">Generating XML or Schema in PeopleSoft</span></span>](../core/generating-xml-or-schema-in-peoplesoft.md)  
  
-   [<span data-ttu-id="64096-112">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="64096-112">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)