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
ms.openlocfilehash: f7b7bd79d927a63a0a7af2e9b7079c29aad2d3b1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380445"
---
# <a name="management-and-monitoring"></a>管理と監視
上に構築されたすべてのアプリケーション、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンが管理が必要です。 新しいアプリケーションのインストール方法 構成は、考えられるでしょうか。 現在、システム内で何が起こっているかのでしょうか。 このセクションではこれらの質問に回答するためのツール。  
  
## <a name="installing-biztalk-server"></a>BizTalk Server のインストール  
 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントの数が含まれています、Windows 環境のさまざまな側面に左右されます。 困難なプロセスになるように製品が必要なすべての正しいバージョンが使用し、正しくすべての製品コンポーネントをインストールする可能性がある可能性があります。  
  
 ただし、インストールは簡単です。 自動的に BizTalk Server 2009 からアップグレードして、すべての項目がこの以前のバージョン用に構築された、オーケストレーションやマップ-は引き続き機能します。 適切な環境が存在することの新しいインストールを行う際に管理者に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]標準をダウンロードできます。CAB ファイル、または、既に使用可能な参照です。前にダウンロードされた CAB ファイルです。 どちらの場合は、このファイルには、製品がインストールを必要とする再頒布可能コンポーネントが含まれています。 正しいバージョンの Microsoft Data Access Components (MDAC)、Microsoft XML Parser (MSXML)、最新のセキュリティのホット フィックス、およびその他の必要なソフトウェアなどが含まれます。  
  
 後のこの内容。CAB ファイルがインストールされている、インストールするための 2 つの主なオプションがある[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自体。 作成する開発者の一般的な既定アプローチを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境独自の使用方法の可能性があります、インストールの 1 つのアカウント、製品のコンポーネントをすべて 1 台のコンピューター。 プロセスが開始されると、これらのコンポーネントがインストールされているときに、開発者がウォッチだけできます。 管理者用の実稼働設定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境はこれに対し、カスタム構成オプションを使用できます。 この選択は、製品を異なるコンピューターに展開する、定義と別のアカウント、およびその他のより詳細な構成を使用できます。  
  
## <a name="creating-scalable-configurations"></a>スケーラブルな構成を作成します。  
 高可用性または冗長性に関する要件、全体ではない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンは、1 台のコンピューターにインストールすることができます。 場合によっては、ただし、これはできません、適切なソリューション。 おそらく、エンジンを処理する必要がありますのメッセージの数は 1 台のコンピューターに対して多すぎるまたは冗長性は、システムの信頼性を高めるに必要な可能性があります。 上記のような要件を満たすために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンは、さまざまな方法でデプロイできます。  
  
 エンジンを展開するための基本的な概念が、ホストの考え方です。 ホストは、オーケストレーション、アダプター、およびパイプラインを含む、さまざまな項目を含めることができます。 ただし、ホストには単なる論理的構造です。 これらを使用するには、BizTalk Server 管理者は、ホスト インスタンスを作成する必要があります. 各ホスト インスタンスは、Windows のプロセスととして次の図にはさまざまな考慮事項含めることができます。 コンピューター A には、ここで示した例の 2 つのホスト インスタンスにホーム。 受信アダプターが含まれていて、受信パイプライン、オーケストレーション P が含まれているし、Q. コンピューター B は、2 つのオーケストレーション P と q: コンピューター C では、コンピューター A でのようにも格納している 1 つのホスト インスタンスを実行中には 2 つのホスト インスタンスにホームもオーケストレーションが含まれています。 代わりに、これらの各インスタンスを別の送信パイプラインが含まれていて、送信アダプター。 最後に、コンピューター D では、すべてのホスト インスタンスでこの構成で使用されるメッセージ ボックス データベースが格納されています。  
  
 ![](../core/media/understandingbts-09-hosts.gif "UnderstandingBTS_09_Hosts")  
  
 この例では、ホストが使用されるいくつかの方法を示します。 たとえば、A と B の両方のマシンからはオーケストレーション P と Q、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用性、各マシンの現在の負荷に基づいて、これらのオーケストレーションに要求の分散を自動的に読み込むことができます。 これにより、大量のプロセスの必要に応じてスケール アップする BizTalk アプリケーションができます。 コンピューター C には、送信メッセージを処理するためにさまざまな方法が 2 つ含まれています。 注意してください。 標準のいずれかの依存おそらく[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]など、HTTP アダプターは、特定のシステムとの通信にカスタム アダプターを使用しますが、その他のアダプター。 このような単一のコンピューターに処理のすべての出力をグループ化状況によっては適切であるをこと。 各ホスト インスタンスは他のすべてのホスト インスタンスから分離されます。-別のプロセス-別のインスタンスで、新しいカスタム アダプタなど、完全に信頼されていないコードを実行する方が安全です。 レプリケートまたはクラスタ化と、単一障害点を作成しないようにすることは、この例は、メッセージ ボックス データベースのインスタンスが 1 つだけを含んでいるにもかかわらずです。  
  
 現在のバージョンで導入された BizTalk アプリケーションの抽象化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]本質的に、ホストに関連付けられていません。 単純な BizTalk アプリケーションのすべてのコンポーネント可能性がありますに含める 1 つのホストと同じコンピューターにインストールされているそれらのすべて。 複雑な場合は、ただし、さまざまな成果物を構成するアプリケーション、オーケストレーション、アダプタ、パイプライン、および -複数のホスト上の図のように、複数のコンピューターに分散することがあります。 したがって、物理マシンにこれらの成果物をマッピングする処理は、BizTalk アプリケーションの概念に依存しません。  
  
