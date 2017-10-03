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
# <a name="managing-messagebox-databases"></a>メッセージ ボックス データベースの管理
メッセージ ボックス データベースには 3 つの重要な役割があります。 1 つ目は、サブスクリプションと追跡情報を格納し、サブスクリプションと一致するサービスにメッセージを配信することです。 2 つ目は、各 BizTalk ホストのキューと状態テーブルを格納するホスト プラットフォームとして機能することです。 そして、3 つ目は、メッセージやメッセージ プロパティを格納することです。  
  
 メッセージ ボックス データベースが環境内でリスクの度合いの高い資産である場合は、インターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用して、メッセージ ボックス データベースとの通信を制限し、セキュリティで保護することをお勧めします。  
  
 Windows Server 2003 を使用する場合、メッセージ ボックス データベースで、分散データ トランザクション コーディネーター (DTC) を有効にする必要があります。 また、複数コンピューター展開ではネットワーク クライアントも有効にする必要があります。 詳細については、次を参照してください。[管理サーバーのポート](../core/ports-for-the-administration-server.md)です。  
  
 このセクションでは、環境内のメッセージ ボックス データベースを管理するための操作手順について説明します。 Microsoft のモデルの概要については、メッセージ ボックス データベースおよびサブスクリプション[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、メッセージの処理に使用するを参照してください[、メッセージ ボックス データベース](../core/the-messagebox-database.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [新しいメッセージ ボックス データベースを追加する方法](../core/how-to-add-a-new-messagebox-database.md)  
  
-   [新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md)  
  
-   [メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md)