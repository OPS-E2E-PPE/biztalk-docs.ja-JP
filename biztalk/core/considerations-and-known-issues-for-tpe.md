---
title: 考慮事項と既知の問題を TPE の |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, known issues
- planning, Tracking Profile Editor
- Tracking Profile Editor, planning
ms.assetid: e96d85e0-e9ae-434a-b54e-5950f4a2b9c6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41f728126f14193ad8fc584a94574dab61f7140f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996875"
---
# <a name="considerations-and-known-issues-for-tpe"></a>TPE の考慮事項と既知の問題
追跡プロファイルと TPE を操作する際に留意しなければならない点は次のとおりです。  
  
## <a name="naming-folders-in-the-tpe"></a>TPE でのフォルダー名の付け方  
 追跡プロファイル エディターでフォルダーに名前を付ける場合は、次の命名規則に従ってください。  
  
-   フォルダー名とデータ項目インスタンス値を合わせた長さは 128 文字を超えないようにする必要があります。  
  
-   Continuation および ContinuationID フォルダーの場合、フォルダーの名前付けは、2 つのオーケストレーションを相関付ける際に非常に重要になります。 たとえば、オーケストレーション A がオーケストレーション B の親である場合、オーケストレーション A には、オーケストレーション B 内の ContinuationID フォルダーに直接マップされる名前を持つ Continuation フォルダーが含まれています。  
  
## <a name="developing-orchestrations-for-the-tpe"></a>TPE のオーケストレーションの開発  
 無効な図形で開始する、または終了するビジネス アクティビティにオーケストレーションをマップすることはできません。 オーケストレーション エンジンでは、一部の図形を追跡できない場合があります。 これらは次のとおりです。  
  
- メッセージの割り当て  
  
- 変換  
  
- グループ (タスク)  
  
- [中断]  
  
- ループ (While)  
  
- 分岐  
  
- 終了  
  
- スロー  
  
- キャッチ  
  
- While 図形  
  
  追跡プロファイル エディターやその他の BAM ツールでビジネス アクティビティを利用できるように、ビジネス アクティビティへのマップを行う場合は、次のガイドラインに従ってください。  
  
- グループ図形の場合は、トランザクション以外のスコープ図形を使用します。  
  
- While 図形の場合は、トランザクション以外のスコープ図形内にラップします。  
  
- 終了図形の場合、通常のシナリオでは終了図形の End イベントが発生しないので、回避策はありません。  
  
- ドラッグ アンド ドロップ操作が許可されていない図形を使用してスケジュールの開始または終了を行わないでください。  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a>実行中のプロセスを監視する追跡プロファイルの適用  
 追跡プロファイルを更新する場合に、アクティビティに BAM の Continuation が含まれていると、実行中のアクティビティ インスタンスに影響することがあります。 具体的には、追跡プロファイルの更新によって、既に記録されているアクティビティ項目に対してデータの下流傍受が指定されると、元の値が上書きされる可能性があります。 各ストリーム オブジェクトは、アクティビティまたはストリームが開始された時点で配置されたプロファイルの特定のバージョンに関連付けられているため、すべての単一のイベント ストリームは、実質的には追跡プロファイルの更新対象のアプリケーションによる影響を受けません。 ただし、Continuation は複数のイベント ストリームを関連付ける手段なので、プロファイルの更新の時点でまだ開始されていなかったストリームは、更新中に変更内容を取得します。その結果、上記のようなデータの上書きが発生する可能性があります。 Continuation の詳細については、[アクティビティ Continuation](../core/activity-continuation.md)と[Continuation を作成する方法](../core/how-to-create-a-continuation.md)を参照してください。  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a>メッセージ プロパティを作成するときの起点となる送信図形や受信図形のないプロファイルの追跡  
 Continuation は、アクティビティ間で共通するコンテキスト プロパティまたはペイロード データを通じてアクティビティを追跡するプロセスです。 メッセージ ID、サービス ID、インスタンス ID などのプロパティの値は、アクティビティ間で変化します。  
  
 このようなシナリオを処理する追跡プロファイルは、次の方法で作成できます。  
  
-   動的バインドを通じてあるオーケストレーションから別のオーケストレーションにメッセージが送信される場合、グローバルな一意のペイロード データ値を Continuation に使用できます。  
  
-   メッセージ内に一意のペイロード データが含まれていない場合は、メッセージのインターチェンジ ID を使用できます。 インターチェンジ ID を使用するには、これを同じ受信図形上で追跡する必要があります。 新しいメッセージを作成する場合はインターチェンジ ID が変更されるため、インターチェンジ ID を使用してメッセージを新規作成することはできません。 受信図形または送信図形以外の図形からインターチェンジ ID を追跡すると、信頼性が低下します。  
  
