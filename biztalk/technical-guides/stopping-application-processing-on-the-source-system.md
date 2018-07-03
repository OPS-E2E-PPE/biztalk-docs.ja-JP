---
title: アプリケーション ソース システムの処理の停止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde5fc62-4bc2-4ef0-81bc-c7d39ff36cb6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c92fe07371be2abb44c314eb77eb38c6c853bebe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982459"
---
# <a name="stopping-application-processing-on-the-source-system"></a>ソース システムで処理するアプリケーションを停止しています
ときにアプリケーションの処理を停止するか、ソース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム サーバーに既存のデータベース サーバーを使用してドキュメントの処理に参加することはできます。 このシナリオでアクティビティを処理する必要があります停止するため、整合性の復元操作を行うことができます。  
  
 ソース システム上でアプリケーションの処理を停止するには、接続は運用環境の間で開かれていないことを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューターと[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 運用環境でアプリケーションの処理を停止する次の手順に従って[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイム コンピューター。  
  
1. すべての受信場所を無効にする、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk グループ内のコンピューター。 すべてのメモを受信できるように、これらの受信場所を無効になっている場所は再度有効にする後でします。 停止します。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]から受信メッセージを処理します。  
  
2. すべてのホスト インスタンスで実行されているを停止、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内のコンピューター。 これから実行できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 これらのホスト インスタンスを後で再開できるようにが停止していたすべてのホスト インスタンスをメモしておきます。  
  
3. すべて停止[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]エージェント ジョブに関連する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。  
  
4. BAM を使用している場合は、すべての BAM キューブ更新およびデータ保守 SSIS パッケージを無効にします。 これを使用して行うことができます[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。  
  
5. Analysis Services を停止、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 MSSQLServerOLAPService のすべてのインスタンスを停止することでこれは、 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services がインストールされているコンピューター。  
  
6. その他の停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスで実行されているサービス マネージャーで、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  グループで、エンタープライズ シングル サインオン サービスや、ルール エンジン更新サービスなどのコンピューター。 後で再起動するように停止しているサービスをメモしておきます。  
  
7. 接続するすべてのアプリケーションを閉じて、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 インタンスを含む、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]、その他の BizTalk アプリケーションがインストールされているとします。  
  
8. によって生成されたデータベースのアクティビティがないことを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio に接続しているどのようなプロセスを表示する、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 これを行う展開**管理** をダブルクリックして**の利用状況モニター**で[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。 クリックして選択し、**プロセス情報**します。 また、システム ストアド プロシージャを使用して、 **sp_who**または**sp_who2**への開いている接続を識別するために、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース。 接続されているすべてのプロセスがある場合は、それらを検索し、それらを通常; 終了内の各プロセスを右クリックし、最後の手段として、または、**プロセス情報**ウィンドウ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio をクリックします**プロセスを強制終了**接続を終了します。  
  
9. その他のデータベースの処理は、アプリケーション データベースで発生する可能性が。 これらのデータベースが復元される場合は、すべての処理が停止したことを確認します。  
  
## <a name="see-also"></a>参照  
 [BizTalk グループの復元](../technical-guides/restoring-the-biztalk-group.md)