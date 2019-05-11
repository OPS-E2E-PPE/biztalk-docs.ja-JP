---
title: 既知の問題は、インストール、構成、および展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1c08eb-d647-4a4a-b9a3-c4d84e8d4b82
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 040b1921228608deddb3e950613f447d984121c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266205"
---
# <a name="known-issues-in-installation-configuration-and-deployment"></a>インストール、構成、および展開に関する既知の問題
## <a name="some-biztalk-edias2-artifacts-are-still-active-after-unconfiguring"></a>構成解除した後、一部の BizTalk edi/as2 アイテムがまだアクティブ  
  
##### <a name="problem"></a>問題  
 BizTalk edi/as2 機能を構成解除した後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、EDI および AS2 処理に関連する一部の BizTalk Server アイテムを BizTalk グループの構成のコンテキストでアクティブにすることができます。 これらの成果物には、EDI および AS2 のパイプラインとバッチ処理オーケストレーションが含まれます。 その結果、BizTalk edi/as2 機能を構成解除した後でも、基本的な EDI および AS2 処理を実行することができます。  
  
##### <a name="cause"></a>原因  
 EDI および AS2 処理に関連付けられているアクティブなポートがあります。 一部のアイテムは引き続きこれらのポートをアクティブにしたままに機能します。  
  
##### <a name="resolution"></a>解決策  
 すべての edi/as2 アイテムを無効にするを無効にし、停止、または EDI および AS2 処理に関連付けられているポートを削除する必要があります。  
  
## <a name="if-the-biztalk-server-computer-or-sql-server-computer-is-renamed-after-biztalk-server-configuration-the-configuration-wizard-will-fail"></a>BizTalk Server の構成後、BizTalk Server コンピューターまたは SQL Server コンピューターの名前が変更、構成ウィザードが失敗します。  
  
##### <a name="problem"></a>問題  
 この問題は、いくつかの方法で問題を発生可能性があります。  
  
-   BizTalk Server の構成が [概要] ページを正しく読み込むが、画面に機能を構成しようとしています。 機能のオプションは表示されません。  
  
-   構成ウィザードは、SQL Server に接続できません。  
  
-   すべてではなく、一部の機能の構成を解除するすべての構成を解除しようとしています。  
  
##### <a name="cause"></a>原因  
 BizTalk Server の構成では、コンピューターのネットワーク名を格納します。 コンピューターの名前変更は、BizTalk Server の構成と構成ウィザードは、BizTalk Server を特定できなくなります。 SQL Server コンピューターの名前が変更された後、BizTalk Server が構成されている場合、同様の問題が発生します。  
  
##### <a name="resolution"></a>解決策  
 BizTalk Server コンピューター、または SQL Server コンピューターに名前を変更できません。 場合は、サーバーの名前を変更する必要があります、コンピューターの名前を変更する前にすべての BizTalk 機能の構成を解除します。 コンピューターの名前を変更するには後、は、BizTalk Server の機能を再構成します。  
  
## <a name="the-biztalk-server-business-rules-configuration-wizard-fails"></a>BizTalk Server ビジネス ルール構成ウィザードが失敗しました。  
  
### <a name="problem"></a>問題  
  
- ビジネス ルールの構成ウィザードは、「一部のコンポーネントの構成に失敗しましたし、それらのコンポーネントの設定は適用されませんでした」エラーで失敗します。  
  
- 対象のビジネス ルール エンジンが既に正常に構成されて、BizTalk サーバー コンピューターには、ルール エンジン更新サービスは開始に失敗し、手動で開始することはできません。  
  
  この問題が発生したときに、BizTalk Server コンピューターのアプリケーション ログには、次のようなエラーを生成可能性があります。  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
### <a name="cause"></a>原因  
 Microsoft マルウェア プロテクション センター SettingsModifier:Win32 から潜在的な脅威に対処するための更新されたシグネチャ ファイルをリリースする/公開しました。 この更新されたシグネチャ ファイル SettingsModifier:Win32 からの脅威を軽減するためにローカルの HOSTS ファイルを更新する Windows Defender などの Microsoft マルウェア検出ソフトウェアが発生することができます/公開しました。 これらの変更の結果として、BizTalk Server ルール エンジン更新サービスを開始する失敗します。  
  
### <a name="resolution"></a>解決策  
 ローカルの HOSTS ファイルに含める、次の行を更新します。  
  
```  
127.0.0.1         localhost  
```  
  
 HOSTS ファイルは %systemroot%\drivers\etc\ ディレクトリ内にあります。  
  
> [!NOTE]
>  SettingsModifier:Win32 から可能な脅威に対処する Microsoft マルウェア プロテクション センターの署名の更新の詳細については/に移動して、公開しました[ http://go.microsoft.com/fwlink/?LinkId=146221](http://go.microsoft.com/fwlink/?LinkId=146221)します。  
  
## <a name="enlistment-of-an-orchestration-fails-if-referenced-assemblies-are-missing-from-the-gacmgmt-db"></a>オーケストレーションが失敗した場合、参照アセンブリが見つからない Gac/mgmt DB からの参加  
  
##### <a name="problem"></a>問題  
 場合、オーケストレーションの参加が失敗した参照 (C#オーケストレーションに参照されるアセンブリ) Gac/mgmt db にはないです。 再展開時に、既存の状態に基づいてオーケストレーションを参加させる必要があります。 参照が不足している場合、展開も失敗します。  
  
##### <a name="cause"></a>原因  
 Gac/mgmt db に参照されたアセンブリが表示されません。  
  
##### <a name="resolution"></a>解決策  
 参照されたアセンブリを GAC に追加または Mgmt db に格納されますしたり、オーケストレーションの参加中にアクセスできるように、リソースとして追加します。  

## <a name="community-blog-biztalk-2013-r2-bugs-issues-quirks"></a>コミュニティのブログ:BizTalk 2013 R2 のバグ、問題、変わった現象

[BizTalk Server 2013 R2 の既知のバグ、問題、変わった現象](https://cdijkgraaf.wordpress.com/2016/08/12/biztalk-2013-r2-known-bugs-issues-quirks/)
  
## <a name="additional-configuration-topics"></a>構成に関するその他のトピック  
  
 [BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)  
  
 [Azure VM での BizTalk Server の構成](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
  [BizTalk Server のクラスター構成](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
  
 [BizTalk Server の展開をセキュリティで保護します。](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  