-   また、パイプライン経由で受信されたものとまったく同じメッセージをオーケストレーション内で使用する限り、つまり、オーケストレーション ポートがパイプラインにバインドされており、受信図形とメッセージ ID がその場所から追跡される場合に限り、メッセージ ID を使用することもできます。 異なる図形からメッセージ ID を追跡すると、そのメッセージ ID は無効となり、Continuation で使用できなくなります。  
  
-   オーケストレーションが別のオーケストレーションを呼び出してメッセージが渡されないかオーケストレーションが別のオーケストレーションを呼び出しますが、呼び出し先のコンストラクトでは、受信、または送信図形ペイロード データ値を取得できる。 場合、ユーザーは、インスタンス ID を使用できます。 呼び出されたオーケストレーションのインスタンス ID を指定することは変わりません。  
  
-   オーケストレーションが、直接呼び出しではなく実行呼び出しによって別のオーケストレーションを読み込む場合は、静的メッセージ プロパティを使用してアクティビティを追跡することはできません。 つまり、Continuation を有効にすることはできません。 このようなオーケストレーション インスタンスで追跡を実行する唯一の方法は、追跡の実行対象となる一意のペイロード データを含んでいるパイプラインを経由してメッセージを渡すことです。  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a>パススルー パイプラインの場合、継続トークンとしてセッション ID を使用できない  
 追跡プロファイルでは、メッセージ ペイロードから項目を選択すると、追跡プロファイルはそのメッセージのスキーマにバインドされます。 パススルー パイプライン内では、スキーマ名の値が NULL 値となります。 BAM が、ポート名別およびスキーマ名別に構成を読み込もうとした場合、セッション ID スキーマとの照合を行うことはできず、エンジンによるデータ追跡は行われません。  
  
 パススルー パイプラインの場合、追跡プロファイルからすべてのペイロード追跡を削除できます。また、ペイロード データの追跡が必要であれば、XML パイプラインの使用も可能です。  
  
## <a name="using-unique-port-names"></a>一意のポート名の使用  
 双方向ポートを列挙する場合、TPE により、ポートは 2 つの論理ポート (送信ポートと受信ポート) として表示されます。 これらの各論理ポートは、同じ名前で表示されます。 BizTalk Server では、一方向ポートと双方向ポートを同じ名前で作成できます。 たとえば、"Port1" という名前の双方向ポートを作成してから、同じ名前の受信ポートを作成できます。 この場合、TPE には受信ポートは一度だけ表示され、双方向は 2 回 (1 回は受信ポートとして、もう 1 回は送信ポートとして) 表示されます。  
  
 TPE は、この場合、両方の受信ポートに追跡プロファイルを適用します。 識別しやすいように、ポートには一意の名前を割り当てるようにしてください。  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a>最初の図形が平行図形である TPE オーケストレーションの使用  
 分岐図形、平行図形、待ち受け図形が含まれたオーケストレーションを開始する場合、いずれかの分岐にアクティビティ ID をマップすることはできません。 平行処理の場合は、分岐図形の上層にアクティビティ ID をマップできます。 また、BAM によってアクティビティ ID を生成し、オーケストレーションの最上層で平行図形の問題を回避することもできます。  
  
> [!IMPORTANT]
>  アクティビティを複数のパスにマップするだけでなく、分岐図形のいずれかのパスにアクティビティ ID をマップすると、アクティビティ ID がマップされていないパスに沿って処理が進められた場合にエラーが発生します。  
  
