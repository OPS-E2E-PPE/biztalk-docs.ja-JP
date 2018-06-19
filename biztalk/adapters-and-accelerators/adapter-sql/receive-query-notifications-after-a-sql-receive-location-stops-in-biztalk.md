---
title: BizTalk Server を使用して SQL のクエリ通知した後、受信場所の内訳が表示される |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e70fa4c2-d81b-4eb0-a23d-871b64c881e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 070285dbd435160af818b1077dafb35cd9e1e545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223018"
---
# <a name="receive-query-notifications-after-a-receive-location-breakdown-in-sql-using-biztalk-server"></a><span data-ttu-id="10ef2-102">BizTalk Server を使用して SQL のクエリ通知した後、受信場所の内訳が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10ef2-102">Receive query notifications After a Receive Location Breakdown in SQL using BizTalk Server</span></span>
<span data-ttu-id="10ef2-103">EMPLOYEE テーブルに変更が加えられたときに、データベース変更の通知メッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="10ef2-103">Consider a scenario where you have a BizTalk application that receives database change notification messages when changes are made to the EMPLOYEE table.</span></span> <span data-ttu-id="10ef2-104">一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割すると、同時に EMPLOYEE テーブルにレコードが追加される、最近追加されたレコードの通知を受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="10ef2-104">If the receive location configured as part of the BizTalk application breaks down, and simultaneously records are added into the EMPLOYEE table, you will not receive notifications for the recently added records.</span></span> <span data-ttu-id="10ef2-105">わからない場合、受信場所が再び使用可能。</span><span class="sxs-lookup"><span data-stu-id="10ef2-105">You will also not know when the receive location is available again.</span></span> <span data-ttu-id="10ef2-106">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド プロパティを公開**NotifyOnListenerStart**、されるを取得する通知が受信場所の回復を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="10ef2-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes a binding property, **NotifyOnListenerStart**, that you can configure to get a notification that the receive location has recovered.</span></span> <span data-ttu-id="10ef2-107">次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="10ef2-107">You can specify the following values for the **NotifyOnListenerStart** binding property:</span></span>  
  
-   <span data-ttu-id="10ef2-108">このプロパティを設定**True**、受信場所が使用できる、受信場所を復旧するとすぐに知らせる通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="10ef2-108">Set this property to **True**, to receive a notification informing that the receive location is available, as soon as the receive location recovers.</span></span>  
  
-   <span data-ttu-id="10ef2-109">このプロパティを設定**False**、受信場所が復旧されると、受信場所の回復後通知通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="10ef2-109">Set this property to **False**, to not receive a notification informing that the receive location has recovered, after the receive location recovers.</span></span>  
  
 <span data-ttu-id="10ef2-110">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="10ef2-110">Default is **True**.</span></span>  
  
## <a name="configuring-the-sql-adapter-behavior"></a><span data-ttu-id="10ef2-111">SQL アダプターの動作を構成します。</span><span class="sxs-lookup"><span data-stu-id="10ef2-111">Configuring the SQL Adapter Behavior</span></span>  
 <span data-ttu-id="10ef2-112">アプローチのいずれか、メタデータの生成中に、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10ef2-112">For either of the approaches, you do not need to perform any specific tasks while generating metadata or while configuring the BizTalk application.</span></span> <span data-ttu-id="10ef2-113">のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または WCF SQL の受信場所にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="10ef2-113">You only need to set the **NotifyOnListenerStart** binding property accordingly on the WCF-Custom or WCF-SQL receive location.</span></span> <span data-ttu-id="10ef2-114">BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信クエリ通知増分 BizTalk Server を使用して SQL から](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="10ef2-114">To create the BizTalk application, you must perform the same set of tasks as described in [Receive Query Notifications Incrementally from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-incrementally-from-sql-using-biztalk-server.md).</span></span> <span data-ttu-id="10ef2-115">ただし、BizTalk アプリケーションを使用して、構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を変更しようとすることができます、 **NotifyOnListenerStart** binding プロパティと、2 つの構成の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="10ef2-115">However, when configuring the BizTalk application using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can try changing the value of the **NotifyOnListenerStart** binding property and see the difference in the two configurations.</span></span>  
  
 <span data-ttu-id="10ef2-116">次の図は、通知の値に基づいて受信方法を示しています、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="10ef2-116">The following figure demonstrates how the notifications are received based on the value of the **NotifyOnListenerStart** binding property.</span></span>  
  
 <span data-ttu-id="10ef2-117">![通知の SQL アダプターを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span><span class="sxs-lookup"><span data-stu-id="10ef2-117">![Configure SQL Adapter for notifications](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span></span>  
  
 <span data-ttu-id="10ef2-118">最初のシナリオでは、ことに注意してくださいときに、 **NotifyOnListenerStart**に設定されている**true**受信場所がダウンしたときに、データベース テーブルにレコードを挿入、アダプターにのみ送信すると、。通知メッセージ受信場所が戻ったときにします。</span><span class="sxs-lookup"><span data-stu-id="10ef2-118">Note that in the first scenario, when the **NotifyOnListenerStart** is set to **true** and records are inserted into the database table while the receive location was down, the adapter only sends you a notification message when the receive location comes back up.</span></span> <span data-ttu-id="10ef2-119">アダプター受信場所が停止していた間に挿入されたレコードを処理する任意の操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="10ef2-119">The adapter does not perform any operation to process the records that were inserted while the receive location was down.</span></span> <span data-ttu-id="10ef2-120">アダプター クライアントは、受信場所が停止していた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ef2-120">The adapter client must implement the relevant logic in their application to process the records that were inserted while the receive location was down.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ef2-121">参照</span><span class="sxs-lookup"><span data-stu-id="10ef2-121">See Also</span></span>  
 [<span data-ttu-id="10ef2-122">BizTalk Server を使用して SQL クエリ通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="10ef2-122">Receive SQL Query Notifications using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)