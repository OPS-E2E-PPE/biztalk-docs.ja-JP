---
title: "メッセージ通知 Operation2 のスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8c004e83ada00b41013c2a22c5e48f29bb39ffd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="cba9c-102">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cba9c-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="cba9c-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で基になるデータベースからデータベースの変更通知を受信する通知の操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces the Notification operation to receive database change notifications from the underlying database in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="cba9c-104">バインドのプロパティを設定して通知の操作を構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="cba9c-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="cba9c-105">通知に関連するバインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="cba9c-105">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="cba9c-106">設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="cba9c-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="cba9c-107">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="cba9c-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="cba9c-108">次の表は、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="cba9c-109">操作</span><span class="sxs-lookup"><span data-stu-id="cba9c-109">Operation</span></span>|<span data-ttu-id="cba9c-110">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="cba9c-110">XML Message</span></span>|<span data-ttu-id="cba9c-111">Description</span><span class="sxs-lookup"><span data-stu-id="cba9c-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="cba9c-112">Notification</span><span class="sxs-lookup"><span data-stu-id="cba9c-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="cba9c-113">これは、Oracle E-business Suite によってアダプターのクライアントに送信される受信メッセージです。</span><span class="sxs-lookup"><span data-stu-id="cba9c-113">This is the inbound message that is sent by Oracle E-Business Suite to the adapter clients.</span></span> <span data-ttu-id="cba9c-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="cba9c-114">In the message:</span></span><br /><br /> <span data-ttu-id="cba9c-115">-`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="cba9c-116">たとえば、このタグ内の「挿入」値は、通知のステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="cba9c-117">-`<Source>`タグは、通知の送信元を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="cba9c-118">たとえば、このタグで「データ」の値では、参照されたオブジェクト内のデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="cba9c-119">同様に、このタグで「オブジェクト」の値では、参照されたオブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="cba9c-120">-`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="cba9c-121">たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cba9c-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="cba9c-122">通知操作のメッセージ アクション</span><span class="sxs-lookup"><span data-stu-id="cba9c-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="cba9c-123">通知操作のメッセージ アクションは「通知」</span><span class="sxs-lookup"><span data-stu-id="cba9c-123">The message action for the notification operation is “Notification.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cba9c-124">参照</span><span class="sxs-lookup"><span data-stu-id="cba9c-124">See Also</span></span>  
 [<span data-ttu-id="cba9c-125">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="cba9c-125">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)