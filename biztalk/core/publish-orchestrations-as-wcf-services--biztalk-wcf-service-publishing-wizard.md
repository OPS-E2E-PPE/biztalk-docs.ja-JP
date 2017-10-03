---
title: "BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tools, WCF Service Publishing Wizard
- WCF services, WCF Service Publishing Wizard
- WCF services, orchestrations
- publishing, orchestrations [WCF services]
- orchestrations, WCF services
- WCF Service Publishing Wizard
ms.assetid: db352132-2fe8-4d53-b239-45e5c3525b6c
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88c3ce33f413a55fbf756aecfb054e66e5d3599c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-biztalk-wcf-service-publishing-wizard-to-publish-orchestrations-as-wcf-services"></a>BizTalk WCF サービス公開ウィザードを使用してオーケストレーションを WCF サービスとして公開する方法
オーケストレーションを WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。  
  
> [!NOTE]
>  BizTalk WCF サービス公開ウィザードを実行する前に、BizTalk プロジェクトを作成する必要があります。 BizTalk プロジェクトには、型修飾子がパブリックである受信ポートを 1 つ以上持つオーケストレーションが含まれている必要があります。 この型修飾子は、ポートが作成されたときのオーケストレーションのプロパティに存在します。  
  
### <a name="to-publish-an-orchestration-as-a-wcf-service"></a>オーケストレーションを WCF サービスとして公開するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、順にクリック**BizTalk WCF サービス公開ウィザード**です。  
  
    > [!NOTE]
    >  BizTalk のオーケストレーションおよびスキーマを作成し、WCF アダプターを使用して WCF サービスとして公開するには、BizTalk WCF サービス公開ウィザードを使用します。 一方、SOAP アダプターを使用してオーケストレーションとスキーマを Web サービスとして公開するには、BizTalk Web サービス公開ウィザードを使用します。  
  
2.  **BizTalk WCF サービス公開ウィザードへようこそ** ページで、をクリックして**次**です。  
  
3.  **WCF サービスの種類**] ページで、[**サービス エンドポイント**選択した BizTalk オーケストレーションを BizTalk アセンブリ内で WCF サービスを公開するにはオプションです。  
  
     ![WCF サービスの種類ページ](../core/media/959900fd-44c9-4f3a-8836-9786a2f5e707.gif "959900fd-44c9-4f3a-8836-9786a2f5e707")  
  
4.  **WCF サービスの種類**] ページで、[**メタデータ エンドポイントを有効にする**チェック ボックスを分離された WCF の受信場所のインターネット インフォメーション サービス (IIS) によってホストされているかどうかを示すためにサービス メタデータを公開します。HTTP/GET 要求を使用して取得します。 このチェック ボックスを有効にすると、ウィザードに Web.config が生成されますここで、 **httpGetEnabled**の属性、  **\<serviceMetadata >**要素がに設定されている**true**。. メタデータ インポート ツール (SvcUtil.exe など) を使用すると、開発環境でこのサービスを呼び出すために必要なクライアント コードを生成できます。 メタデータが公開されるアドレスは、エンドポイント アドレスと**? wsdl**クエリ文字列。  
  
    > [!NOTE]
    >  機密性の高いサービス メタデータが誤って公開されないように、実稼働環境ではこの動作を無効にすることをお勧めします。 これは、httpgetenabled を false に設定、または、MEX 仮想ディレクトリを削除して実行できます。  
  
5.  **WCF サービスの種類**] ページの [、**アダプター名 (トランスポートの種類)**ドロップダウン リストで、WCF サービスの公開に使用する分離 WCF アダプターを選択します。 以下のいずれかのアダプターを選択できます。  
  
    -   **Wcf-basichttp です。** : WCF-BasicHttp 受信アダプターは、ASMX ベースのサービスなど WS-I 基本プロファイル 1.1 準拠の Web サービスと通信できます。  
  
    -   **Wcf-wshttp です。** : WCF-WSHttp アダプターは、HTTP および HTTPS を使用し WS-* 標準をとおしてサービスと通信できます。  
  
    -   **Wcf-customisolated です。** : WCF-CustomIsolated アダプターを使用すると、HTTP トランスポートで WCF (Windows Communication Foundation) の拡張機能を利用できるようになります。  
  
6.  **WCF サービスの種類**] ページで、[、**次のアプリケーションに作成する BizTalk 受信場所**チェック ボックスを受信ポートと各生成された .svc ファイルに対応する場所を作成するには選択した WCF アダプターの**アダプター名**ドロップダウン リスト。 受信場所が既に存在する場合、既存の受信場所は置き換えられません。 このオプションを選択すると後で、受信ポートと受信場所が生成する、アプリケーションを選択、 **BizTalk アプリケーション名**クリックしてドロップダウン リスト、**次**です。  
  
7.  **WCF サービスの作成**] ページで、[ **BizTalk オーケストレーションの WCF サービスとして発行**、クリックして**[次へ]**です。  
  
     ![WCF サービス ページを作成する](../core/media/86cb66b5-6842-4330-8942-20afa68ec5fa.gif "86cb66b5-6842-4330-8942-20afa68ec5fa")  
  
8.  **BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\*.dll)**テキスト ボックスで、BizTalk アセンブリ ファイルの名前を入力またはクリックして**参照**を参照するにはをクリックし、オーケストレーションを含むアセンブリ**次**です。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを選択する前にすべての依存アセンブリを BizTalk アセンブリと同じフォルダーにコピーまたはグローバル アセンブリ キャッシュ (GAC) に依存アセンブリをインストールします。  
  
    > [!NOTE]
    >  BizTalk アセンブリ ファイルを GAC にインストールする場合はで選択するアセンブリに GAC にアセンブリが更新されたことを確認してください、 **BizTalk アセンブリ** ダイアログ ボックス。 GAC 内のアセンブリの完全修飾名が同じである場合、BizTalk WCF サービス公開ウィザードでは、選択したアセンブリ ファイルではなく、GAC 内のアセンブリ ファイルが使用されます。  
  
    > [!NOTE]
    >  パス名が 260 文字を超えると、パス名が長すぎるというエラー メッセージが表示される場合があります。  
  
     ![BizTalk アセンブリ ページ](../core/media/d34a027e-ea82-4048-8b15-d97df795b0d4.gif "d34a027e-ea82-4048-8b15-d97df795b0d4")  
  
