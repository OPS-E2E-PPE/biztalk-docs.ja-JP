---
title: '方法: LDAP クエリを使用する電子メール アドレスにメッセージを動的にルーティングするスケジュールを作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a2237b76524488d7a3903468ebb321d19ae623
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987603"
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a>方法: LDAP クエリを使用する電子メール アドレスにメッセージを動的にルーティングするスケジュールを作成
## <a name="goal"></a>[目標]  
 このセクションでは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 経由の電子メール アドレスを照会し、BizTalk Server の SMTP アダプターを使用してエンドポイントを解決する電子メール メッセージを送信するスケジュールを作成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   LDAP クエリを使用してメッセージを動的にルーティングするスケジュールの回覧先を作成します。  
  
-   旅行プランのテスト用クライアントのサンプル アプリケーションを使用して、旅行プランをテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)します。  
  
 このセクションを実行するコンピューターで Microsoft Active Directory ディレクトリ サービスを構成し、実行されている必要があります (でないために必要なコンピューターがドメイン コント ローラーが、そのドメインに接続する必要があります)。 SMTP サーバーを構成および実行して; にある必要がありますも、このトピックの結果をテストするために、ESB によって送信された電子メールをチェックすると、クライアントが必要です。  
  
 このセクションの手順には、globalbank.com のドメインと Active Directory 組織単位に Employees という名前 (などの自分のプロファイルで有効な電子メールアドレスを持つJohnEvansをという名前のユーザーを含むGlobalBankをという名前の組織が想定していますjohne@globalbank.com). これらの環境要因をレプリケートする必要はありません。ただし、この実装で、環境を再作成するために、これらの要因を考慮してください、必要に応じて置換を行います。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a>ESB スケジュール オンランプ ドメイン固有言語 (DSL) モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントして、**追加**、順にクリックします**新しい行程**します。  
  
3.  **新しい項目の追加**ダイアログ ボックスに「 **LdapResolution**で、**名前**ボックスをクリックして**追加**します。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行プランのプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックします。 **LdapResolution.itinerary**します。 **LdapResolution**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストでは、をクリックして**XML 行程エクスポーター**します。  
  
    2.  下、**エクステンダー設定**セクションで、横に、**旅行プラン XML ファイル**プロパティ、省略記号ボタン (…) をクリックします。  
  
    3.  **XML ファイルの**ダイアログ ボックスに「 **C:\HowTos\Itineraries\LdapResolution**で、**ファイル名**ボックスをクリック**保存**します。  
  
        > [!NOTE]
        >  この手順では、旅行プランを XML としてローカル ファイルの場所にエクスポートすることができます。 行程データベースの代わりにスケジュールをローカル ファイルの場所にエクスポートして、ESB のテスト用クライアント アプリケーションを使用してスケジュールのテストが可能です。 この操作方法に関するトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行プランの構造を定義するには  
  
1. ツールボックスからドラッグ、**入口**デザイン サーフェイスにモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
   1.  をクリックして、**名前**プロパティ、および入力**ReceiveNAOrder**します。  
  
   2.  **エクステンダー**ドロップダウン リストでは、をクリックして**入口 ESB エクステンダー**します。  
  
   3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB**します。  
  
   4.  **受信ポート**ドロップダウン リストでは、をクリックして**OnRamp.Itinerary**します。  
  
2. ツールボックスからドラッグ、**行程サービス**の右側に配置し、デザイン画面に要素をモデル化し、**入口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
   1.  をクリックして、**名前**プロパティ、および入力**RouteMessageEmail**します。  
  
   2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**エクステンダーのメッセージング**します。  
  
       > [!NOTE]
       >  このプロパティは、プロセスが行われる (メッセージング) パイプラインで定義します。 または、プロセスはオーケストレーション内の場所を受け取らない場合は設定、**行程サービス エクステンダー**プロパティを**オーケストレーション エクステンダー**します。  
  
   3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、 をクリックし、**受信ハンドラー**。  
  
   4.  **サービス名**ドロップダウン リストでは、をクリックして**Microsoft.Practices.ESB.Services.Routing**します。  
  
