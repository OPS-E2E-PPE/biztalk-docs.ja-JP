---
title: BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, WCF services
- tools, WCF Service Publishing Wizard
- publishing, schemas [WCF services]
- WCF services, schemas
- WCF Service Publishing Wizard
ms.assetid: 3b770fd5-5b7b-493f-9016-d7d58854c5ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4079486e7dc225793f0620dfb52a7c6fdbf02899
ms.sourcegitcommit: 9b93ee2a019bef8d482626cf5525a6b95509b135
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2018
ms.locfileid: "42709895"
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-schemas-as-wcf-services"></a>BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法
スキーマを WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。  
  
> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。 BizTalk プロジェクトには、WCF サービスとして公開するスキーマを含める必要があります。  
  
### <a name="to-publish-schemas-as-wcf-servicees"></a>スキーマを WCF サービスとして公開するには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk WCF サービス公開ウィザード**します。  
  
   > [!NOTE]
   >  BizTalk のオーケストレーションおよびスキーマを作成し、WCF アダプターを使用して WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。 一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。  
  
2. **BizTalk WCF サービス公開ウィザードへようこそ**] ページで [**次**します。  
  
3. **WCF サービスの種類**] ページで、[、**サービス エンドポイント**選択した BizTalk オーケストレーションを BizTalk アセンブリ内で WCF サービスを発行するオプション。  
  
    ![WCF サービスの種類ページ](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4. **WCF サービスの種類**ページ、オンまたはオフ、**メタデータ エンドポイントを有効にする**分離 WCF の受信場所のインターネット インフォメーション サービス (IIS) によってホストされているかどうかを示すチェック ボックスを発行します。HTTP GET 要求を使用した取得用サービスのメタデータ。  
  
    ウィザードを Web.config ファイルを生成する、このチェック ボックスがオンの場合、 **httpGetEnabled**の属性、 **\<serviceMetadata\>** に要素が設定されている**true**します。 メタデータ インポート ツール (SvcUtil.exe など) を使用すると、開発環境でこのサービスを呼び出すために必要なクライアント コードを生成できます。 メタデータが公開されるアドレスは、エンドポイント アドレスと **? wsdl**クエリ文字列。  
  
   > [!NOTE]
   >  可能性のある機密性の高いサービス メタデータが誤って漏洩を防ぐためには、運用環境では、この動作を無効にすることをお勧めします。 これは、httpgetenabled を false に設定するか、MEX 仮想ディレクトリを削除して実行できます。  
  
5. **WCF サービスの種類**] ページの [、**アダプター名 (トランスポートの種類)** ドロップダウン リストで、WCF サービスを発行する際の分離 WCF アダプターを選択します。 以下のいずれかのアダプターを選択できます。  
  
   -   **Wcf-basichttp します。** : WCF-BasicHttp 受信アダプターは、ASMX ベースのサービスなど WS-I 基本プロファイル 1.1 準拠の Web サービスと通信できます。  
  
   -   **Wcf-wshttp します。** : WCF-WSHttp アダプターは、HTTP および HTTPS を使用し WS-* 標準をとおしてサービスと通信できます。  
  
   -   **Wcf-customisolated します。** : WCF-CustomIsolated アダプターを使用すると、HTTP トランスポートで WCF (Windows Communication Foundation) の拡張機能を利用できるようになります。  
  
6. **WCF サービスの種類** ページで、、**次のアプリケーションを作成する BizTalk 受信場所**受信ポートと受信の各生成 .svc ファイルに対応する場所を作成する チェック ボックス選択した WCF アダプター、**アダプター名**ドロップダウン リスト。 受信場所が既に存在する場合、既存の受信場所は置き換えられません。 このオプションを選択した後、アプリケーションで、受信ポートと受信場所が生成される場所を選択、 **BizTalk アプリケーション名**ドロップダウン リスト、およびクリック **[次へ]** します。  
  
7. **WCF サービスの作成**] ページで、[**スキーマを WCF サービスとして公開**、順にクリックします**次**します。  
  
    ![WCF サービス ページを作成する](../core/media/717db27a-2843-4950-899d-0946460f5c1f.gif "717db27a-2843-4950-899d-0946460f5c1f")  
  
8. **WCF サービス**ページで、公開する WCF サービスを定義します。 ツリーを使用して、 **Web サービスの説明**を追加、削除、名前の変更、および公開する WCF サービスの Web サービス説明ノードの編集 ダイアログ ボックス。 **情報** ダイアログ ボックス、選択したノードに関する情報を提供し、現在のノードまたはサブノードでエラーが表示されます。  
  
   -   ツリーのルート ノード (Web サービスの説明) は、公開する WCF サービスについての説明です。 仮想ディレクトリ名では、ルート ノードが既定の名前として使用されます。 選択して公開する WCF サービスの Web サービス説明の名前を変更する**web サービスの説明の名前を変更**します。  
  
        ![WCF サービス ページ](../core/media/35131a58-dae7-45fe-ac6a-928c8570f27d.gif "35131a58-dae7-45fe-ac6a-928c8570f27d")  
  
   -   Web メソッド ノード**Operation1**、既定のサービス ノードの**Service1**で既定で表示されて、 **Web サービスの説明**のダイアログ ボックスを使用することができます、要求-応答の受信場所。 一方向の WCF について、このサービスの説明の受信場所が、既定の Web メソッド ノードを右クリックして、をクリックしてで発行する予定の場合**web メソッドの削除**、し、次のように、一方向の Web メソッドを作成します既定のサービスを右クリック。ノードを指す**web メソッドを追加**、 をクリックし、**一方向**。  
  
   -   新しい WCF サービスを追加する Web サービス説明の名前を右クリックし、 **web サービスの追加**します。 これにより、WCF 操作なしの新しい WCF サービスが作成されます。 WCF サービスの名前を変更、WCF サービスのノードを右クリックし、をクリックする**web サービスの名前を変更**、し、enter キーを押して新しい名前を受け入れます。  
  
   -   新しい WCF 操作を追加するには、WCF サービスのノードを右クリックし、 をポイント**Web メソッドの追加**、順にクリックします**一方向**(要求 WCF 操作の場合) 用または**要求-応答**(用、要求-応答 WCF 操作)。  
  
   -   要求と応答スキーマの種類を設定するには、右、**要求**または**応答**ノードをクリック**スキーマの種類の選択**します。 **要求メッセージの種類**] ダイアログ ボックスに、ドキュメント スキーマを格納しているアセンブリの名前を入力、 **BizTalk アセンブリ ファイル**テキスト ボックスまたは [**参照**を検索するにはアセンブリ。 **使用可能なスキーマ型**リスト ビューには、スキーマの場合は、各ルート要素が表示されます。 要求または応答のスキーマの種類として追加するルート ノードを選択します。  
  
       > [!NOTE]
       >  BizTalk アセンブリ ファイルをグローバル アセンブリ キャッシュ (GAC) にインストールした場合に選択するアセンブリを GAC にアセンブリが更新されたこと確認、**要求メッセージの種類** ダイアログ ボックス。 GAC の完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
        ![要求メッセージの種類 ページ](../core/media/6bb4cc17-b108-4692-a5ca-548c7ef46045.gif "6bb4cc17-b108-4692-a5ca-548c7ef46045")  
  
   -   名前を変更することができます、**要求**と**応答**ノードは、生成されたコードには影響しません。 スキーマを定義した後で部分要素の名前を変更すると、WCF 操作パラメーターの名前が変更されます。 公開する WCF サービスのサービス メタデータを表示することで、変更内容を確認できます。  
  
       > [!NOTE]
       >  Web サービス説明ノードの名前を変更するとき、空白文字は使用できません。  
  
9. クリックして**次**ウィザードを続行します。  
  
10. **WCF サービスのプロパティ**] ページの [、 **WCF サービスの Targetnamespace**テキスト ボックスに、WCF サービスは、ターゲットの名前空間を入力し、順にクリックします**次**。  
  
     ![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. **WCF サービスの場所**ページで、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。 既定の場所を受け入れることができます (`http://localhost/<Web service description name>`)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはクリック**参照**Web ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    - **既存のプロジェクトを上書きします。** : このオプションは、Web ディレクトリが存在する場合のみ選択できます。 このオプションを選択すると、同じ場所にのみ公開できます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    - **WCF サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
      このページを終了したらクリックして**次**します。  
  
      ![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  プロジェクトの場所には、別のサーバーを指定することもできます。 WCF サービスを別のサーバーに発行するには、としてプロジェクト名を入力`http://<servername>/<WCF service location>`します。  
  
    > [!NOTE]
    >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。 たとえば、 `http://<servername>:8080/<WCF service location>` のようにします。  
  
    > [!NOTE]
    >  ウィザードを使用して受信場所を作成する場合は、既定値を使用して受信場所が作成されます。 受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**パイプライン。 公開された WCF サービスを通じて受信するメッセージが、特別なパイプライン処理 (たとえば、検証、関連付け/プロパティの昇格、または受信/送信マップ) を必要とする場合には、受信パイプラインを設定する必要があります**Microsoft.BizTalk.DefaultPipelines.XMLReceive**、または BizTalk 管理コンソールを使用してカスタム パイプラインです。  
  
12. **WCF サービスの概要** ページで、WCF サービスの設定を確認します。  
  
13. クリックして**作成**WCF サービスを作成します。  
  
14. クリックして**完了**BizTalk WCF サービス公開ウィザードを完了します。  
  
15. BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開した後、これらのサービスを適切に構成する必要があります。 分離 WCF を構成する方法については、受信アダプターを参照してください[BizTalk WCF サービス公開ウィザードで WCF サービス公開を構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードで公開した WCF サービスを構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [チュートリアル: Wcf-basichttp アダプターを使用した WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)