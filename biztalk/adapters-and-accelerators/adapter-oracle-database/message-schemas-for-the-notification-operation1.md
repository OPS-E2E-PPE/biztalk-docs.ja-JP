---
title: 通知 Operation1 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f98d76d0-6084-4de7-b6ff-124202ca92ab
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdf371335a1242423c4497f186fa5764f5b2fb2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991691"
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="c262d-102">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c262d-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="c262d-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースからデータベース変更通知を受信する通知の操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the Notification operation to receive database change notifications from the Oracle database.</span></span>  
  
 <span data-ttu-id="c262d-104">バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c262d-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c262d-105">通知に関連するバインドのプロパティの詳細については、[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c262d-105">For more information about the Notification-related binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="c262d-106">設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="c262d-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="c262d-107">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="c262d-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="c262d-108">次の表では、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="c262d-109">演算</span><span class="sxs-lookup"><span data-stu-id="c262d-109">Operation</span></span>|<span data-ttu-id="c262d-110">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="c262d-110">XML Message</span></span>|<span data-ttu-id="c262d-111">説明</span><span class="sxs-lookup"><span data-stu-id="c262d-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="c262d-112">Notification</span><span class="sxs-lookup"><span data-stu-id="c262d-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://Microsoft.LobServices.OracleDB/2007/03/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="c262d-113">これは、Oracle データベース アダプターのクライアントに送信される受信メッセージです。</span><span class="sxs-lookup"><span data-stu-id="c262d-113">This is the inbound message that is sent by the Oracle database to the adapter clients.</span></span> <span data-ttu-id="c262d-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="c262d-114">In the message:</span></span><br /><br /> <span data-ttu-id="c262d-115">-`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="c262d-116">たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="c262d-117">-`<Source>`タグは、通知のソースを示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="c262d-118">たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="c262d-119">同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="c262d-120">-`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="c262d-121">たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="c262d-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="c262d-122">通知操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="c262d-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="c262d-123">通知操作のメッセージのアクションが"<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>します。</span><span class="sxs-lookup"><span data-stu-id="c262d-123">The message action for the notification operation is “<http://Microsoft.LobServices.OracleDB/2007/03/Notification”>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c262d-124">参照</span><span class="sxs-lookup"><span data-stu-id="c262d-124">See Also</span></span>  
 [<span data-ttu-id="c262d-125">BizTalk Adapter for Oracle Database 用のメッセージとメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c262d-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)