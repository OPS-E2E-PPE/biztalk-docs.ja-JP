---
title: "ソース システムで処理するアプリケーションを停止しています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde5fc62-4bc2-4ef0-81bc-c7d39ff36cb6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe980e3f29e2bd4cf13aa2b74a1923126fcec2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="stopping-application-processing-on-the-source-system"></a>ソース システムで処理するアプリケーションを停止しています
ときにアプリケーションの処理を停止するか、ソース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーの既存のデータベース サーバーを使用してドキュメントの処理に参加することはできます。 このシナリオでアクティビティを処理する必要があります停止整合性の復元操作を完了できるようにします。  
  
 停止するアプリケーションの処理、送信元システムで接続が、運用環境間で開かれてないことを確認してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 運用環境でアプリケーションの処理を停止する次の手順に従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。  
  
1.  すべての受信場所を無効にする、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループ内のコンピューター。 すべてのメモを受信できるように、これらの受信場所を無効になっている場所を再度有効にする以降。 これが停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]から受信メッセージを処理します。  
  
2.  すべてのホスト インスタンスで実行されているを停止、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内のコンピューター。 これから、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 これらのホスト インスタンスを後で再開できるように停止したすべてのホスト インスタンスをメモしておきます。  
  
3.  すべて停止[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]に関連するエージェント ジョブ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
4.  BAM を使用している場合は、すべての BAM キューブ更新およびデータ保守 SSIS パッケージを無効にします。 使用してこれ行う[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。  
  
5.  Analysis Services を停止、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 MSSQLServerOLAPService のすべてのインスタンスを停止することによってこれ行う、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services がインストールされているコンピューター。  
  
6.  その他の停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスで実行されているサービス マネージャーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンタープライズ シングル サインオン サービスや、ルール エンジン更新サービスなどのグループ内のコンピューター。 サービスが停止しているは、後で再起動するようにをメモしておきます。  
  
7.  アプリケーションへの接続をすべて閉じて、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 インスタンスを含むこの、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]、その他の BizTalk アプリケーションがインストールされているとします。  
  
8.  によって生成されたデータベース アクティビティがないことを確認してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 使用して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio に接続しているどのようなプロセスを表示する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 展開してこれ行う**管理** をダブルクリックして**利用状況モニター**で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。 クリックして選択し、**プロセス情報**です。 または、システム ストアド プロシージャを使用して**sp_who**または**sp_who2**に任意の開いている接続を識別する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納するコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 接続されているすべてのプロセスがある場合は、それらを見つけて終了することが追加されます。内の各プロセスを右クリックし、最後の手段として、または、**プロセス情報**ペインで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio およびクリック**プロセスを強制終了**接続を終了します。  
  
9. その他のデータベースの処理は、アプリケーション データベースで発生する可能性がします。 これらのデータベースが復元される場合は、すべての処理が停止していることを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk グループを復元します。](../technical-guides/restoring-the-biztalk-group.md)