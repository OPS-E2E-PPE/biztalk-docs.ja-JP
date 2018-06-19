---
title: Biztalk SQL アダプターを使用してクエリ通知のメッセージ スキーマ |Microsoft ドキュメント
description: SQL アダプターを使用して、BizTalk で SQL Server データベースからクエリ通知を受信するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5183655-64d4-4767-a923-0a575e3708cd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f662f34a9ac31dd5ce200d776bc8b542008e98e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963406"
---
# <a name="message-schemas-for-query-notification"></a><span data-ttu-id="c480e-103">クエリ通知のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c480e-103">Message Schemas for Query Notification</span></span>
<span data-ttu-id="c480e-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの SQL Server データベースからクエリ通知を受信する通知操作します。</span><span class="sxs-lookup"><span data-stu-id="c480e-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Notification operation to receive query notifications from the SQL Server database.</span></span>  
  
 <span data-ttu-id="c480e-105">バインドのプロパティを設定して通知の操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c480e-105">You configure the Notification operation by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="c480e-106">通知に関連するバインドのプロパティの詳細については、次を参照してください。 [SQL Server のアダプターのバインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="c480e-106">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="c480e-107">設定する、 **NotificationStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ\>)、クエリ通知のです。</span><span class="sxs-lookup"><span data-stu-id="c480e-107">You set the **NotificationStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the query notification.</span></span> <span data-ttu-id="c480e-108">このクエリの結果セットは、通知の操作で自分のコードを厳密に型指定されたデータとして返されます。</span><span class="sxs-lookup"><span data-stu-id="c480e-108">The result set of this query is returned as strongly-typed data to your code in the Notification operation.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="c480e-109">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="c480e-109">Message Structure for the Notification operation</span></span>  
 <span data-ttu-id="c480e-110">次の表は、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-110">The following table shows the XML message structure for the Notification operation.</span></span>  

<span data-ttu-id="c480e-111">**操作**:`Notification`</span><span class="sxs-lookup"><span data-stu-id="c480e-111">**Operation**: `Notification`</span></span>

<span data-ttu-id="c480e-112">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="c480e-112">**XML message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

<span data-ttu-id="c480e-113">**説明**: これは、SQL Server によってアダプターのクライアントに送信される受信メッセージ。</span><span class="sxs-lookup"><span data-stu-id="c480e-113">**Description**: This is the inbound message that is sent by the SQL Server to the adapter clients.</span></span> <span data-ttu-id="c480e-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="c480e-114">In the message:</span></span>

- <span data-ttu-id="c480e-115">`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-115">The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="c480e-116">たとえば、このタグ内の「挿入」値は、通知のステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span>
- <span data-ttu-id="c480e-117">`<Source>`タグは、通知の送信元を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-117">The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="c480e-118">たとえば、このタグで「データ」の値では、参照されたオブジェクト内のデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="c480e-119">同様に、このタグで「オブジェクト」の値では、参照されたオブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span>
- <span data-ttu-id="c480e-120">`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-120">The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="c480e-121">クエリ通知メッセージは、2 つの種類: 変更および定期受信します。</span><span class="sxs-lookup"><span data-stu-id="c480e-121">Query notification messages are of two types: change and subscribe.</span></span> <span data-ttu-id="c480e-122">A「変更」の値、`<Type>`タグを示すクエリの結果が変更された一方で「サブスクライブ」の値、`<Type>`タグは、サブスクリプション要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c480e-122">A “change” value in the `<Type>` tag indicates that the results of the query have changed, whereas a “subscribe” value in the `<Type>` tag indicates that a subscription request failed.</span></span>

  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="c480e-123">通知操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="c480e-123">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="c480e-124">通知操作のメッセージ アクションは「通知」</span><span class="sxs-lookup"><span data-stu-id="c480e-124">The message action for the notification operation is “Notification.”</span></span>  
  