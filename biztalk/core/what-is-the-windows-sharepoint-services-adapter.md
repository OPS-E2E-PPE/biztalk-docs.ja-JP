---
title: "Windows SharePoint Services アダプターについて  | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, process flow
- Windows SharePoint Services adapters, receiving documents
- Windows SharePoint Services adapters, sending documents
- Windows SharePoint Services adapters, security
- Windows SharePoint Services adapters
- Windows SharePoint Services adapters, about Windows SharePoint Services adapters
ms.assetid: 1875ac85-46c2-4da5-ad16-8b078cb4cbd7
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a25bc378bdbb4c8bef34c3cff0140d03094faad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターについて 
Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプタによって、Windows SharePoint Services と Microsoft Office InfoPath の密接な統合を実現できます。 このトピックでは、Windows SharePoint Services アダプタの機能および動作の概要について説明します。  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプタの機能  
 Windows SharePoint Services アダプタの主要機能を次の一覧に示します。  
  
-   XML またはバイナリの BizTalk Server メッセージを SharePoint Services ドキュメント ライブラリに送信する機能。  
  
-   InfoPath との統合: Windows SharePoint Services サイトから開かれたときに InfoPath で自動的に開くへの送信の BizTalk Server の XML メッセージを変換することができます。  
  
-   Windows SharePoint Services に送信されるメッセージのプロパティの昇格。 オーケストレーション インスタンス ID、メッセージ ID、またはメッセージから抽出した値など、メッセージに関する BizTalk Server メタデータで、最大 16 列の SharePoint 列を更新できます。  
  
-   メッセージの内容および BizTalk Server プロパティに基づくファイル名の定義。  
  
-   任意の一覧にドキュメントを送信する機能 (の代わりに、ドキュメント ライブラリに) ここで Windows SharePoint Services では、ドキュメント自体は格納されませんが、プロパティの昇格が発生するので、新しい一覧項目が作成され、列の値が取得されます。メッセージです。  
  
-   任意のドキュメント ライブラリの任意のビューからメッセージを受信し、指定したファイル名を使用して指定されたドキュメント ライブラリに保存して整理する機能。  
  
-   BizTalk Server で Windows SharePoint Services アダプターのプロパティの昇格: Windows SharePoint Services ファイルの情報はメッセージ コンテキスト プロパティとして BizTalk Server で使用可能になります。 メッセージ コンテキスト プロパティには、パイプライン、オーケストレーションなどからアクセスできます。カスタム SharePoint 列には WSS.InPropertiesXml ドキュメント経由でアクセスできます。  
  
-   動的ポートの完全なサポート: 送信アダプターは、(送信ポートの作成時に、ユーザーによって定義された) 静的 URI バインドまたは (メッセージを送信するときに、オーケストレーションで定義された) 動的 URI バインドをサポートできます。 物理送信ポートや動的送信ポートのすべての構成情報は、WSS.Filename、WSS.ConfigTimeout などのメッセージ コンテキスト プロパティから定義できます。  
  
-   パフォーマンス カウンター  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a>Windows SharePoint Services アダプターの動作  
 Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプタは、次の 3 つの主要コンポーネントから構成されています。  
  
-   Windows SharePoint Services アダプタ Web サービス  
  
-   Windows SharePoint Services 受信アダプタ  
  
-   Windows SharePoint Services 送信アダプタ  
  
 Windows SharePoint Services サーバーには、Windows SharePoint Services のライブラリおよび一覧にアクセスするための Web サービス (BTSharePointAdapterWS.asmx) がインストールされます。 この Web サービスは、SharePoint ライブラリのドキュメントを取得、配置、削除、およびアーカイブするメソッドを公開しています。 受信アダプタは Web サービスからファイルを受け取り、送信アダプタは Web サービスにファイルを渡します。  
  
 次の図は、これらの機能を提供する Windows SharePoint Services 用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アダプタの主要なコンポーネントを示しています。  
  
 ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a>Windows SharePoint Services からのドキュメントの受信  
 受信アダプタは、Windows SharePoint Services ドキュメント ライブラリのビューにポーリングして、 Windows SharePoint Services サーバーにある、Windows SharePoint Services オブジェクト モデルを使用する Web メソッドを呼び出し、ライブラリの参照、ファイルのチェックアウト、およびアダプタへのファイル データ返信を行います。 その後、BizTalk Server メッセージ ボックスにファイルを送信して、Windows SharePoint Services からファイルを削除またはアーカイブする別のメソッドを呼び出します。 Windows SharePoint Services ライブラリのファイルをフィルタ選択するため、アダプタが Windows SharePoint Services のビューから Windows SharePoint Services のライブラリにポーリングします。  
  
 ポーリングを一括して行うことで、BizTalk Server で構成できる単純な管理モデルが実現されます。 また、メッセージのバッチ処理が可能になり、パフォーマンスが向上します。  
  
 Windows SharePoint Services、Web サービス、および BizTalk Server ではプラットフォームレベルのトランザクションのサポートを利用できないので、チェックアウト メカニズムを使用して障害発生に伴うエラーを最小限に抑えます。 一定の条件下では、つまり、BizTalk Server メッセージ ボックス データベースにファイルが正常に送信されるものの、Windows SharePoint Services から削除できない場合は、ファイルは BizTalk Server に送信された後も Windows SharePoint Services サーバーでチェックアウトされたままになります。 エラーは BizTalk Server のイベント ログに記録されます。  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a>Windows SharePoint Services へのドキュメントの送信  
 アダプタは、Windows SharePoint Services サーバーの Web メソッドを呼び出すことによって、Windows SharePoint Services にドキュメントを送信します。 Windows SharePoint Services サイトの URL、そのサイトから見たドキュメント ライブラリまたは一覧の相対 URL、ファイル、または一覧項目名と昇格させたプロパティを指定して、そのファイルに関連付けます。  
  
 ファイル名は、固定文字列またはドキュメントの XML データから派生した名前に設定できます。 派生した名前を使用すると、標準の名前付け規則を適用しやすくなります。 また、昇格させたファイル プロパティの値を列の値として設定できます。 ファイル名と同様に、昇格させたプロパティの値は、固定文字列またはドキュメントの XML データから派生した名前に設定できます。  
  
