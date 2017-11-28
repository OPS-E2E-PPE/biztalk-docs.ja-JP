---
title: "メッセージ ボックス データベースの管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e854ad0f7014de8241f8a7b6af6addd49cb4da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-messagebox-databases"></a><span data-ttu-id="830f5-102">メッセージ ボックス データベースの管理</span><span class="sxs-lookup"><span data-stu-id="830f5-102">Managing MessageBox Databases</span></span>
<span data-ttu-id="830f5-103">メッセージ ボックス データベースには 3 つの重要な役割があります。</span><span class="sxs-lookup"><span data-stu-id="830f5-103">The MessageBox database has three essential functions.</span></span> <span data-ttu-id="830f5-104">1 つ目は、サブスクリプションと追跡情報を格納し、サブスクリプションと一致するサービスにメッセージを配信することです。</span><span class="sxs-lookup"><span data-stu-id="830f5-104">It stores subscriptions and tracking information and it delivers the messages to the services that match the subscriptions.</span></span> <span data-ttu-id="830f5-105">2 つ目は、各 BizTalk ホストのキューと状態テーブルを格納するホスト プラットフォームとして機能することです。</span><span class="sxs-lookup"><span data-stu-id="830f5-105">The MessageBox database is a host platform that stores the queues and state tables for each BizTalk Host.</span></span> <span data-ttu-id="830f5-106">そして、3 つ目は、メッセージやメッセージ プロパティを格納することです。</span><span class="sxs-lookup"><span data-stu-id="830f5-106">The MessageBox database also stores messages and message properties.</span></span>  
  
 <span data-ttu-id="830f5-107">メッセージ ボックス データベースが環境内でリスクの度合いの高い資産である場合は、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用して、メッセージ ボックス データベースとの通信を制限し、セキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="830f5-107">If the MessageBox databases are an asset with high-risk exposure in your environment, we recommend that you use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to restrict and secure communication to and from the MessageBox databases.</span></span>  
  
 <span data-ttu-id="830f5-108">Windows Server 2003 を使用する場合、メッセージ ボックス データベースで、分散データ トランザクション コーディネーター (DTC) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="830f5-108">If you use Windows Server 2003, you must enable the distributed transaction coordinator (DTC) on the MessageBox database.</span></span> <span data-ttu-id="830f5-109">また、複数コンピューター展開ではネットワーク クライアントも有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="830f5-109">You must also enable network clients for multicomputer deployments.</span></span> <span data-ttu-id="830f5-110">詳細については、次を参照してください。[管理サーバーのポート](../core/ports-for-the-administration-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="830f5-110">For more information, see [Ports for the Administration Server](../core/ports-for-the-administration-server.md).</span></span>  
  
 <span data-ttu-id="830f5-111">このセクションでは、環境内のメッセージ ボックス データベースを管理するための操作手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="830f5-111">This section contains procedural information about managing MessageBox databases in your environment.</span></span> <span data-ttu-id="830f5-112">Microsoft のモデルの概要については、メッセージ ボックス データベースおよびサブスクリプション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、メッセージの処理に使用するを参照してください[、メッセージ ボックス データベース](../core/the-messagebox-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="830f5-112">For conceptual information about MessageBox databases and the subscription model Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process messages, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="830f5-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="830f5-113">In This Section</span></span>  
  
-   [<span data-ttu-id="830f5-114">新しいメッセージ ボックス データベースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="830f5-114">How to Add a New MessageBox Database</span></span>](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [<span data-ttu-id="830f5-115">新しいメッセージの公開を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="830f5-115">How to Disable New Message Publication</span></span>](../core/how-to-disable-new-message-publication.md)  
  
-   [<span data-ttu-id="830f5-116">メッセージ ボックス データベースを削除する方法</span><span class="sxs-lookup"><span data-stu-id="830f5-116">How to Delete a MessageBox Database</span></span>](../core/how-to-delete-a-messagebox-database.md)