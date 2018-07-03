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
ms.openlocfilehash: 7b58dcb66e4a001d7d163f5d8de53fb89502c6ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983387"
---
# <a name="how-to-configure-an-http-receive-handler"></a>HTTP 受信ハンドラを構成する方法
次の手順を実行して、HTTP 受信ハンドラのプロパティを構成します。  
  
> [!NOTE]
>  各ホストに関連付けられる受信ハンドラは 1 つだけです。  
> 
> [!NOTE]
>  HTTP 受信アダプタは、BizTalk 分離ホスト インスタンスのコンテキストで実行されます。  
> 
> [!CAUTION]
>  HTTP アダプター ハンドラーまたは SOAP アダプター ハンドラーを使用するときは、これらのハンドラーのホスト インスタンスを Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、または [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] コンピューターにインストールすることをお勧めします。  
  
### <a name="to-configure-the-general-properties-for-an-http-receive-handler"></a>HTTP 受信ハンドラの全般プロパティを構成するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。  
  
2. 展開したアダプターの一覧でクリックして**HTTP、** 受信ハンドラを構成するをクリックするを右クリックし、右側のウィンドウで**プロパティ**します。  
  
3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。  
  
4. クリックして**プロパティ**にアクセスする、**バッチ サイズ**プロパティは、HTTP の受信ハンドラー。  
  
5. 1 から 256 に値を入力し、クリックして**OK**します。  
  
6. **[OK]** をクリックします。  
  
   BizTalk Server では、メッセージのバッチを効果的に処理して、1 つのメッセージを非常に高速処理を行わないように設計されています。 したがって、この受信ハンドラーを双方向 (要求 - 応答) の受信場所で使用する場合は、次の手順に従うことで、待機時間を最小限に抑えることができます。  
  
- 設定、**バッチ サイズ**プロパティ値の 1 にします。  
  
- 削減、 **MaxReceiveInterval** 500 の既定値から値を 100 未満の値を**Messaging Isolated、xlang/s では、** と**In-process**サービスクラス。  変更が加えられた、 **adm_ServiceClass**サービスの種類ごとに 1 つのレコードを含む BizTalk 管理データベースのテーブル。  これはサービスの種類全体の変更のため、この設定を変更する場合は、注意を使用します。 この設定は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージング エージェントが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ ボックス データベースでメッセージをポーリングするときの最大ポーリング間隔 (ミリ秒) を指定します。  また、特定の負荷条件下でメッセージの制限が必要かどうかを制限コントローラーが判断する際にも使用されます。 必要な場合、制限コントローラーは、システムのストレス条件に基づいてメッセージ ディスパッチの間隔を段階的に遅らせます。 高スループットのシステムでは、この設定は使用されません。  ただし、一度この値を使用すると、MaxReceiveInteral/10 と MaxReceiveInterval の間で間隔が動的に変更されます。  
  
  > [!NOTE]
  >  この設定を変更するで作成されたすべてのホストに影響を**ホストの種類**の**Isolated**します。  
  
- 構成済みの HTTP 受信機能に関連付けられている IIS アプリケーション プールを再起動します。  
  
  ログオン アカウント、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りが必要し、HTTP が使用する分離コード ファイルを動的にコンパイルする一時ディレクトリまたはディレクトリに書き込みアクセス許可は、関数を受信します。 アクセス許可を与えるには、次の操作を行います。  
  
### <a name="to-grant-the-account-for-the-biztalkserverisolatedhost-host-instance-read-and-write-permissions-to-the-temp-directory-of-your-biztalk-server"></a>BizTalkServerIsolatedHost ホスト インスタンスのアカウントに、BizTalk Server の一時ディレクトリの読み取りアクセス許可と書き込みアクセス許可を与えるには  
  
1. クリックして**開始**、 をクリックして**実行**、型**CMD**、ENTER キーを押します。  
  
2. コマンド プロンプトで「 **TEMP 設定**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TEMP**環境変数。  
  
3. コマンド プロンプトで「 **set TMP**に関連付けられているディレクトリを表示するには ENTER キー押すと、 **TMP**環境変数。  
  
   ログオン アカウントとして指定されているアカウントに付与、 **BizTalkServerIsolatedHost**ホスト インスタンスの読み取りと書き込みアクセス許可に関連付けられているディレクトリを**TEMP**と**TMP**環境変数。 ログオン アカウントを特定する、 **BizTalkServerIsolatedHost**インスタンスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、展開**ホスト インスタンス**を右クリックし、 **BizTalkServerIsolatedHost**ホスト右側のペインでインスタンスをクリックして**プロパティ**します。 ホスト インスタンスを使用するログオン アカウントが横に表示されます、**ログオン**ラベル。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)