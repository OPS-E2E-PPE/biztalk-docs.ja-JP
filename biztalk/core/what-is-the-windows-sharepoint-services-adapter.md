---
title: Windows SharePoint Services アダプターとは何ですか。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4949188ec1bed73fa663a7cfb87e7c3bdad6265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242921"
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターとは何ですか。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows SharePoint services アダプターは、Windows SharePoint Services と Microsoft Office InfoPath の密接な統合を提供します。 次のトピックでは、機能と、Windows SharePoint Services アダプターの動作の概要について説明します。  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプタの機能  
 次の一覧には、Windows SharePoint Services アダプターの重要な機能について説明します。  
  
-   SharePoint ドキュメント ライブラリに BizTalk Server の XML、バイナリ メッセージを送信する機能。  
  
-   InfoPath との統合:Windows SharePoint Services サイトから開いたときに InfoPath で自動的に開きますへの送信の BizTalk Server の XML メッセージを変換できます。  
  
-   Windows SharePoint Services に送信されるメッセージのプロパティの昇格。 最大 16 の SharePoint 列は、メッセージのようなオーケストレーション インスタンス ID、メッセージ ID、またはメッセージから抽出された値に関するメタデータを BizTalk Server で更新できます。  
  
-   ファイル名の定義は、プロパティをメッセージの内容および BizTalk Server に基づきます。  
  
-   任意の一覧にドキュメントを送信する機能 (の代わりに、ドキュメント ライブラリに)。ここでは、ドキュメント自体は Windows SharePoint Services に格納されませんが、プロパティの昇格が発生するので、新しいリスト アイテムが作成され、列の値は、メッセージから取得されます。  
  
-   任意のドキュメント ライブラリの任意のビューからメッセージを受信し、指定したファイル名を使用して指定されたドキュメント ライブラリにアーカイブできる機能。  
  
-   BizTalk Server で Windows SharePoint Services アダプターのプロパティの昇格:Windows SharePoint Services ファイルの情報はメッセージ コンテキスト プロパティとして BizTalk Server で使用されます。 メッセージ コンテキスト プロパティは、パイプライン、オーケストレーションなどからアクセスできます。カスタムの SharePoint 列は、WSS を介してアクセスできます。InPropertiesXml ドキュメントです。  
  
-   動的ポートに完全にサポートします。送信アダプターは、静的 URI バインドが (送信ポートが作成されるときにユーザーによって定義) または (メッセージを送信するときに、オーケストレーションで定義された)、動的 URI バインドをサポートできます。 すべての構成情報は、WSS などのメッセージ コンテキスト プロパティを定義できます。ファイル名と WSS。ConfigTimeout、動的送信ポートを物理送信ポートとして。  
  
-   パフォーマンス カウンター  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a>Windows SharePoint Services アダプターの動作  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows SharePoint services アダプターは、次の 3 つの主要なコンポーネントで構成されます。  
  
- Windows SharePoint Services アダプター Web サービス  
  
- Windows SharePoint Services 受信アダプタ  
  
- Windows SharePoint Services 送信アダプター  
  
  Windows SharePoint Services サーバーで Windows SharePoint Services ライブラリとリストへのアクセスを提供する Web サービス (BTSharePointAdapterWS.asmx) がインストールされています。 Web サービスは、get、put、削除、および SharePoint ライブラリからドキュメントをアーカイブするメソッドを公開します。 受信アダプターは、Web サービスからのファイルとして投稿ファイル送信アダプターを取得します。  
  
  次の図の主要なコンポーネントを示しています、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらの機能を提供する Windows SharePoint services アダプター。  
  
  ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a>Windows SharePoint Services からドキュメントの受信  
 受信アダプターは、Windows SharePoint Services ドキュメント ライブラリのビューをポーリングします。 Windows SharePoint Services オブジェクト モデルを使用してライブラリを参照する、ファイルをチェック アウト、およびアダプターにファイル データを返す Windows SharePoint Services サーバーで Web メソッドを呼び出します。 アダプターは、BizTalk Server メッセージ ボックスにファイルを送信し、削除または Windows SharePoint Services からファイルをアーカイブする別の Web メソッドを呼び出します。 Windows SharePoint Services ライブラリ内のファイルをフィルター処理するためには、アダプターは、Windows SharePoint Services ビューを介して Windows SharePoint Services ライブラリをポーリングします。  
  
 (ポーリング) を一元的なアプローチには、BizTalk server の構成が完了したら、シンプルな管理モデルが用意されています。 メッセージのバッチ処理を許可するというが、パフォーマンスの向上も提供します。  
  
 Windows SharePoint Services、Web サービス、および BizTalk Server では、プラットフォーム レベルのトランザクション サポートを利用できない、ために、チェック アウト メカニズムがエラー状態に関連付けられているエラーを最小限に抑えるに使用されます。 特定の条件下で (つまり、ファイルを BizTalk Server メッセージ ボックス データベースに正常に送信されますが、Windows SharePoint Services から削除することはできません)、いても、それらのファイルは、Windows SharePoint Services サーバーでチェック アウトされたままBizTalk Server に送信します。 エラーは、BizTalk server のイベント ログに記録されます。  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a>Windows SharePoint Services にドキュメントを送信します。  
 アダプターは、Windows SharePoint Services サーバーで Web メソッドを呼び出すことによって、Windows SharePoint Services にドキュメントを送信します。 アダプターは、Windows SharePoint Services サイトの URL、ドキュメント ライブラリまたはリストの URL サイト、ファイル、またはリスト項目の名前を基準と昇格させたプロパティに関連付けるファイルを指定します。  
  
 固定文字列またはドキュメント内の XML データから派生した名前には、ファイル名を設定できます。 名前を派生すると、標準の命名規則を適用する非常に便利なことができます。 アダプターは昇格させた設定も列の値として、ファイルのプロパティの値。 ファイル名と同様、昇格させたプロパティの値は修正できます。 またはドキュメント内の XML データから派生できます。  
  
