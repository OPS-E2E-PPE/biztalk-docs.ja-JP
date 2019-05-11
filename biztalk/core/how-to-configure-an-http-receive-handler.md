---
title: HTTP 受信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- permissions, receive handlers
- configuring [HTTP adapters], permissions
- HTTP adapters, receive handlers
- receive handlers, permissions
- configuring [HTTP adapters], receive handlers
- permissions, HTTP adapters
- receive handlers, HTTP adapters
- HTTP adapters, permissions
ms.assetid: c295489e-dbbb-44f7-bddb-d3cdfe302cf5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0aec49f0334a62e559c0812a7b44029c25b4c95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386448"
---
# <a name="how-to-configure-an-http-receive-handler"></a>HTTP 受信ハンドラを構成する方法
受信ハンドラーを HTTP のプロパティを構成する次の手順を使用します。  
  
> [!NOTE]
>  各ホストは、1 つだけの受信ハンドラーが関連付けられていることができます。  
> 
> [!NOTE]
>  HTTP では、BizTalk 分離ホスト インスタンスのコンテキストでアダプターの実行が表示されます。  
> 
> [!CAUTION]
>  HTTP または SOAP アダプタ ハンドラを使用する場合は、Microsoft では、これらのハンドラーのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター。  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a>HTTP の [全般] プロパティの受信ハンドラを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。  
  
2. 展開したアダプターの一覧でクリックして**HTTP、** 受信ハンドラを構成するをクリックするを右クリックし、右側のウィンドウで**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。  
  
4. クリックして**プロパティ**にアクセスする、**バッチ サイズ**プロパティは、HTTP の受信ハンドラー。  
  
5. 1 から 256 に値を入力し、クリックして**OK**します。  
  
6. **[OK]** をクリックします。  
  
   BizTalk Server では、メッセージのバッチを効果的に処理して、1 つのメッセージを非常に高速処理を行わないように設計されています。 ように、ハンドラーが 2 つを使用しようとしている場合、この受信方向または要求-応答の受信場所、次の手順の待機時間を最小限に抑えることができます。  
  
- 設定、**バッチ サイズ**プロパティ値の 1 にします。  
  
- 削減、 **MaxReceiveInterval** 500 の既定値から値を 100 未満の値を**Messaging Isolated、xlang/s では、** と**In-process**サービスクラス。  変更が加えられた、 **adm_ServiceClass**サービスの種類ごとに 1 つのレコードを含む BizTalk 管理データベースのテーブル。  これはサービスの種類全体の変更のため、この設定を変更する場合は、注意を使用します。 この設定を指定します (ミリ秒単位) の最大ポーリング間隔、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージング エージェント、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージをメッセージ ボックス データベースです。  また、使用されますスロットル コント ローラーによって負荷条件下でメッセージの制限が必要かどうかを決定します。 必要な場合、制限コント ローラーは、システムのストレス条件に基づいてメッセージ ディスパッチの間隔を遅延増分します。 高スループットのシステムでは、この設定は使用されません。  この値が使用されると、ただし、時間間隔が動的に変更と、maxreceiveinteral/10 と MaxReceiveInterval の間。  
  
  > [!NOTE]
  >  この設定を変更するで作成されたすべてのホストに影響を**ホストの種類**の**Isolated**します。  
  
- 再起動を任意の HTTP に関連付けられている IIS アプリケーション プールに構成されている関数が表示されます。  
  
  ログオン アカウント、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りが必要し、HTTP が使用する分離コード ファイルを動的にコンパイルする一時ディレクトリまたはディレクトリに書き込みアクセス許可は、関数を受信します。 次の手順を使用して、アクセス許可を付与します。  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a>Biztalkserverisolatedhost アカウントに付与するには、ホスト インスタンスの読み取りし、BizTalk server の一時ディレクトリに対する書き込みアクセス許可  
  
1. クリックして**開始**、 をクリックして**実行**、型**CMD**、ENTER キーを押します。  
  
2. コマンド プロンプトで「 **TEMP 設定**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TEMP**環境変数。  
  
3. コマンド プロンプトで「 **set TMP**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TMP**環境変数。  
  
   ログオン アカウントとして指定されているアカウントに付与、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りと書き込みアクセス許可に関連付けられているディレクトリを**TEMP**と**TMP**環境変数。 ログオン アカウントを特定する、 **BizTalkServerIsolatedHost**インスタンスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックし、 **BizTalkServerIsolatedHost**ホスト右側のペインでインスタンスをクリックして**プロパティ**します。 ホスト インスタンスを使用するログオン アカウントが横に表示されます、**ログオン**ラベル。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)