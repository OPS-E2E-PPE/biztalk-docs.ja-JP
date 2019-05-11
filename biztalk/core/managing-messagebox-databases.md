---
title: メッセージ ボックス データベースの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [MessageBox database], about managing MessageBox database
- managing [MessageBox database]
- MessageBox database, managing
ms.assetid: 9675b5d5-7a69-468d-be42-34a72cd6e5c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75dc3bdcd2d30eb7f8b0f5604d3e7e61cc54de59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380349"
---
# <a name="managing-messagebox-databases"></a><span data-ttu-id="ec7cb-102">メッセージ ボックス データベースの管理</span><span class="sxs-lookup"><span data-stu-id="ec7cb-102">Managing MessageBox Databases</span></span>
<span data-ttu-id="ec7cb-103">メッセージ ボックス データベースには、3 つの重要な機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-103">The MessageBox database has three essential functions.</span></span> <span data-ttu-id="ec7cb-104">サブスクリプションを保存し、サブスクリプションに一致するサービスに、メッセージを配信する追跡情報。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-104">It stores subscriptions and tracking information and it delivers the messages to the services that match the subscriptions.</span></span> <span data-ttu-id="ec7cb-105">メッセージ ボックス データベースは、各 BizTalk ホストのキューおよび状態テーブルを格納するホスト プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-105">The MessageBox database is a host platform that stores the queues and state tables for each BizTalk Host.</span></span> <span data-ttu-id="ec7cb-106">メッセージ ボックス データベースには、メッセージおよびメッセージ プロパティも格納されます。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-106">The MessageBox database also stores messages and message properties.</span></span>  
  
 <span data-ttu-id="ec7cb-107">メッセージ ボックス データベースが環境内で露出度の危険度の高い資産である場合は、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用して制限して、メッセージ ボックス データベースとの通信をセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-107">If the MessageBox databases are an asset with high-risk exposure in your environment, we recommend that you use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to restrict and secure communication to and from the MessageBox databases.</span></span>  
  
 <span data-ttu-id="ec7cb-108">Windows Server 2003 を使用する場合は、メッセージ ボックス データベースでの分散トランザクション コーディネーター (DTC) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-108">If you use Windows Server 2003, you must enable the distributed transaction coordinator (DTC) on the MessageBox database.</span></span> <span data-ttu-id="ec7cb-109">また、複数コンピューター展開のネットワーク クライアントを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-109">You must also enable network clients for multicomputer deployments.</span></span> <span data-ttu-id="ec7cb-110">詳細については、次を参照してください。[管理サーバーのポート](../core/ports-for-the-administration-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-110">For more information, see [Ports for the Administration Server](../core/ports-for-the-administration-server.md).</span></span>  
  
 <span data-ttu-id="ec7cb-111">このセクションには、環境内でのメッセージ ボックス データベースの管理の手順に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-111">This section contains procedural information about managing MessageBox databases in your environment.</span></span> <span data-ttu-id="ec7cb-112">メッセージ ボックス データベースとサブスクリプションの概念については、Microsoft をモデル化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを処理するために使用を参照してください[、メッセージ ボックス データベース](../core/the-messagebox-database.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec7cb-112">For conceptual information about MessageBox databases and the subscription model Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses to process messages, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec7cb-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ec7cb-113">In This Section</span></span>  
  
-   [<span data-ttu-id="ec7cb-114">新しいメッセージ ボックス データベースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="ec7cb-114">How to Add a New MessageBox Database</span></span>](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [<span data-ttu-id="ec7cb-115">新しいメッセージの公開を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="ec7cb-115">How to Disable New Message Publication</span></span>](../core/how-to-disable-new-message-publication.md)  
  
-   [<span data-ttu-id="ec7cb-116">メッセージ ボックス データベースを削除する方法</span><span class="sxs-lookup"><span data-stu-id="ec7cb-116">How to Delete a MessageBox Database</span></span>](../core/how-to-delete-a-messagebox-database.md)