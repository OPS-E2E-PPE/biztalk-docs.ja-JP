---
title: "メッセージ通知 Operation1 のスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd0d7513a0a439d34d5bfb4722fec2b9025e676b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="a69a4-102">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="a69a4-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="a69a4-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースからデータベースの変更通知を受信する通知操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the Notification operation to receive database change notifications from the Oracle database.</span></span>  
  
 <span data-ttu-id="a69a4-104">バインドのプロパティを設定して通知の操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a69a4-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="a69a4-105">通知に関連するバインドのプロパティの詳細については、次を参照してください。 [Oracle データベース アダプターのバインドのプロパティについてお読み](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="a69a4-105">For more information about the Notification-related binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="a69a4-106">設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="a69a4-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="a69a4-107">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="a69a4-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="a69a4-108">次の表は、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="a69a4-109">操作</span><span class="sxs-lookup"><span data-stu-id="a69a4-109">Operation</span></span>|<span data-ttu-id="a69a4-110">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="a69a4-110">XML Message</span></span>|<span data-ttu-id="a69a4-111">Description</span><span class="sxs-lookup"><span data-stu-id="a69a4-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="a69a4-112">Notification</span><span class="sxs-lookup"><span data-stu-id="a69a4-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="a69a4-113">これは、Oracle データベースでアダプターのクライアントに送信される受信メッセージです。</span><span class="sxs-lookup"><span data-stu-id="a69a4-113">This is the inbound message that is sent by the Oracle database to the adapter clients.</span></span> <span data-ttu-id="a69a4-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a69a4-114">In the message:</span></span><br /><br /> <span data-ttu-id="a69a4-115">-`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="a69a4-116">たとえば、このタグ内の「挿入」値は、通知のステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="a69a4-117">-`<Source>`タグは、通知の送信元を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="a69a4-118">たとえば、このタグで「データ」の値では、参照されたオブジェクト内のデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="a69a4-119">同様に、このタグで「オブジェクト」の値では、参照されたオブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="a69a4-120">-`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="a69a4-121">たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a69a4-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="a69a4-122">通知操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="a69a4-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="a69a4-123">通知操作のメッセージ アクションは、"http://Microsoft.LobServices.OracleDB/2007/03/Notification"です。</span><span class="sxs-lookup"><span data-stu-id="a69a4-123">The message action for the notification operation is “http://Microsoft.LobServices.OracleDB/2007/03/Notification”.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a69a4-124">参照</span><span class="sxs-lookup"><span data-stu-id="a69a4-124">See Also</span></span>  
 [<span data-ttu-id="a69a4-125">メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="a69a4-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)