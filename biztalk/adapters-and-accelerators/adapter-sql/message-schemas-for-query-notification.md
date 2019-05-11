---
title: Biztalk SQL アダプターを使用してクエリ通知のメッセージ スキーマ |Microsoft Docs
description: SQL アダプタを使用して、BizTalk での SQL Server データベースからクエリ通知を受け取る
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
ms.openlocfilehash: be33d8990e5577fbb52cd1d294dff4c5257c3bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368432"
---
# <a name="message-schemas-for-query-notification"></a><span data-ttu-id="07bdb-103">クエリ通知のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="07bdb-103">Message Schemas for Query Notification</span></span>
<span data-ttu-id="07bdb-104">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]サーフェスの SQL Server データベースからクエリ通知を受信する通知操作。</span><span class="sxs-lookup"><span data-stu-id="07bdb-104">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] surfaces the Notification operation to receive query notifications from the SQL Server database.</span></span>  
  
 <span data-ttu-id="07bdb-105">バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-105">You configure the Notification operation by setting binding properties in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="07bdb-106">通知に関連するバインドのプロパティの詳細については、次を参照してください。 [for SQL Server のアダプターのバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-106">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="07bdb-107">設定する、 **NotificationStatement** SQL ステートメントを指定するプロパティのバインド (SELECT または EXEC\<ストアド プロシージャ\>) のクエリ通知します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-107">You set the **NotificationStatement** binding property to specify a SQL statement (SELECT or EXEC \<stored procedure\>) for the query notification.</span></span> <span data-ttu-id="07bdb-108">このクエリの結果セットは、通知の操作では、コードを厳密に型指定されたデータとして返されます。</span><span class="sxs-lookup"><span data-stu-id="07bdb-108">The result set of this query is returned as strongly-typed data to your code in the Notification operation.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="07bdb-109">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="07bdb-109">Message Structure for the Notification operation</span></span>  
 <span data-ttu-id="07bdb-110">次の表では、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-110">The following table shows the XML message structure for the Notification operation.</span></span>  

<span data-ttu-id="07bdb-111">**操作**: `Notification`</span><span class="sxs-lookup"><span data-stu-id="07bdb-111">**Operation**: `Notification`</span></span>

<span data-ttu-id="07bdb-112">**XML メッセージ**:</span><span class="sxs-lookup"><span data-stu-id="07bdb-112">**XML message**:</span></span>  
```xml
<?xml version="1.0" encoding="utf-8" ?>
  <Notification xmlns="http://schemas.microsoft.com/Sql/2008/05/Notification">
    <Info>Value</Info>
    <Source>Value</Source>
    <Type>Value</Type>
 </Notification>
```

<span data-ttu-id="07bdb-113">**説明**:これは、SQL Server によってアダプター クライアントに送信される受信メッセージです。</span><span class="sxs-lookup"><span data-stu-id="07bdb-113">**Description**: This is the inbound message that is sent by the SQL Server to the adapter clients.</span></span> <span data-ttu-id="07bdb-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="07bdb-114">In the message:</span></span>

- <span data-ttu-id="07bdb-115">`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-115">The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="07bdb-116">たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span>
- <span data-ttu-id="07bdb-117">`<Source>`タグは、通知のソースを示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-117">The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="07bdb-118">たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="07bdb-119">同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span>
- <span data-ttu-id="07bdb-120">`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-120">The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="07bdb-121">クエリ通知メッセージが 2 つの型: 変更およびサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="07bdb-121">Query notification messages are of two types: change and subscribe.</span></span> <span data-ttu-id="07bdb-122">A は値を「変更」、`<Type>`タグが、クエリの結果が変更されたことを示しますに「サブスクライブ」の値、`<Type>`タグは、サブスクリプション要求が失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="07bdb-122">A “change” value in the `<Type>` tag indicates that the results of the query have changed, whereas a “subscribe” value in the `<Type>` tag indicates that a subscription request failed.</span></span>

  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="07bdb-123">通知操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="07bdb-123">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="07bdb-124">通知操作のメッセージのアクションは、「通知します」</span><span class="sxs-lookup"><span data-stu-id="07bdb-124">The message action for the notification operation is “Notification.”</span></span>  
  