---
title: "既知の問題のインストール、構成、および展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda1bd5c8167bbf9f6049b3620c0c949950b1e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a>インストール、構成、および展開での既知の問題
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a>一部の BizTalk EDI/AS2 アイテムが構成解除した後もアクティブになっている  
  
##### <a name="problem"></a>Problem  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BizTalk EDI/AS2 機能を構成解除した後、EDI 処理および AS2 処理に関連する一部の BizTalk Server アイテムが、BizTalk グループ構成のコンテキストにおいてアクティブのままとなります。 これらのアイテムには、EDI パイプライン、AS2 パイプライン、バッチ処理オーケストレーションなどがあります。 このため、BizTalk EDI/AS2 機能を構成解除した後でも、基本的な EDI 処理および AS2 処理を実行できます。  
  
##### <a name="cause"></a>原因  
 EDI 処理および AS2 処理に関連付けられているアクティブなポートがあります。 一部のアイテムは、これらのポートがアクティブである間は、引き続き機能します。  
  
##### <a name="resolution"></a>解決方法  
 すべての EDI/AS2 アイテムを無効にするには、EDI 処理および AS2 処理に関連付けられているポートを無効化、停止、または削除する必要があります。  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a>BizTalk Server を構成した後に BizTalk Server のコンピューターまたは SQL Server のコンピューターの名前を変更すると、構成ウィザードが失敗する  
  
##### <a name="problem"></a>Problem  
 この問題は、次のようにさまざまなケースで生じることがあります。  
  
-   BizTalk Server 構成で概要ページを正しく読み込むことができましたが、機能を構成しようとすると、画面に機能オプションが表示されません。  
  
-   構成ウィザードが SQL Server に接続できません。  
  
-   すべての構成を解除しようとすると、一部の機能は解除されますが、すべての機能は解除されません。  
  
##### <a name="cause"></a>原因  
 BizTalk Server の構成では、コンピューターのネットワーク名を格納します。 BizTalk Server 構成のコンピューターの名前が変更されると、構成ウィザードは BizTalk Server を特定できなくなります。 BizTalk Server を構成した後に SQL Server コンピューターの名前を変更する場合も、同様の問題が発生します。  
  
##### <a name="resolution"></a>解決方法  
 BizTalk Server コンピューターまたは SQL Server コンピューターの名前を変更しないでください。 サーバーの名前を変更する必要がある場合は、コンピューターの名前を変更する前に、すべての BizTalk 機能の構成を解除します。 コンピューターの名前を変更してから、BizTalk Server の機能を再構成してください。  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a>BizTalk Server のビジネス ルール構成ウィザードが失敗する  
  
### <a name="problem"></a>Problem  
  
-   ビジネス ルール構成ウィザードが "一部のコンポーネントの構成に失敗しました。それらのコンポーネントにはどの設定も適用されませんでした" というエラーで失敗します。  
  
-   BizTalk Server コンピューターにビジネス ルール エンジンが既に正常に構成されている場合、ルール エンジン更新サービスの開始は失敗し、手動で開始することはできません。  
  
 この問題が発生した場合は、BizTalk Server コンピューターのアプリケーション ログに次のようなエラーが生成されることがあります。  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a>原因  
 マイクロソフト マルウェア対応センターは、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威の可能性に対処するために、更新されたシグネチャ ファイルを公開しました。 この更新されたシグネチャ ファイルにより、SettingsModifier:Win32/PossibleHostsFileHijack からの脅威を緩和するために、Windows Defender などのソフトウェアでローカル HOSTS ファイルが更新されます。 これらの変更の結果、BizTalk Server ルール エンジン更新サービスが正常に開始できない場合があります。  
  
### <a name="resolution"></a>解決方法  
 ローカル HOSTS ファイルを更新して次の行を追加してください。  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリにあります。  
  
> [!NOTE]
>  SettingsModifier:Win32/PossibleHostsFileHijack によって生じる可能性がある脅威に対処する、Microsoft マルウェア プロテクション センターの署名更新の詳細については、[http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221) を参照してください。  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a>GAC/Mgmt db に参照アセンブリが見つからない場合、オーケストレーションの参加に失敗する  
  
##### <a name="problem"></a>Problem  
 GAC/Mgmt db に参照 (オーケストレーションで参照される C# アセンブリ) が見つからない場合、オーケストレーションの参加に失敗します。 再展開中に、既存の状態に基づいたオーケストレーションの参加が必要になることがあります。 参照が見つからないと、展開も失敗します。  
  
##### <a name="cause"></a>原因  
 GAC/Mgmt db に参照アセンブリが見つかりません。  
  
##### <a name="resolution"></a>解決方法  
 オーケストレーションの参加時に Mgmt db に格納された参照アセンブリにアクセスできるように、参照アセンブリを GAC に追加するか、リソースとして追加します。  

## <a name="community-blog-biztalk-2013-r2-bugs-issues--quirks"></a>コミュニティ ブログ: BizTalk 2013 R2 のバグ、問題、変わった現象

[BizTalk Server 2013 R2 の既知のバグ、問題、変わった現象](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a>構成に関するその他のトピック  
  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)  
  
 [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [BizTalk Server のクラスター構成](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [BizTalk Server の安全な展開](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  