9. **オーケストレーションとポート** ページで、プラス記号 (+) をクリックして、各アセンブリおよびオーケストレーションのツリー ノードを展開します。 対応するツリー ノードのチェック ボックスを選択して公開するオーケストレーションとポートを選択します。 ごとに 1 つの WCF サービスではなく選択した受信ポートの受信ポートを選択、すべての 1 つの WCF サービス (.svc ファイル) を作成する場合、**選択されているすべてのポートを 1 つの WCF サービスに結合**オプションをクリックして**[次へ]**です。  
  
    > [!NOTE]
    >  選択したすべてのポートを 1 つの WCF サービスに統合すると、選択したすべてのポートの種類が同じになり、ポート内の操作名も同じになります。  
  
     ![操作とポート ページ](../core/media/97112744-ddd4-4512-ac56-41317ba9412b.gif "97112744-ddd4-4512-ac56-41317ba9412b")  
  
10. **WCF サービスのプロパティ**] ページの [、 **、WCF サービスの Targetnamespace**テキスト ボックスでは、WCF サービスのターゲットの名前空間を入力し、をクリックして**次**です。  
  
     ![WCF サービスのプロパティ ページ](../core/media/07518c78-bcae-4274-bb14-aeef107ee4c6.gif "07518c78-bcae-4274-bb14-aeef107ee4c6")  
  
11. **WCF サービスの場所**] ページの [、**場所**テキスト ボックスに、WCF サービスが生成される Web ディレクトリ名を入力します。 既定の場所を受け入れることができます (http://localhost/\<*BizTalk アセンブリ名*>)、WCF サービスの場所を入力、**場所**テキスト ボックス、またはをクリックして**参照** Web ディレクトリを選択します。 次のいずれかのオプションをクリックします。  
  
    -   **既存のプロジェクトを上書きします。** : このオプションは、Web ディレクトリが既に存在する場合にのみ使用できます。 このオプションを選択すると、同じ場所にのみ公開できます。 このオプションを選択しない場合は、別のプロジェクトの場所を入力する必要があります。  
  
    -   **WCF サービスへの匿名アクセスを許可します。** : このオプションでは、作成した仮想ディレクトリに匿名アクセスを追加します。 既定では、仮想ディレクトリは、その親仮想ディレクトリまたは Web サイト (最上位の仮想ディレクトリである場合) から、アクセス権限を継承します。  
  
     このページを終了したらクリックして**次**です。  
  
     ![WCF サービスの場所 ページ](../core/media/76285470-1520-4d77-a5b6-c58cbe8fc575.gif "76285470-1520-4d77-a5b6-c58cbe8fc575")  
  
    > [!NOTE]
    >  プロジェクトの場所には、別のサーバーを指定することもできます。 WCF サービスを別のサーバーで発行するプロジェクト名を入力として http://\<*servername*>/\<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  プロジェクトの場所には、既定以外の Web サイトを指定することもできます。 既定以外の Web サイトに公開する場合は、URL に Web サイトのポート番号を含めます。 たとえば、http://\<*servername*>: 8080/\<*WCF サービスの場所*>。  
  
    > [!NOTE]
    >  ウィザードを使用して受信場所を作成する場合は、既定値を使用して受信場所が作成されます。 受信パイプラインの既定値は、 **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**パイプライン。 公開された WCF サービスを通じて受信するメッセージには特別なパイプライン処理 (たとえば、検証、関連付け/プロパティの昇格、または受信/送信マップ) が必要な場合に、受信パイプラインを設定する必要があります**Microsoft.BizTalk.DefaultPipelines.XMLReceive**、またはカスタム パイプラインに、BizTalk Server 管理コンソールを使用します。  
  
    > [!NOTE]
    >  使用しない場合、**オーケストレーションを WCF サービスとして公開**オプションで、このページに達した後、 **WCF サービスの作成** ページの表示を**Web サービスの説明**する前に選択した BizTalk アセンブリからのサービスおよびメソッドの名前が表示されますが、発行オプションを変更します。 これは、公開方法が変更されたときにメモリ内の Web サービスの説明が削除されないためです。  
  
12. **WCF サービスの概要** ページで、WCF サービスの設定を確認します。  
  
13. をクリックして**作成**WCF サービスを作成します。  
  
14. をクリックして**完了**を BizTalk WCF サービス公開ウィザードを完了します。  
  
15. BizTalk WCF サービス公開ウィザードを使用して WCF サービスを公開した後、これらのサービスを適切に構成する必要があります。 分離 WCF を構成する方法については、受信アダプターを参照してください[BizTalk WCF サービス公開ウィザードで WCF サービス公開を構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk WCF サービス公開ウィザードで公開された WCF サービスを構成する方法](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)   
 [チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)   
 [BizTalk WCF サービス公開ウィザードを使用してスキーマを WCF サービスとして公開する方法](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)