## <a name="managing-applications"></a>アプリケーションの管理  
 メインの管理ツール、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンは、BizTalk Server 管理コンソールのユーザー インターフェイスを提供する Microsoft 管理コンソール (MMC) スナップイン[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者。 このツールには、さまざまな機能の管理者が利用できますが、最も重要な機能は次の 3 つの作業を行います。  
  
- **BizTalk アプリケーションをデプロイします。** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者の単位として、すべての BizTalk アプリケーションで作業することができます。 BizTalk Server 管理コンソールを使用して、管理者は、BizTalk アプリケーションを作成し、1 つまたは複数のサーバーにデプロイします。  
  
- **BizTalk アプリケーションを構成します。** 開発者は、オーケストレーションを作成するときに、論理語の大部分では動作します。 定義する方法、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジンと通信、特定のアプリケーションでは、たとえば、開発者が使用される特定の URL について悩むことがなく HTTP アダプターを選択できます。 同様に、開発者は、送信パイプラインがこの署名の作成にどのようなキーを使用する正確に気にせず、送信メッセージにデジタル署名を追加するコンポーネントを含める必要がありますを指定することができます。 まだ、アプリケーションが機能するために、これらの詳細を指定する必要があります。 BizTalk Server 管理コンソールでは、上記のような構成を作成および変更できます。  
  
- **BizTalk アプリケーションを監視します。** 使用して、**グループ ハブ**ページが BizTalk Server 管理コンソールで、管理者は、BizTalk アプリケーションの動作を監視できます。 グループ ハブには、これらのアプリケーションの現在の状態に関する情報が表示されます。 および、れるので、アプリケーションは、さまざまな方法で調べることができます。 たとえば、問題を検索する管理者を必要とするのではなく、**グループ ハブ**ページでは、色分けされたインジケーターを使用して、これらの問題を表示します。 これにより、管理者がアプリケーションの監視をより予防的なアプローチです。  
  
  依存する BizTalk 管理コンソール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の管理データベース、その他のサービスも提供します。 管理者は動的にマシンを追加し、ホストを指定、アプリケーションの実行中に、それらに割り当てられています。 これらの変更にアプリケーションをシャット ダウンする必要はありません。 管理コンソールの機能にもアクセスできますプログラムを介して Windows Management Instrumentation (WMI)、管理機能を自動化するスクリプトを作成することもできます。  
  
## <a name="reporting-on-and-debugging-applications"></a>レポートの作成と、アプリケーションのデバッグ  
 BizTalk アプリケーションでは多くの問題: 送信しメッセージを受信、オーケストレーション内でそれらのメッセージ処理、別のプロトコルを使用するさまざまなシステムと通信します。 アプリケーションのアクティビティのレコードを維持するには、特にエラーが発生した場合は、非常に便利です。 同様に、オーケストレーションとその他のアプリケーション コンポーネントをデバッグする手段を持つことが不可欠です。 これら両方の機能は、グループ ハブによって提供される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
-   グループ ハブでは、エンジンで実行されているアプリケーションに関する情報をグラフィカルにアクセスを提供します。 オーケストレーションが開始され、終了、それぞれのメッセージの送信し、受信されると、それらのメッセージの内容、内の各図形が実行されたときに、この情報を含めることができます。 開発者または管理者はでもオーケストレーションを停止し、事前に定義された場所で調査、ブレークポイントを設定します。 グループ ハブこともできますアーカイブされたデータを調査するビジネス プロセスの実行のパターンや傾向を検索します。 この情報は、デバッグに役立ちます (確認メッセージを実際に顧客に送信されたこと) などのビジネスの質問に答えることと、継続的な統計を維持することは、パフォーマンスを向上させるために使用できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server メッセージング エンジン](../core/the-biztalk-server-messaging-engine.md)   
インストール[BizTalk Server 2016](../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)または[BizTalk Server 2013 または R2](../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)    
[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)  
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)   
 [グループ ハブ ページの使用](../core/using-the-group-hub-page.md)