> [!IMPORTANT]
>  Windows SharePoint Services アダプターで昇格させたプロパティは、BizTalk Server で、昇格させたプロパティ、または Windows SharePoint Services での昇格させたプロパティとは異なるものです。  
  
 Windows SharePoint Services の昇格させたプロパティは、Windows SharePoint Services フォーム ライブラリを参照するときに、XML 要素を表示する使用されます。 Windows SharePoint Services フォーム ライブラリに InfoPath フォームが発行されるは、自動的に実行されるため、主要な要素を昇格させるようフォーム ライブラリが構成されます。 InfoPath フォーム ライブラリ (InfoPath フォームを同一の XSD スキーマと InfoPath ソリューションを保存するドキュメント ライブラリ) を使用する場合にのみ、この機能は Windows SharePoint Services で使用できます。  
  
 Windows SharePoint Services アダプターのプロパティの昇格には、スキーマが異なるドキュメントが同じドキュメント ライブラリに格納されている場合は、Windows SharePoint Services にプロパティを昇格させるユーザーができるようにします。  
  
 BizTalk Server のプロパティの昇格は、同様の概念、のみ、メッセージのプロパティとしてオーケストレーションと、UI でエンドユーザーにプロパティを表示が行われる。 さらに、BizTalk Server は、プロパティ値が、ドキュメントに保存されるとき、プロパティの降格の概念をサポートします。  
  
 InfoPath フォームおよびフォーム ライブラリ (はなく、任意の XML およびドキュメント ライブラリを)、Windows SharePoint Services アダプターを使用する場合は、送信アダプターを使って昇格させたプロパティを設定する必要はありません。 代わりに、(メッセージを変更することで直接にまたは降格するプロパティを介して間接的に) は、ドキュメントをオーケストレーション内で変更できます。 値は、Windows SharePoint Services によって自動的に昇格されます。  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターのセキュリティに関する考慮事項  
 Windows SharePoint Services アダプターは、サブシステム、Windows SharePoint Services Web サイトで実行される BTSharePointAdapterWS Web サービスと、BizTalk Server ホスト インスタンス プロセス内の BizTalk server で実行されるアダプタ ランタイムで構成されます。 アダプタ ランタイムから呼び出す BTSharePointAdapterWS Web サービス Windows SharePoint Services 内の特定のタスクを実行する権限が必要です。 このコンポーネントは、呼び出し元として実行される、ので、アクセス許可は、呼び出し元に付与する必要があります。 つまり、BizTalk ホスト インスタンスを行う必要があります、**共同作成者**そのサイトからメッセージを送受信するには、SharePoint サイト。 BTSharePointAdapterWS Web サービスは、のメンバーでのみ呼び出すことができます、 **SharePoint Enabled Hosts**グループ。 アダプター ランタイムや、Web サービスとの対話を実行する BizTalk ホスト インスタンスを許可するためにホスト インスタンスの Windows アカウント行う必要がありますのメンバー、 **SharePoint Enabled Hosts**グループ。 アカウント、SharePoint のメンバーを追加し、ホスト インスタンスを作成したり、このグループにもからアカウントを削除するには、管理者の責任は**共同作成者**ロール。  
  
|コンポーネント|プロセス id|権限|  
|---------------|----------------------|----------------|  
|BTSharePointAdapterWS Web サービス|呼び出し元 id|SharePoint Enabled Hosts グループに付与されたアクセス許可を呼び出す|  
|アダプター ランタイム|BizTalk ホストの id|なし|  
|Windows SharePoint Services オブジェクト モデル|なし|SharePoint Enabled Hosts グループのメンバーである必要があります、**共同作成者**SharePoint Services のロール。|  
  
 BizTalk Server セットアップではアカウントのみのメンバーであるように BTSharePointAdapterWS Web サービスのアクセス許可を構成、 **SharePoint Enabled Hosts**グループがこの Web サービスにアクセスできます。 管理者がホストに関連付けられた NT グループを追加する必要が、Windows SharePoint Services アダプターを実行するホストを実行する場合に、 **SharePoint Enabled Hosts**グループを追加したり、 **SharePoint Enabled Hosts**グループ、Windows SharePoint Services に**共同作成者**ロール。  
  
 Windows SharePoint Services ファイル、リスト、およびドキュメント ライブラリへのアクセス許可は、Windows SharePoint Services のセキュリティを使用して制限されます。 メッセージは、Windows SharePoint Services から直接 BizTalk Server に送信されます。 アダプタ ランタイムと Web サービスの間の通信は、HTTP または HTTPS で行われます。  
  
 アダプターでは、BTSharePointAdapterWS Web サービスが Windows SharePoint Services サイトと同じ HTTP スキーム (HTTP または HTTPS) を使用することを前提としています。 つまり、アダプターが HTTPS を使用して、Windows SharePoint Services サイトがセキュリティで保護された IIS Web サイトで作成されるか、BTSharePointAdapterWS Web との通信に HTTP が使用される場合に、BTSSharePointAdapterWS Web サービスと通信サービスに、Windows SharePoint Services サイトは、サーバー証明書がない IIS Web サイトに作成されます。  
  
## <a name="see-also"></a>参照  
 [設定して、Windows SharePoint Services アダプターを展開します。](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターの構成](../core/configuring-the-windows-sharepoint-services-adapter.md)   
 [Windows SharePoint Services アダプターのチュートリアル](../core/windows-sharepoint-services-adapter-walkthroughs.md)