## <a name="availability-of-message-properties-at-design-time"></a>デザイン時のメッセージ プロパティの可用性  
 追跡プロファイルを作成する際、一部のメッセージ プロパティを利用できない場合があります。 たとえば、メッセージ プロパティのマップ元となる図形がオーケストレーションの最上部に位置している場合などです。 このようなオーケストレーション インスタンスでは、メッセージ プロパティの値は NULL 値になります。  
  
 その例として、待ち受け図形がオーケストレーションの最初の図形である場合が挙げられます。 この図形からメッセージのプロパティがマップされているだけで、次のプロパティ値がある場合: InstanceID、ServiceID、ServiceClassID します。 ただし、MessageID はこの時点ではスコープ外となるので、NULL 値を持ちます。  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a>ループ図形内部の図形をマップしてマイルストーンを報告することはできない  
 TPE では、ループ図形内部にあるソースを、ループ図形外部の項目にマップされているアクティビティに割り当てることはできません。  
  
 ループ アクティビティとは、オーケストレーション内でループ処理される、つまり反復するアクションのことです。 オーケストレーション内でループ処理されるアクションからイベントをキャプチャできます。 この操作を行うには、アクティビティをもう 1 つ作成し、ループ内の新しいアクティビティ マイルストーンとデータのすべてをマップします。 ループ内でのデータ処理は、スケジュールされた実行ごとに 1 回以上行われるので、この操作が必要です。  
  
 たとえば、ループ内で処理される複数の品目を注文した場合のような質問「どの注文書は、100 ドルの価格がある」でしょうか。 あいまいになります。 質問を明確にすると、次のようになります。  
  
 価格が 100 ドルの品目があるのはどの注文書か  
  
 合計/最低/最高 100 ドルの価格があるのはどの注文書か  
  
 明確な質問を作成するには、注文書とは別のものとして品目を考える必要があります。 追跡プロファイル エディターでは、ルート アクティビティ (注文書など) はループの外側のすべてのアクションにマップされます。 子アクティビティ (品目など) はループ内のアクションにマップされます。  
  
 このような構造を操作するには、通常、反復ループを分解し、外部アクティビティに関連付けられている内部アクティビティに基づいて関連アクティビティを作成します。  
  
 ルート アクティビティの ActivityID としてペイロード項目を使用し、このペイロード項目を、ループ内部の一部のメッセージで利用できるようにする必要があります。 子アクティビティの下に表示されるリレーションシップ ノードにアクティビティをマップし、ルート アクティビティとして名前を付けます。  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a>複数のアプリケーションにまたがるプロファイルの追跡  
 追跡プロファイルが複数のアプリケーションにまたがっている場合、追跡プロファイルは、ソリューション内のすべてのアプリケーションが展開された後に展開する必要があります。 追跡プロファイルが展開されている最後の項目ではない場合、次のメッセージを受信は"**マッピング ソースが見つかりません。**"展開ウィザードが BTTDeploy.exe を呼び出すときに、します。  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a>複数の BizTalk Server アイテムのドキュメント参照 URL または MessageID ノードへのマップ  
 TPE では、複数の BizTalk Server アイテムを同じドキュメント参照 URL ノードや MessageID ノードにドラッグ アンド ドロップできます。  
  
 複数のソースが BAM アクティビティ内の同じ項目にマップされている場合、BAM 処理時に発生した最後のアイテムが追跡データに保持され、BAM ポータルで表示可能になります。  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a>BizTalk ソリューション バージョンに合わせた BTT バージョンの更新  
 BAM 開発者や管理者は、BTT ファイルを自動更新することにより、追跡プロファイルと BizTalk ソリューションのバージョン同期を維持できます。 これを行うには、変更、**バージョン**属性、 **DataLevel** BTT ファイルの要素。 次の例では、TargetAssemblyName および SchemaName 属性を使用してバージョン情報を変更します。  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a>TPE で一部のオーケストレーション図形を追跡できない  
 オーケストレーション エンジンは次の図形についてイベントを生成できないので、これらの図形を TPE で追跡またはマップすることはできません。  
  
-   タスク  
  
-   すべての分岐  
  
-   [中断]  
  
-   終了  
  
-   スロー  
  
-   キャッチ  
  
-   メッセージの割り当て (構築図形に含まれているため)  
  
-   変換 (構築図形に含まれているため)  
  
-   ループ  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a>追跡プロファイルを取得しない TPE のデプロイ  
 アップグレードまたは再展開の後、展開された追跡プロファイルを取得できない場合があります。 これは、BizTalkMgmtDb データベースがレジストリ内に保存されているサーバー名に不一致があるために発生します。  
  
 BizTalkMgmtDb は、グループの構成中にレジストリに書き込まれます。 TPE はエントリを使用して、プライマリ インポート データベースを検索し、追跡プロファイルをフィルター処理します。  
  
 構成中、サーバー名は複数の形式で入力できます。 以下に例を示します。  
  
- mgmtsvr1316267,15001\inst  
  
- MGMTSVR1316267\inst,15001  
  
  TPE は、レジストリ エントリの使用時に基本的な文字列比較を実行します。 格納されたサーバーとデータベースの名前を検査し、それらを TPE で入力する必要が展開された追跡プロファイルを取得する**管理データベースの設定** ダイアログ ボックス。  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a>サーバー名とデータベース名の構文を確認して、それを、BizTalk 管理データベースに入力するには  
  
1. 開く、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**カスタム構成マネージャ**します。 使用方法について、**カスタム構成マネージャ**を参照してください[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。  
  
2. ナビゲーション ウィンドウで選択**グループ**グループの構成 ページを開きます。  
  
3. **データ ストア**グリッドの形式を確認、**サーバー名**と**データベース名**します。  
  
4. TPE を開き、選択、**ツール**メニュー項目。  
  
5. 選択、**管理データベースの設定**メニュー項目を開く、**管理データベースの設定** ダイアログ ボックス。  
  
6. **SQL Server**テキスト ボックスで使用されたサーバー名を入力、**サーバー名**のフィールド、**データ ストア**gridon、**カスタム構成マネージャ**グループ ページ。  
  
7. **データベース名**テキスト ボックスで使用されていたデータベース名を入力、**データベース名**のフィールド、**データ ストア**gridon、**カスタム構成Manager**グループ ページ。  
  
8. をクリックして、 **OK**エントリを保存するボタンをクリックします。  
  
## <a name="see-also"></a>参照  
 [TPE の使用](../core/using-the-tpe.md)   
 [Xml-data Reduced を参照してください。](../core/tracking-profile-editor.md)