---
title: "メッセージのポーリングと biztalk SQL アダプターの TypedPolling 操作のスキーマ |Microsoft ドキュメント"
description: "ポーリングと TypedPolling メッセージの BizTalk アダプター パック (BAP) で SQL アダプターによって使用される構造体"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f18185e4bfaf5502537a68044579b0f7721cd23
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="4f1af-103">ポーリングと TypedPolling 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="4f1af-103">Message Schemas for the Polling and TypedPolling Operations</span></span>
<span data-ttu-id="4f1af-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスのポーリングと TypedPolling 受信アダプターのクライアントに、ポーリング クエリの結果セットを返す操作。</span><span class="sxs-lookup"><span data-stu-id="4f1af-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Polling and TypedPolling inbound operations to return the result set of the polling query to an adapter client.</span></span>  
  
 <span data-ttu-id="4f1af-105">バインドのプロパティを設定して、ポーリングおよび TypedPolling 操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="4f1af-105">You configure the Polling and TypedPolling operations by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="4f1af-106">これらのバインド プロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="4f1af-106">For more information about these binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="4f1af-107">設定する、 **PollingStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ >)、ポーリング クエリのです。</span><span class="sxs-lookup"><span data-stu-id="4f1af-107">You set the **PollingStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure>) for the polling query.</span></span> <span data-ttu-id="4f1af-108">ポーリング操作で、コードへのデータおよび TypedPolling 操作の厳密に型指定されたデータとして、このクエリの結果セットが返されます。</span><span class="sxs-lookup"><span data-stu-id="4f1af-108">The result set of this query is returned as data to your code in the Polling operation, and as strongly-typed data in the TypedPolling operation.</span></span> <span data-ttu-id="4f1af-109">結果セットの構造は、アダプターが、指定されたクエリのサーフェスをメタデータによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="4f1af-109">The structure of the result set is determined by the metadata that the adapter surfaces for the specified query.</span></span>  
  
## <a name="polling-message-structure"></a><span data-ttu-id="4f1af-110">メッセージの構造のポーリング</span><span class="sxs-lookup"><span data-stu-id="4f1af-110">Polling message structure</span></span> 
  
<span data-ttu-id="4f1af-111">**操作**:`Polling`</span><span class="sxs-lookup"><span data-stu-id="4f1af-111">**Operation**: `Polling`</span></span>

<span data-ttu-id="4f1af-112">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="4f1af-112">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Polling xmlns="http://schemas.microsoft.com/Sql/2008/05/Polling">
    <PolledData>
      <DataSet xmlns="http://schemas.datacontract.org/2004/07/System.Data">
        <any>[Value]</any>
        <any>[Value]</any>
        …
        </DataSet>
    </PolledData>
 </Polling>
```

<span data-ttu-id="4f1af-113">**説明**: SQL Server によってアダプターのクライアントに送信される受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="4f1af-113">**Description**: The inbound message that is sent by the SQL Server to the adapter clients.</span></span>  


## <a name="typedpolling-message-structure"></a><span data-ttu-id="4f1af-114">TypedPolling メッセージの構造体</span><span class="sxs-lookup"><span data-stu-id="4f1af-114">TypedPolling message structure</span></span> 

<span data-ttu-id="4f1af-115">**操作**:`TypedPolling`</span><span class="sxs-lookup"><span data-stu-id="4f1af-115">**Operation**: `TypedPolling`</span></span>

<span data-ttu-id="4f1af-116">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="4f1af-116">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

<span data-ttu-id="4f1af-117">**説明**: SQL Server によってアダプターのクライアントに送信される厳密に型指定された受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="4f1af-117">**Description**: The strongly-typed inbound message that is sent by the SQL Server to the adapter clients.</span></span>
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="4f1af-118">ポーリングと TypedPolling 操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="4f1af-118">Message Action for the Polling and TypedPolling Operations</span></span>  
 <span data-ttu-id="4f1af-119">メッセージ アクション、します。</span><span class="sxs-lookup"><span data-stu-id="4f1af-119">The message action for the:</span></span>  
  
-   <span data-ttu-id="4f1af-120">ポーリング操作は、「ポーリングしています。」</span><span class="sxs-lookup"><span data-stu-id="4f1af-120">Polling operation is “Polling.”</span></span>  
  
-   <span data-ttu-id="4f1af-121">TypedPolling 操作は"TypedPolling"</span><span class="sxs-lookup"><span data-stu-id="4f1af-121">TypedPolling operation is “TypedPolling.”</span></span>  
  
