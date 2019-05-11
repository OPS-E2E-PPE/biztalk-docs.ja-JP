---
title: ポーリングと TypedPolling 操作では、BizTalk SQL アダプターのメッセージ スキーマ |Microsoft Docs
description: SQL アダプターの BizTalk アダプター パック (BAP) によって使用される構造をメッセージのポーリングと TypedPolling
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e900307-2c9c-493b-81c9-67af3e143eeb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4930e854bcad679a3b6ab8c3e90150ad3e879c98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368612"
---
# <a name="message-schemas-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="575bd-103">Polling 操作と TypedPolling 操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="575bd-103">Message Schemas for the Polling and TypedPolling Operations</span></span>
<span data-ttu-id="575bd-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Polling 操作と TypedPolling サーフェスの受信アダプターのクライアントに、ポーリング クエリの結果セットを返す操作。</span><span class="sxs-lookup"><span data-stu-id="575bd-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Polling and TypedPolling inbound operations to return the result set of the polling query to an adapter client.</span></span>  
  
 <span data-ttu-id="575bd-105">バインドのプロパティを設定してポーリングと TypedPolling 操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="575bd-105">You configure the Polling and TypedPolling operations by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="575bd-106">これらのバインド プロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="575bd-106">For more information about these binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="575bd-107">設定する、 **PollingStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ\>) のポーリング クエリ。</span><span class="sxs-lookup"><span data-stu-id="575bd-107">You set the **PollingStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the polling query.</span></span> <span data-ttu-id="575bd-108">このクエリの結果セットは、ポーリング操作では、コードへのデータと TypedPolling 操作で厳密に型指定されたデータとして返されます。</span><span class="sxs-lookup"><span data-stu-id="575bd-108">The result set of this query is returned as data to your code in the Polling operation, and as strongly-typed data in the TypedPolling operation.</span></span> <span data-ttu-id="575bd-109">結果セットの構造は、アダプターが指定されたクエリのサーフェスをメタデータによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="575bd-109">The structure of the result set is determined by the metadata that the adapter surfaces for the specified query.</span></span>  
  
## <a name="polling-message-structure"></a><span data-ttu-id="575bd-110">メッセージの構造のポーリング</span><span class="sxs-lookup"><span data-stu-id="575bd-110">Polling message structure</span></span> 
  
<span data-ttu-id="575bd-111">**操作**: `Polling`</span><span class="sxs-lookup"><span data-stu-id="575bd-111">**Operation**: `Polling`</span></span>

<span data-ttu-id="575bd-112">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="575bd-112">**XML Message**:</span></span>  
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

<span data-ttu-id="575bd-113">**説明**:SQL Server によってアダプター クライアントに送信される受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="575bd-113">**Description**: The inbound message that is sent by the SQL Server to the adapter clients.</span></span>  


## <a name="typedpolling-message-structure"></a><span data-ttu-id="575bd-114">TypedPolling メッセージの構造</span><span class="sxs-lookup"><span data-stu-id="575bd-114">TypedPolling message structure</span></span> 

<span data-ttu-id="575bd-115">**操作**: `TypedPolling`</span><span class="sxs-lookup"><span data-stu-id="575bd-115">**Operation**: `TypedPolling`</span></span>

<span data-ttu-id="575bd-116">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="575bd-116">**XML Message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <TypedPollingResultSet xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedPolling">
    <COLUMN1>[Value]</Column1>
    <COLUMN2>[Value]</Column2>
    …
  </TypedPollingResultSet>
```

<span data-ttu-id="575bd-117">**説明**:厳密に型指定された受信メッセージを SQL Server によってアダプター クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="575bd-117">**Description**: The strongly-typed inbound message that is sent by the SQL Server to the adapter clients.</span></span>
  
## <a name="message-action-for-the-polling-and-typedpolling-operations"></a><span data-ttu-id="575bd-118">Polling 操作と TypedPolling 操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="575bd-118">Message Action for the Polling and TypedPolling Operations</span></span>  
 <span data-ttu-id="575bd-119">メッセージのアクションにします。</span><span class="sxs-lookup"><span data-stu-id="575bd-119">The message action for the:</span></span>  
  
-   <span data-ttu-id="575bd-120">ポーリング操作が「ポーリングします。」</span><span class="sxs-lookup"><span data-stu-id="575bd-120">Polling operation is “Polling.”</span></span>  
  
-   <span data-ttu-id="575bd-121">TypedPolling 操作は、"TypedPolling"</span><span class="sxs-lookup"><span data-stu-id="575bd-121">TypedPolling operation is “TypedPolling.”</span></span>  
  
