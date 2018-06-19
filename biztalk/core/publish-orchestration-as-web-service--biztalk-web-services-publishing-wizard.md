---
title: 公開ウィザード Web サービスとしてのオーケストレーションを公開するサービスを BizTalk Web を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, about BizTalk Web Services Publishing Wizard
- orchestrations, publishing
ms.assetid: d990f8e4-88ce-4718-8a94-63796b8d92dc
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c86721091b9a0c9e8436b42a7489e228dbb7e0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25975344"
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-an-orchestration-as-a-web-service"></a>BizTalk Web サービス公開ウィザードを使用してオーケストレーションを Web サービスとして公開する方法
BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開することができます。  
  
> [!NOTE]
>  BizTalk Web サービス公開ウィザードを実行する前に、BizTalk プロジェクトをビルドする必要があります。  
  
> [!NOTE]
>  コマンド ライン ツール BTSWebSvcPub.exe を使用して、オーケストレーションを Web サービスとして公開できます。 詳細については、次を参照してください。 [BTSWebSvcPub コマンド ライン リファレンス](../core/btswebsvcpub-command-line-reference.md)です。  
  
### <a name="to-publish-an-orchestration-as-a-web-service"></a>オーケストレーションを Web サービスとして公開するには  
  
1.  をクリックして **開始**, 、 をポイント **すべてのプログラム**, 、 をポイント **Microsoft BizTalk Server**, 、 をクリックし、 **BizTalk Web サービス公開ウィザード**します。  
  
2.  **BizTalk Web サービス公開ウィザードへようこそ** ] ページで [ **次**します。  
  
3.  **Web サービスの作成**  ページで、 **BizTalk オーケストレーション web サービスとして発行**, 、 をクリックし、 **次**します。  
  
4.  **BizTalk アセンブリ**  ページで、BizTalk アセンブリ ファイルで (\*.dll) テキスト ボックスで、BizTalk アセンブリ ファイルの名前を入力するか、をクリックして **参照**  をクリックし、オーケストレーションを含むアセンブリを参照 **次**します。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを選択する前に、すべての依存アセンブリを BizTalk アセンブリと同じフォルダーにコピーするか、依存アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールします。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを GAC にインストールする場合で選択するアセンブリを GAC にアセンブリが更新されたこと確認、 **BizTalk アセンブリ**  ダイアログ ボックス。 GAC の完全修飾名が同じである場合、BizTalk Web サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
    > [!NOTE]
    >  オーケストレーションを含む Visual Studio で BizTalk Web サービス公開ウィザードを開くと、BizTalk アセンブリ ファイルが、オーケストレーションを含むアセンブリを使用して作成されます。  
  
    > [!NOTE]
    >  260 文字を超えるパスを指定すると、パスが長すぎることを示すエラー メッセージが表示される場合があります。  
  
5.  **オーケストレーションとポート**  ページで、プラス記号をクリックして各アセンブリおよびオーケストレーションのツリー ノードを展開します。 対応するツリー ノードのチェック ボックスをオンにして、公開するオーケストレーションとポートを選択します。 ごとに 1 つの Web サービスではなく、選択した受信ポートの受信ポートを選択、すべての 1 つの Web サービス (.asmx) を作成する場合、 **選択されているすべてのポートを 1 つの web サービスに結合** にして、をクリックし、 **次**します。  
  
    > [!NOTE]
    >  選択したすべてのポートを 1 つの Web サービスに結合すると、それらのポートの種類は同じで、ポートの操作名は一意になります。  
  
6.  **Web サービスのプロパティ**  ページで、 **web サービスのターゲット名前空間** ボックスで、Web サービスのターゲット名前空間を入力して、SOAP ヘッダーと、Web サービスの SharePoint Portal Server 2007 シングル サインオン (SSO) サポート、ウィザードがどのように処理するかを指定する適切なボックスをオンにします。 Web サービスの実装をさらにカスタマイズする場合は、クリックして **詳細**  ボタンをクリックします。 次の詳細設定オプションが表示されます。  
  
    |オプション|値|Description|  
    |------------|-----------|-----------------|  
    |SOAP パラメーターの書式|既定値|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)です。|  
    |SOAP パラメーターの書式|Bare|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)です。|  
    |SOAP パラメーターの書式|Wrapped|SOAP メッセージ内におけるパラメーターの書式を指定します。 詳細についてを参照してください SoapParameterStyle Enumeration [ http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259)です。|  
    |適合性表示|なし|バインド要求が準拠する Web サービスの相互運用性 (WSI) 仕様を指定します。 詳細については、「WebServiceBindingAttribute.ConformsTo プロパティを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)です。|  
    |適合性表示|WS-I 基本プロファイル 1.1|バインド要求が準拠する Web サービスの相互運用性 (WSI) 仕様を指定します。 詳細については、「WebServiceBindingAttribute.ConformsTo プロパティを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064)です。|  
    |要求 - 応答を強制|[Default]|一方向の BizTalk 操作を要求 - 応答 Web メソッドとして公開するかどうかを指定します。 既定では、一方向のフラグは強制されません。|  
    |要求 - 応答を強制|いいえ|一方向の BizTalk 操作を要求 - 応答 Web メソッドとして公開するかどうかを指定します。 既定では、一方向のフラグは強制されません。|  
    |要求 - 応答を強制|はい|一方向の BizTalk 操作を要求 - 応答 Web メソッドとして公開するかどうかを指定します。 既定では、一方向のフラグは強制されません。|  
  
