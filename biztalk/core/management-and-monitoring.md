---
title: 管理と監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92724f79-32bb-40d3-a0af-147aba00d87e
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea24b6e36de3920a820efe2ac1af177b8a00720d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973571"
---
# <a name="management-and-monitoring"></a>管理と監視
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンで構築されるすべてのアプリケーションは管理が必要です。 ここでは、新しいアプリケーションのインストール方法、 可能な構成、 システムの内部で現在発生している状況などを 確認するためのツールについて説明します。  
  
## <a name="installing-biztalk-server"></a>BizTalk Server のインストール  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には多くのコンポーネントが用意されていますが、これらは Windows 環境のさまざまな側面に左右されます。 製品に必要なものがすべて正しいバージョンで使用できることを確認し、製品のコンポーネントをすべて正しくインストールすることは、時として困難なプロセスになります。  
  
 ただし、インストール自体は簡単です。 BizTalk Server 2009 からのアップグレードは自動的に行われます。また、オーケストレーションやマップなど、以前のバージョンで構築したすべてのアイテムはそのまま動作します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を新しくインストールする管理者は、適切な環境が整っているかどうかを確認するため、標準の .CAB ファイルをダウンロードするか既にダウンロード済みの .CAB ファイルを参照できます。 どちらの場合も、このファイルで、製品のインストールに必要な再配布可能コンポーネントを確認できます。 たとえば、正しいバージョンの Microsoft Data Access Components (MDAC)、Microsoft XML Parser (MSXML)、最新のセキュリティ修正パッチ、その他の必要なソフトウェアなどを確認できます。  
  
 .CAB ファイルの内容をインストールした後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 本体をインストールするには、2 つの方法があります。 多くの開発者が独自の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を構築するときに採用する既定の方法は、1 台のコンピューター上に 1 つのアカウントですべての製品コンポーネントをインストールする方法です。 インストール処理が始まると、これらのコンポーネントは自動的にインストールされるので、開発者はこれを確認するだけです。 一方、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の実稼働環境を設定する管理者の場合は、カスタム構成オプションを使用することもあります。 この方法を選択すると、別のコンピューターに製品を展開したり、さまざまなアカウントを定義して使用したり、さらにその他の詳細な構成も可能になります。  
  
## <a name="creating-scalable-configurations"></a>スケーラブルな構成の作成  
 高可用性または冗長性が必要ない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジン全体を 1 台のコンピューターにインストールできます。 しかし状況によっては、この方法が適切でない場合があります。 たとえば、BizTalk Server 2006 エンジンで処理が必要となるメッセージの数が 1 台のコンピューターに対して多すぎる場合や、システムの信頼性をより高めるため冗長性が必要とされる場合などです。 このような場合の要件を満たすため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンはさまざまな方法で展開できるようになっています。  
  
 エンジンを展開するときの基本となる概念はホストです。 ホストには、オーケストレーション、アダプター、パイプラインなど、さまざまな項目を含めることができます。 ただし、ホストは単なる論理的な構成要素であり、 ホストを使用するには、BizTalk Server 管理者がホスト インスタンスを作成する必要があります。 各ホスト インスタンスは Windows プロセスであり、次の図に示すようにさまざまな項目を含めることができます。 この例では、コンピューター A に 2 つのホスト インスタンスが存在し、 受信アダプターが含まれていて、受信パイプライン、オーケストレーション P が含まれているし、Q. コンピューター B は、2 つのオーケストレーション P と q: コンピューター C では、コンピューター A でのようにも格納している 1 つのホスト インスタンスを実行中には 2 つのホスト インスタンスにホームもオーケストレーションが含まれています。 代わりに、インスタンスごとに別の送信パイプラインと送信アダプターが含まれています。 最後に、コンピューター D には、この構成に含まれているすべてのホスト インスタンスで使用されるメッセージ ボックス データベースが格納されています。  
  
 ![](../core/media/understandingbts-09-hosts.gif "UnderstandingBTS_09_Hosts")  
  
 この例では、ホストの使用方法がいくつか示されています。 たとえば、コンピューター A と B の両方でオーケストレーション P と Q を実行できるので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では各コンピューターの可用性と現在の負荷に基づいて、これらのオーケストレーションに自動的に要求の負荷を分散できます。 このことにより、容量を多く使用するプロセスにも対応できるよう、BizTalk アプリケーションを拡張できます。 また、コンピューター C では 2 とおりの方法で送信メッセージを処理できます。 1 つは、HTTP アダプターなどの、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の標準アダプターを使用する方法で、もう 1 つは、カスタム アダプターを使用して特定のシステムと通信する方法です。 1 台のコンピューターの出力処理をすべてグループ化することは、場合によっては優れた判断といえます。 また、各ホスト インスタンスは他のすべてのホスト インスタンスと分離され、別のプロセスとして動作するので、新しいカスタム アダプタなど信頼性の確実でないコードを個別のインスタンスで実行しても比較的安全です。 この例には、メッセージ ボックス データベースの 1 つのインスタンスだけが含まれていますが、この場合もエラーを回避して継続的な動作を実現するよう、データベースをレプリケートまたはクラスタ化できます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の現在のバージョンで導入された BizTalk アプリケーションの抽象化は、本質的にホストと関連するものではありません。 単純な BizTalk アプリケーションの場合、すべてのコンポーネントは 1 つのホストに含まれ、同じコンピューター上にインストールされます。 一方、より複雑なアプリケーションの場合は、上の図のように、オーケストレーション、アダプタ、パイプラインなどアプリケーションを構成するさまざまなアイテムが、複数のコンピュータ上にある複数のホストに分散されます。 したがって、物理的なコンピュータにこれらのアイテムをマッピングするプロセスは、BizTalk アプリケーションの概念には依存しません。  
  
