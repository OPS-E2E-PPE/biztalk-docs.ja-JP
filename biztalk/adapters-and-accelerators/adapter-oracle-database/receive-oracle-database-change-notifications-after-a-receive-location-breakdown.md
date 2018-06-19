---
title: 受信場所のブレーク ダウンの後に Oracle データベースの変更通知を受け取る |Microsoft ドキュメント
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
ms.openlocfilehash: 3f20fdcd30362a87a49be17d061a9fe86595c78c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214090"
---
# <a name="receive-oracle-database-change-notifications-after-a-receive-location-breakdown"></a><span data-ttu-id="586d5-102">受信場所のブレーク ダウンの後に Oracle データベースの変更通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="586d5-102">Receive Oracle Database change notifications after a receive location breakdown</span></span>
<span data-ttu-id="586d5-103">ACCOUNTACTIVITY テーブルへの変更が加えられたときに、データベース変更の通知メッセージを受信する BizTalk アプリケーションが存在するシナリオを検討してください。</span><span class="sxs-lookup"><span data-stu-id="586d5-103">Consider a scenario where you have a BizTalk application that receives database change notification messages when changes are made to the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="586d5-104">一部として、受信場所が構成されている場合、BizTalk アプリケーションが分割すると、同時に ACCOUNTACTIVITY テーブルにレコードを追加、最近追加されたレコードの通知を受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="586d5-104">If the receive location configured as part of the BizTalk application breaks down, and simultaneously records are added into the ACCOUNTACTIVITY table, you will not receive notifications for the recently added records.</span></span> <span data-ttu-id="586d5-105">わからない場合、受信場所が再び使用可能。</span><span class="sxs-lookup"><span data-stu-id="586d5-105">You will also not know when the receive location is available again.</span></span> <span data-ttu-id="586d5-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド プロパティを公開**NotifyOnListenerStart**、されるを取得する通知が受信場所の回復を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="586d5-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes a binding property, **NotifyOnListenerStart**, that you can configure to get a notification that the receive location has recovered.</span></span> <span data-ttu-id="586d5-107">次の値を指定することができます、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="586d5-107">You can specify the following values for the **NotifyOnListenerStart** binding property:</span></span>  
  
-   <span data-ttu-id="586d5-108">このプロパティを設定**True**、受信場所が使用できる、受信場所を復旧するとすぐに知らせる通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="586d5-108">Set this property to **True**, to receive a notification informing that the receive location is available, as soon as the receive location recovers.</span></span>  
  
-   <span data-ttu-id="586d5-109">このプロパティを設定**False**、受信場所が復旧されると、受信場所の回復後通知通知を受信しません。</span><span class="sxs-lookup"><span data-stu-id="586d5-109">Set this property to **False**, to not receive a notification informing that the receive location has recovered, after the receive location recovers.</span></span>  
  
 <span data-ttu-id="586d5-110">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="586d5-110">Default is **True**.</span></span>  
  
## <a name="configuring-the-oracle-database-adapter-behavior"></a><span data-ttu-id="586d5-111">Oracle データベース アダプターの動作を構成します。</span><span class="sxs-lookup"><span data-stu-id="586d5-111">Configuring the Oracle Database Adapter Behavior</span></span>  
 <span data-ttu-id="586d5-112">アプローチのいずれか、メタデータの生成中に、または BizTalk アプリケーションを構成するときに、特定のタスクを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="586d5-112">For either of the approaches, you do not need to perform any specific tasks while generating metadata or while configuring the BizTalk application.</span></span> <span data-ttu-id="586d5-113">のみを設定する必要があります、 **NotifyOnListenerStart**適宜 Wcf-custom または Wcf-oracledb で受信場所にプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="586d5-113">You only need to set the **NotifyOnListenerStart** binding property accordingly on the WCF-Custom or WCF-OracleDB receive location.</span></span> <span data-ttu-id="586d5-114">BizTalk アプリケーションを作成する」の説明に従って、同じ一連のタスクを実行する必要があります[受信 Oracle データベースの変更通知増分を使用して BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="586d5-114">To create the BizTalk application, you must perform the same set of tasks as described in [Receiving Oracle Database Change Notifications Incrementally Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-incrementally-using-biztalk-server.md).</span></span> <span data-ttu-id="586d5-115">ただし、BizTalk アプリケーションを使用して、構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]の値を変更しようとすることができます**NotifyOnListenerStart** binding プロパティと、2 つの構成の違いを確認します。</span><span class="sxs-lookup"><span data-stu-id="586d5-115">However, when configuring the BizTalk application using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you can try changing the value of **NotifyOnListenerStart** binding property and see the difference in the two configurations.</span></span>  
  
 <span data-ttu-id="586d5-116">次の図は、通知の値に基づいて受信方法を示しています、 **NotifyOnListenerStart**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="586d5-116">The following figure demonstrates how the notifications are received based on the value of the **NotifyOnListenerStart** binding property.</span></span>  
  
 <span data-ttu-id="586d5-117">![通知の SQL アダプターを構成する](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span><span class="sxs-lookup"><span data-stu-id="586d5-117">![Configure SQL Adapter for notifications](../../adapters-and-accelerators/adapter-oracle-database/media/4018300a-1a58-47da-ac9d-c77c13d7081d.gif "4018300a-1a58-47da-ac9d-c77c13d7081d")</span></span>  
  
 <span data-ttu-id="586d5-118">最初のシナリオでは、ことに注意してくださいときに、 **NotifyOnListenerStart**に設定されている**True**受信場所がダウンしたときに、データベース テーブルにレコードを挿入、アダプターにのみ送信すると、。受信場所が表示されたら、メッセージを通知します。</span><span class="sxs-lookup"><span data-stu-id="586d5-118">Note that in the first scenario, when the **NotifyOnListenerStart** is set to **True** and records are inserted into the database table while the receive location was down, the adapter only sends you a notification message when the receive location comes up.</span></span> <span data-ttu-id="586d5-119">アダプター受信場所が停止していた間に挿入されたレコードを処理する任意の操作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="586d5-119">The adapter does not perform any operation to process the records that were inserted while the receive location was down.</span></span> <span data-ttu-id="586d5-120">アダプター クライアントは、受信場所が停止していた間に挿入されたレコードを処理するには、そのアプリケーション内で関連するロジックを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="586d5-120">The adapter client must implement the relevant logic in their application to process the records that were inserted while the receive location was down.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586d5-121">参照</span><span class="sxs-lookup"><span data-stu-id="586d5-121">See Also</span></span>  
 [<span data-ttu-id="586d5-122">BizTalk Server を使用して Oracle データベースの変更通知を受け取る</span><span class="sxs-lookup"><span data-stu-id="586d5-122">Receiving Oracle Database Change Notifications Using BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-oracle-database-change-notifications-using-biztalk-server.md)