7.  **Web サービスのプロパティ** ] ページで [ **次**します。  
  
    > [!NOTE]
    >  選択した SOAP ヘッダー オプションは、このウィザードのインスタンスの実行中に作成されるすべての Web サービスと Web メソッドにグローバルに適用されます。  
  
8.  選択した場合は **追加の SOAP ヘッダーを追加** オプション、 **要求 SOAP ヘッダー** と **応答 SOAP ヘッダー** ページが表示されます。 リストにログインを追加したりを使用して要求と応答の SOAP ヘッダーを削除する、 **追加** と **削除** 次のダイアログ ボックスにボタン。  
  
    -   SOAP ヘッダーを追加する をクリックして **追加**します。 **BizTalk アセンブリ ファイル (\*.dll)** テキスト ボックスで、型または SOAP ヘッダー スキーマを含むアセンブリを参照します。 **利用可能なスキーマ型** リスト ビューには、スキーマの場合は、各ルート要素が表示されます。 要求または応答の SOAP ヘッダーとして追加するルート ノードを選択します。 複数の項目を選択する、CTRL キーを押しながらクリックして **OK**します。  
  
    -   一覧から SOAP ヘッダーを削除するに追加された SOAP ヘッダーの一覧から選択し、 **削除**します。  
  
    -   をクリックして **次** 各 **SOAP ヘッダー** ウィザードを続行するページです。  
  
    > [!NOTE]
    >  ターゲットの名前空間とルート要素名によって SOAP ヘッダーが定義されます。  
  
    > [!NOTE]
    >  対象となる名前空間とルート要素名の同じ組み合わせを要求および応答 SOAP ヘッダーとして追加すると、受信および送信ヘッダーとして扱われません。 オーケストレーション内で受信ヘッダーを送信ヘッダーに手動でコピーする必要があります。  
  
    > [!NOTE]
    >  対象となる名前空間とルート要素名の同じ組み合わせは、要求 SOAP ヘッダーとして 1 度、応答 SOAP ヘッダーとして一度だけ追加できます。  
  
9. **Web サービス プロジェクト**  ページで、 **プロジェクト名** テキスト ボックスに、プロジェクトの名前を入力します。 既定の場所を受け入れることができます (http://localhost/<*project_name*>)、プロジェクトの場所を入力、**プロジェクトの場所**テキスト ボックス、またはをクリックして**参照**とWeb ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    -   **既存のプロジェクトを上書きします。** : このオプションは、プロジェクトの場所が既に存在する場合にのみ使用できます。 このオプションを選択する場合は、同じ場所に発行することのみできます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    -   **Web サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
    -   **BizTalk を作成する受信場所。** このオプションでは、生成された各 .asmx ファイルに対応する SOAP アダプターの受信ポートと受信場所が自動的に作成されます。 受信場所が既に存在する場合、既存の受信場所は置き換えられません。 SOAP アダプターを解決する形式を使用して、受信場所/\<*仮想ディレクトリ名*\>/\<*オーケストレーション namespace_typename_portname* \>.asmx です。 このオプションの選択後、受信ポートと場所を生成するアプリケーションを選択します。  
  
        > [!NOTE]
        >  プロジェクトの場所には、別のサーバーを指定することもできます。 別のサーバーに Web サービスを発行するとしてプロジェクト名を入力**http://&lt です*servername*>/<*project_name*>** です。  
  
        > [!NOTE]
        >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。 たとえば、 http://localhost:8080/< *project_name*>。  
  
        > [!NOTE]
        >  ウィザードを使用して受信場所を作成する場合は、既定値を使用して受信場所が作成されます。 受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** パイプラインです。 公開された Web サービスを通じて受信するメッセージには、特別なパイプライン処理が必要がある場合 (たとえば、検証、関連付け/プロパティの昇格、または受信/送信マップ) に、受信パイプラインを設定する必要があります **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, 、またはカスタム パイプラインにします。  
  
        > [!NOTE]
        >  オーケストレーションから (呼び出し) Web サービスを使用する際、SOAP アダプターはパススルー スタイルの送信パイプラインのみをサポートします。 カスタム送信パイプラインを使用できますをメッセージのボディ部を変更するコンポーネントを含めることはできません。 これらのコンポーネントには、XML アセンブラーおよびエンコード コンポーネントが含まれます。  
  
        > [!NOTE]
        >  このページにアクセスするときに選択した方をキャンセルする場合を選択して **web サービスとしてのスキーマの公開** オプションの **Web サービス**  ページの表示が、 **Web サービスの説明** からを選択する前に以前 BizTalk アセンブリからサービスおよびメソッド名が表示されます **BizTalk オーケストレーション web サービスとして発行** オプション。 これは、公開方法が変更されても、メモリ内の Web サービスの説明はクリアされないためです。  
  
10. クリックして **次** ASP.NET Web サービス プロジェクトの設定を確認します。  
  
11. クリックして **作成** ASP.NET Web サービスを作成します。  
  
12. をクリックして **完了** BizTalk Web サービス公開ウィザードを完了します。  
  
> [!NOTE]
>  オーケストレーションを Windows Vista で Web サービスとして公開している場合、サービスをホストする仮想ディレクトリを更新する必要があります。 コマンド プロンプトから次のコマンドを発行するには、置換\<vdir\>仮想ディレクトリの名前に置き換えます: **%systemroot%\system32\inetsrv\appcmd です。EXE 構成の移行"Default Web Site/\<vdir 名前\>"** です。  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)   
 [オーケストレーションを Web サービスにマップする方法](../core/how-to-map-orchestrations-to-web-services.md)