## <a name="managing-applications"></a>アプリケーションの管理  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンのメインの管理ツールは、BizTalk Server 管理コンソールです。これは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者向けのユーザー インターフェイスを搭載した、Microsoft 管理コンソール (MMC) のスナップインです。 管理者はこのツールを使用して多くの機能を実現できます。中でも最も重要な機能は次の 3 つです。  
  
- **BizTalk アプリケーションをデプロイします。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者の単位として、すべての BizTalk アプリケーションで作業することができます。 BizTalk Server 管理コンソールを使用すると、管理者は BizTalk アプリケーションを作成し、作成したアプリケーションを 1 つ以上のサーバーに展開できます。  
  
- **BizTalk アプリケーションを構成します。** 開発者がオーケストレーションを作成するときに行う作業の多くは論理的なものです。 たとえば開発者は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンと特定のアプリケーションの通信方法を定義するときに、使用される具体的な URL を考慮することなく HTTP アダプターを選択できます。 同様に開発者は、送信メッセージにデジタル署名を追加するコンポーネントを送信パイプラインに含めることができますが、このとき、デジタル署名の作成に使用される正確なキーを考慮する必要はありません。 ただし、アプリケーションが機能するにはこれらの詳細を別に指定する必要があります。 BizTalk Server 管理コンソールで、管理者はこのような構成を作成および変更できます。  
  
- **BizTalk アプリケーションを監視します。** 使用して、**グループ ハブ**ページが BizTalk Server 管理コンソールで、管理者は、BizTalk アプリケーションの動作を監視できます。 グループ ハブにはこれらのアプリケーションの現在の状態に関する情報が示されるので、アプリケーションをさまざまな方法で調べることができます。 たとえば、問題を検索する管理者を必要とするのではなく、**グループ ハブ**ページでは、色分けされたインジケーターを使用して、これらの問題を表示します。 これにより、管理者はさらに効率よくアプリケーションを監視でき、問題を未然に防ぐことができます。  
  
  BizTalk 管理コンソールは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の管理データベースに依存しています。また、上記以外のサービスも提供しています。 アプリケーションの実行中でも、管理者は動的にコンピューターを追加でき、追加したコンピューターに割り当てるホストを指定できます。 これらの変更を行うためにアプリケーションをシャットダウンする必要はありません。 管理コンソールの機能には、WMI (Windows Management Instrumentation) のプログラムからアクセスすることもできます。管理者は WMI を使用して、管理機能を自動化するスクリプトを作成できます。  
  
## <a name="reporting-on-and-debugging-applications"></a>アプリケーションに関するレポートの作成とアプリケーションのデバッグ  
 BizTalk アプリケーションでは、メッセージの送受信、オーケストレーション内でのメッセージの処理、異なるプロトコルを経由したさまざまなシステムとの通信など、数多くの処理が行われます。 アプリケーションの動作を記録しておくと、特にエラーが発生したときに非常に役立ちます。 同様に、オーケストレーションやその他のアプリケーション コンポーネントをデバッグする方法をいくつか用意しておくことも重要です。 これら両方の機能は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のグループ ハブで提供されます。  
  
-   グループ ハブを使用すると、BizTalk Server エンジンで実行されているアプリケーションに関する情報に、グラフィカルにアクセスできます。 これらの情報には、オーケストレーションの開始日時と終了日時、オーケストレーション内の各図形の実行日時、オーケストレーションの各メッセージの送受信日時、メッセージに含まれる内容などがあります。 開発者や管理者はブレークポイントを設定することもでき、あらかじめ指定した場所でオーケストレーションを停止してその内容を調査できます。 また、グループ ハブではアーカイブされたデータを調査することもでき、ビジネス プロセスの実行パターンや傾向を分析できます。 分析した情報は、デバッグや、業務上の疑問点への回答 (メッセージが確実に顧客に送信されたかどうかの確認など) に役立てたり、継続的な統計を集めて、パフォーマンスの向上に使用できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server メッセージング エンジン](../core/the-biztalk-server-messaging-engine.md)   
インストール[BizTalk Server 2016](../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)または[BizTalk Server 2013 または R2](../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)    
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)  
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)   
 [グループ ハブ ページの使用](../core/using-the-group-hub-page.md)