3. 右クリックし、**リゾルバー**のコレクション、 **RouteMessageEmail**モデル要素をクリックして**新しいリゾルバーを追加**します。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
   1.  をクリックして、**名前**プロパティ、および入力**LdapResolver**します。  
  
   2.  **リゾルバーの実装**ドロップダウン リストでは、をクリックして**LDAP 競合回避モジュールの拡張機能**します。  
  
   3.  **トランスポート名**ドロップダウン リストでは、をクリックして**SMTP**します。  
  
   4.  をクリックして、**トランスポート場所**プロパティ、および入力 **{メール}**  
  
   5.  をクリックして、 **SearchRoot**プロパティ、および入力**ou = 従業員、dc = globalbank、dc = com**  
  
       > [!NOTE]
       >  「前提条件」セクションでは、仕様に従って、環境設定が、場合は、上記プロパティ値環境に適したしたもので置き換えます。  
  
   6.  をクリックして、**フィルター**プロパティに値を変更して **(&(objectClass=User) (&#124;(givenName = john)))**  
  
       > [!NOTE]
       >  既存のテキストを置き換えるには、上記の値を入力します。  
  
   7.  **ThrowErrorIfNotFound**ドロップダウン リストでは、をクリックして**True**します。  
  
4. [プロパティ] ウィンドウ、**エンドポイント構成**プロパティ、省略記号ボタン (…) を順にクリックします。  
  
   1. **エンドポイント構成**ダイアログ ボックスで、をクリックして、 **EmailBodyText**プロパティ、および入力**注文を処理する準備が**します。  
  
   2. をクリックして、**から**プロパティ、および入力 <strong>orders@globalbank.com</strong>します。  
  
   3. をクリックして、 **MessagePartsAttachment**プロパティ、および入力**2**します。  
  
   4. をクリックして、**サブジェクト**プロパティ、および入力 **{givenName} ため**。  
  
   5. 構成、 **SMTPAuthentication、SMTPHost、ユーザー名、** と**パスワード**プロパティは、ローカル環境の接続情報を使用します。  
  
   6. をクリックして**OK**を閉じる、**エンドポイント構成** ダイアログ ボックス。  
  
5. 右クリックし、 **LdapResolver**リゾルバー、およびクリック**テスト構成の競合回避モジュール**します。  
  
6. [出力] ウィンドウで、解決のサブジェクトを確認します**エンドポイント構成**値は**john 順序**、ことを確認します、解決**トランスポート場所**が、。電子メール アドレスを Active Directory でユーザーのアカウントに関連付けられている (たとえば、 johne@globalbank.com)。  
  
7. ツールボックス、**コネクタ**します。 接続をドラッグして、 **ReceiveNAOrder**モデル要素に、 **RouteMessageEmail**モデル要素。  
  
8. ツールボックスからドラッグして、**傾斜オフ**の右側に配置し、デザイン画面に要素をモデル化し、 **RouteMessageEmail**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
   1.  をクリックして、**名前**プロパティ、および入力**EmailNAOrderDoc**します。  
  
   2.  **エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ ESB エクステンダー**します。  
  
   3.  **BizTalk アプリケーション**ドロップダウン リストでは、をクリックして**GlobalBank.ESB**します。  
  
   4.  **送信ポート**ドロップダウン リストでは、をクリックして**DynamicResolutionOneWay**します。  
  
9. ツールボックスからドラッグ、**スケジュール サービス**モデルのデザイン画面に要素との間に配置し、 **RouteMessageEmail**モデル要素と**EmailNAOrderDoc**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  をクリックして、**名前**プロパティ、および入力**SendPortFilter**します。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストでは、をクリックして**傾斜オフ エクステンダー**。  
  
    3.  **傾斜オフ**ドロップダウン リストで、展開**EmailNAOrderDoc**、順にクリックします**送信ハンドラー**します。  
  
10. ツールボックス、**コネクタ**します。 接続をドラッグして、 **RouteMessageEmail**モデル要素に、 **SendPortFilter**モデル要素。  
  
11. ツールボックス、**コネクタ**します。 接続をドラッグして、 **SendPortFilter**モデル要素に、 **EmailNAOrderDoc**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>旅行プランのテスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **LdapResolution**旅行プランをクリックして**モデルのエクスポート**します。  
  
    > [!NOTE]
    >  旅行プランの XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクト成果物を保存します。  
  
3.  Windows エクスプ ローラーでは、C:\HowTos\Itineraries を参照し、旅行プラン XML (LdapResolution.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行プランをテストするには  
  
1.  中に作成されたショートカットを使用してスケジュールのテスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB します。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントでオフ、 **WCF サービスを使用して**チェック ボックスをオンにし**ロード行程**。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**LdapResolution.xml**、順にクリックします**オープン**旅行プランを読み込めません。  
  
4.  をクリックして**OK**をオフに、**旅行プランは正常に読み込まれる**メッセージ。  
  
5.  旅行プランのテスト クライアントで、横にある省略記号ボタン (…) をクリックします。、**ロード メッセージ**ボックス。  
  
6.  **を読み込む XML ドキュメントの選択** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリックします**オープン**テスト メッセージを読み込めません。  
  
7.  をクリックして、**要求を提出**ボタンをクリックします。 テストが完了したら、クリックして**OK**表示される確認メッセージを無視します。  
  
8.  Microsoft Outlook Express (または任意のメール クライアント) を開き John Evans の電子メールへのメッセージの配信を確認します。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)