> [!IMPORTANT]
>  Windows SharePoint Services アダプタの昇格させたプロパティは、BizTalk Server の昇格させたプロパティや Windows SharePoint Services の昇格させたプロパティとは異なるエンティティです。  
  
 Windows SharePoint Services の昇格させたプロパティを使用すると、Windows SharePoint Services フォーム ライブラリを参照するときに XML 要素を表示できます。 InfoPath フォームを Windows SharePoint Services フォーム ライブラリに公開すると、主要な要素を自動的に昇格させるようフォーム ライブラリが構成されます。 この機能は、Windows SharePoint Services で InfoPath フォーム ライブラリ (同一の XSD スキーマと InfoPath ソリューションを使用した複数の InfoPath フォームを保存するドキュメント ライブラリ) を使用するときに限り使用できます。  
  
 Windows SharePoint Services アダプタでのプロパティの昇格を使用することで、スキーマが異なるドキュメントが同一のドキュメント ライブラリに保存されているときに、ユーザーが Windows SharePoint Services にプロパティを昇格できます。  
  
 オーケストレーションにはプロパティをメッセージのプロパティとして見せ、エンド ユーザーの UI には見せないようにする点では、BizTalk Server のプロパティの昇格も同様の考え方です。 BizTalk Server では、プロパティの値をドキュメントに戻して保存するときにプロパティを降格するという概念もサポートされています。  
  
 Windows SharePoint Services アダプタを (任意の XML およびドキュメント ライブラリではなく) InfoPath フォームおよびフォーム ライブラリと使用するときは、昇格させたプロパティを送信アダプタで設定する必要はありません。 代わりに、(メッセージを直接変更するか、降格するプロパティから間接的に変更して) ドキュメントをオーケストレーション内で変更できます。 値は Windows SharePoint Services により自動的に昇格されます。  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプタのセキュリティに関する考慮事項  
 Windows SharePoint Services アダプタは、Windows SharePoint Services Web サイトで実行される BTSharePointAdapterWS Web サービスと、BizTalk Server ホスト インスタンス プロセス内の BizTalk Server で実行されるアダプタ ランタイムという 2 つのサブシステムから構成されています。 アダプタ ランタイムから呼び出す BTSharePointAdapterWS Web サービスには、Windows SharePoint Services 内の特定の作業を実行できるアクセス許可が必要です。 アダプタ ランタイムは呼び出し元として実行されるので、アクセス許可は呼び出し元に与える必要があります。 つまり、BizTalk ホスト インスタンスを行う必要があります、**共同作成者**を送信し、そのサイトからメッセージを受信できるように、SharePoint サイトでします。 BTSharePointAdapterWS Web サービスは、のメンバーによってのみ呼び出すことができます、 **SharePoint Enabled Hosts**グループ。 Web サービスと対話する、アダプター ランタイムを実行している BizTalk ホスト インスタンスを許可するためにホスト インスタンスの Windows アカウント行う必要がありますのメンバー、 **SharePoint Enabled Hosts**グループ。 SharePoint のメンバーのアカウントを追加し、ホスト インスタンスを作成したり、このグループにもからアカウントを削除するには、管理者の責任において、**共同作成者**ロール。  
  
|コンポーネント|プロセス ID|権限|  
|---------------|----------------------|----------------|  
|BTSharePointAdapterWS Web サービス|呼び出し元の ID|SharePoint Enabled Hosts グループに与えられた呼び出しアクセス許可|  
|アダプタ ランタイム|BizTalk ホストの ID|なし|  
|Windows SharePoint Services オブジェクト モデル|なし|SharePoint Enabled Hosts グループのメンバーである必要があります、**共同作成者**SharePoint Services のロール。|  
  
 BizTalk Server のセットアップがのメンバーであるアカウントのみにするように、BTSharePointAdapterWS Web サービスにアクセス許可を構成、 **SharePoint Enabled Hosts**グループがこの Web サービスにアクセスできます。 管理者がそのホストに関連付けられた NT グループを追加する必要があるホストで Windows SharePoint Services アダプターを実行する場合、 **SharePoint Enabled Hosts**グループを追加、 **SharePoint Enabled Hosts**グループ、Windows SharePoint Services に**共同作成者**ロール。  
  
 Windows SharePoint Services のファイル、一覧、およびドキュメント ライブラリへのアクセス許可は、Windows SharePoint Services のセキュリティで制限します。 メッセージは、Windows SharePoint Services から直接 BizTalk Server に送信されます。 アダプタ ランタイムと Web サービスの間の通信は、HTTP または HTTPS 経由で行われます。  
  
 アダプタでは、BTSharePointAdapterWS Web サービスが Windows SharePoint Services サイトと同一の HTTP スキーマ (HTTP または HTTPS) を使用していることを前提としています。 つまり、セキュリティで保護された IIS Web サイトに Windows SharePoint Services サイトが作成されている場合、BTSSharePointAdapterWS Web サービスとの通信には HTTPS が使用され、サーバー証明書がない IIS Web サイトに Windows SharePoint Services サイトが作成されている場合、HTTP が使用されます。  
  
## <a name="see-also"></a>参照  
 [設定して、Windows SharePoint Services アダプターの展開](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターを構成します。](../core/configuring-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプタのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)