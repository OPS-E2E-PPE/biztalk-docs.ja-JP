---
title: 通知 Operation2 のメッセージ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dddab2ef-94db-46c8-95c1-57517681e8dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1226f31c43b3274c841f92473807d3d4bc709090
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530677"
---
# <a name="message-schemas-for-the-notification-operation"></a><span data-ttu-id="2335e-102">通知操作のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2335e-102">Message Schemas for the Notification Operation</span></span>
<span data-ttu-id="2335e-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]Oracle E-business Suite で基になるデータベースからデータベース変更通知を受信する通知の操作を表示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]surfaces the Notification operation to receive database change notifications from the underlying database in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="2335e-104">バインドのプロパティを設定して、通知の操作を構成する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2335e-104">You configure the Notification operation by setting binding properties in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="2335e-105">通知に関連するバインドのプロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="2335e-105">For more information about the Notification-related binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span> <span data-ttu-id="2335e-106">設定する、 **NotificationStatement**クエリ通知の SELECT ステートメントを指定するプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="2335e-106">You set the **NotificationStatement** binding property to specify a SELECT statement for the query notification.</span></span>  
  
## <a name="message-structure-for-the-notification-operation"></a><span data-ttu-id="2335e-107">通知操作のメッセージの構造</span><span class="sxs-lookup"><span data-stu-id="2335e-107">Message Structure for the Notification Operation</span></span>  
 <span data-ttu-id="2335e-108">次の表では、通知操作の XML メッセージの構造を示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-108">The following table shows the XML message structure for the Notification operation.</span></span>  
  
|<span data-ttu-id="2335e-109">演算</span><span class="sxs-lookup"><span data-stu-id="2335e-109">Operation</span></span>|<span data-ttu-id="2335e-110">XML メッセージ</span><span class="sxs-lookup"><span data-stu-id="2335e-110">XML Message</span></span>|<span data-ttu-id="2335e-111">説明</span><span class="sxs-lookup"><span data-stu-id="2335e-111">Description</span></span>|  
|---------------|-----------------|-----------------|  
|<span data-ttu-id="2335e-112">Notification</span><span class="sxs-lookup"><span data-stu-id="2335e-112">Notification</span></span>|`<?xml version="1.0" encoding="utf-8" ?>  <Notification xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/Notification">    <Info>Value</Info>    <Source>Value</Source>    <Type>Value</Type> </Notification>`|<span data-ttu-id="2335e-113">これは、Oracle E-business Suite アダプター クライアントに送信される受信メッセージです。</span><span class="sxs-lookup"><span data-stu-id="2335e-113">This is the inbound message that is sent by Oracle E-Business Suite to the adapter clients.</span></span> <span data-ttu-id="2335e-114">メッセージ。</span><span class="sxs-lookup"><span data-stu-id="2335e-114">In the message:</span></span><br /><br /> <span data-ttu-id="2335e-115">-`<Info>`タグは、通知の理由を示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-115">- The `<Info>` tag indicates the reason for the notification.</span></span> <span data-ttu-id="2335e-116">たとえば、このタグ内の"insert"値は、notification ステートメントで参照されるテーブルの 1 つ以上のデータが挿入されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-116">For example, an “insert” value in this tag indicates that data has been inserted in one or more of the tables referenced in the notification statement.</span></span><br /><br /> <span data-ttu-id="2335e-117">-`<Source>`タグは、通知のソースを示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-117">- The `<Source>` tag indicates the source for the notification.</span></span> <span data-ttu-id="2335e-118">たとえば、このタグ内の「データ」の値では、参照先オブジェクトのデータの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-118">For example, a “data” value in this tag indicates a change in the data in a referenced object.</span></span> <span data-ttu-id="2335e-119">同様に、このタグ内の「オブジェクト」の値では、参照先オブジェクトの変更を示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-119">Similarly, an “object” value in this tag indicates a change in a referenced object.</span></span><br /><br /> <span data-ttu-id="2335e-120">-`<Type>`タグは、データの変更の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-120">- The `<Type>` tag indicates the type of data change.</span></span> <span data-ttu-id="2335e-121">たとえば、"Update"の値、`<Type>`タグは、クエリの結果が更新されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="2335e-121">For example, an “Update” value in the `<Type>` tag indicates that the results of the query have been updated.</span></span>|  
  
## <a name="message-action-for-the-notification-operation"></a><span data-ttu-id="2335e-122">通知操作のメッセージのアクション</span><span class="sxs-lookup"><span data-stu-id="2335e-122">Message Action for the Notification Operation</span></span>  
 <span data-ttu-id="2335e-123">通知操作のメッセージのアクションは、「通知します」</span><span class="sxs-lookup"><span data-stu-id="2335e-123">The message action for the notification operation is “Notification.”</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2335e-124">参照</span><span class="sxs-lookup"><span data-stu-id="2335e-124">See Also</span></span>  
 [<span data-ttu-id="2335e-125">メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="2335e-125">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)