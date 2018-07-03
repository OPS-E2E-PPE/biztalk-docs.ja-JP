---
title: 受信場所のブレーク ダウン後の Oracle データベース変更通知の受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22ad6da2-2979-4158-b1d1-d54095223af9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96e10d45158dc3ce1f07032a182ce8088f90ac92
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988235"
---
# <a name="receive-oracle-database-change-notifications-after-a-receive-location-breakdown"></a><span data-ttu-id="4a45b-102">受信場所のブレーク ダウン後に、Oracle データベース変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-102">Receive Oracle Database change notifications after a receive location breakdown</span></span>
<span data-ttu-id="4a45b-103">ACCOUNTACTIVITY テーブルに変更されたときに、データベース変更通知のメッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4a45b-103">Consider a scenario where you have a BizTalk application that receives database change notification messages when changes are made to the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="4a45b-104">一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割し同時に ACCOUNTACTIVITY テーブルにレコードが追加、最近追加されたレコードの通知は受け取りません。</span><span class="sxs-lookup"><span data-stu-id="4a45b-104">If the receive location configured as part of the BizTalk application breaks down, and simultaneously records are added into the ACCOUNTACTIVITY table, you will not receive notifications for the recently added records.</span></span> <span data-ttu-id="4a45b-105">わからない、受信場所が再度使用可能です。</span><span class="sxs-lookup"><span data-stu-id="4a45b-105">You will also not know when the receive location is available again.</span></span> <span data-ttu-id="4a45b-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを公開します**NotifyOnListenerStart**、受信場所が回復した通知を受け取る構成できます。</span><span class="sxs-lookup"><span data-stu-id="4a45b-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes a binding property, **NotifyOnListenerStart**, that you can configure to get a notification that the receive location has recovered.</span></span> <span data-ttu-id="4a45b-107">次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4a45b-107">You can specify the following values for the **NotifyOnListenerStart** binding property:</span></span>  
  
- <span data-ttu-id="4a45b-108">このプロパティを設定**True**、受信場所に回復するとすぐに受信場所が使用可能な通知の通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-108">Set this property to **True**, to receive a notification informing that the receive location is available, as soon as the receive location recovers.</span></span>  
  
- <span data-ttu-id="4a45b-109">このプロパティを設定**False**、受信場所が回復、受信場所の回復後通知通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="4a45b-109">Set this property to **False**, to not receive a notification informing that the receive location has recovered, after the receive location recovers.</span></span>  
  
  <span data-ttu-id="4a45b-110">既定値は**True**します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-110">Default is **True**.</span></span>  
  
## <a name="configuring-the-oracle-database-adapter-behavior"></a><span data-ttu-id="4a45b-111">Oracle データベース アダプターの動作を構成します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-111">Configuring the Oracle Database Adapter Behavior</span></span>  
 <span data-ttu-id="4a45b-112">いずれの方法には、メタデータを生成するときに、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4a45b-112">For either of the approaches, you do not need to perform any specific tasks while generating metadata or while configuring the BizTalk application.</span></span> <span data-ttu-id="4a45b-113">のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または Wcf-oracledb で受信場所にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4a45b-113">You only need to set the **NotifyOnListenerStart** binding property accordingly on the WCF-Custom or WCF-OracleDB receive location.</span></span> <span data-ttu-id="4a45b-114">BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信 Oracle データベース変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-114">To create the BizTalk application, you must perform the same set of tasks as described in [Receiving Oracle Database Change Notifications Incrementally Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md).</span></span> <span data-ttu-id="4a45b-115">ただし、使用して BizTalk アプリケーションを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を変更するをお試しください**NotifyOnListenerStart**プロパティをバインドし、2 つの構成の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a45b-115">However, when configuring the BizTalk application using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can try changing the value of **NotifyOnListenerStart** binding property and see the difference in the two configurations.</span></span>  
  
 <span data-ttu-id="4a45b-116">次の図は、通知の値に基づいて受信方法を示して、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4a45b-116">The following figure demonstrates how the notifications are received based on the value of the **NotifyOnListenerStart** binding property.</span></span>  
  
 <span data-ttu-id="4a45b-117">![通知の SQL アダプターを構成](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span><span class="sxs-lookup"><span data-stu-id="4a45b-117">![Configure SQL Adapter for notifications](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span></span>  
  
 <span data-ttu-id="4a45b-118">最初のシナリオで注意ときに、 **NotifyOnListenerStart**に設定されている**True**レコードがデータベース テーブルに挿入されるは、受信場所がダウンしていたときに、アダプターにのみ送信すると、受信場所が動作するときの通知メッセージです。</span><span class="sxs-lookup"><span data-stu-id="4a45b-118">Note that in the first scenario, when the **NotifyOnListenerStart** is set to **True** and records are inserted into the database table while the receive location was down, the adapter only sends you a notification message when the receive location comes up.</span></span> <span data-ttu-id="4a45b-119">アダプターでは、受信場所がダウンしていた間に挿入されたレコードを処理する操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="4a45b-119">The adapter does not perform any operation to process the records that were inserted while the receive location was down.</span></span> <span data-ttu-id="4a45b-120">アダプターのクライアントは、受信場所がダウンしていた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a45b-120">The adapter client must implement the relevant logic in their application to process the records that were inserted while the receive location was down.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a45b-121">参照</span><span class="sxs-lookup"><span data-stu-id="4a45b-121">See Also</span></span>  
 [<span data-ttu-id="4a45b-122">BizTalk Server を使用して Oracle データベースの変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="4a45b-122">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)