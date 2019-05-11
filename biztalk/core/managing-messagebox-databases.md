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
# <a name="managing-messagebox-databases"></a>メッセージ ボックス データベースの管理
メッセージ ボックス データベースには、3 つの重要な機能が備わっています。 サブスクリプションを保存し、サブスクリプションに一致するサービスに、メッセージを配信する追跡情報。 メッセージ ボックス データベースは、各 BizTalk ホストのキューおよび状態テーブルを格納するホスト プラットフォームです。 メッセージ ボックス データベースには、メッセージおよびメッセージ プロパティも格納されます。  
  
 メッセージ ボックス データベースが環境内で露出度の危険度の高い資産である場合は、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用して制限して、メッセージ ボックス データベースとの通信をセキュリティで保護することをお勧めします。  
  
 Windows Server 2003 を使用する場合は、メッセージ ボックス データベースでの分散トランザクション コーディネーター (DTC) を有効にする必要があります。 また、複数コンピューター展開のネットワーク クライアントを有効にする必要があります。 詳細については、次を参照してください。[管理サーバーのポート](../core/ports-for-the-administration-server.md)します。  
  
 このセクションには、環境内でのメッセージ ボックス データベースの管理の手順に関する情報が含まれています。 メッセージ ボックス データベースとサブスクリプションの概念については、Microsoft をモデル化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージを処理するために使用を参照してください[、メッセージ ボックス データベース](../core/the-messagebox-database.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [新しいメッセージ ボックス データベースを追加する方法](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)  
  
-   [メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md)