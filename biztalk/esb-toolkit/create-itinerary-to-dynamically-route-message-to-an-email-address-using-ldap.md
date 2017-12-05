---
title: "方法: 動的に LDAP クエリを使用する電子メール アドレスにメッセージをルーティングする日程を作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d9929dd-5e45-4b0d-90df-52a35e68b0ba
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751eaf381b762372652bb77ddf6f00ffe43971c2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-create-an-itinerary-to-dynamically-route-a-message-to-an-email-address-using-an-ldap-query"></a>方法: 動的に LDAP クエリを使用する電子メール アドレスにメッセージをルーティングする日程を作成します。
## <a name="goal"></a>[目標]  
 このセクションでは、LDAP (ライトウェイト ディレクトリ アクセス プロトコル) 経由での電子メール アドレスにクエリを実行し、BizTalk Server SMTP アダプタを使用してエンドポイントを解決する電子メール メッセージを送信する旅程を作成する方法を示します。  
  
 このトピックでは、次の手順を行います。  
  
-   LDAP クエリを使用してメッセージを動的にルーティングする itinerary 回覧を作成します。  
  
-   行程テスト用クライアントのサンプル アプリケーションを使用して旅程をテストします。  
  
## <a name="prerequisites"></a>前提条件  
 この操作方法に関するトピックの手順の完了が必要、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)です。  
  
 このセクションを完了するが、コンピューターに Microsoft Active Directory ディレクトリ サービスを構成しを実行している必要があります (にないために必要なコンピューターがドメイン コント ローラーがドメインに接続されている必要があります)。 また、SMTP サーバーがあります構成され、実行中です。このトピックの結果をテストするために、ESB によって送信された電子メールをチェックすると、クライアントが必要です。  
  
 このセクションの手順には、組織 globalbank.com のドメインと、Active Directory Employees という名前を含む組織単位 (など、プロファイル内の有効な電子メールアドレスにJohnEvansをという名前のユーザーとグローバルBankをという名前が想定していますjohne@globalbank.com). これらの環境的要因をレプリケートする必要はありません。ただし、環境内には、この実装を再作成するためには、これらの要因を考慮してください、必要に応じて置換を行います。  
  
## <a name="steps"></a>手順  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model"></a>ESB itinerary ドメイン固有言語 (DSL) モデルを作成するには  
  
1.  Visual Studio で、C:\HowTos\Patterns\Patterns.sln を開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ItineraryLibrary**プロジェクトをポイントし、**追加**、クリックして**新しい行程**です。  
  
3.  **新しい項目の追加** ダイアログ ボックスで、「 **LdapResolution**で、**名前**ボックスをクリックしてして**追加**です。  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>旅行計画のプロパティを構成するには  
  
1.  Visual Studio でのデザイン画面をクリックして**LdapResolution.itinerary**です。 **LdapResolution**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  **モデル エクスポーター**ドロップダウン リストをクリックして**XML 行程エクスポーター**です。  
  
    2.  下にある、 **Extender の設定**セクションで、次に、**行程 XML ファイル**プロパティ、省略記号ボタン (...) をクリックします。  
  
    3.  **[XML ファイルの**] ダイアログ ボックスで、「 **C:\HowTos\Itineraries\LdapResolution**で、**ファイル名**ボックスをクリックして**保存**です。  
  
        > [!NOTE]
        >  この手順では、旅行計画をローカル ファイルの場所に XML としてエクスポートすることができます。 代わりに、ローカル ファイルの場所に日程を itinerary のデータベースにエクスポートして ESB のテスト用クライアント アプリケーションを使用して旅行計画のテストを有効にします。 このトピックの後半には、このプロセスを完了します。  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>旅行計画の構造を定義するには  
  
1.  ツールボックスからドラッグして、**入り口**デザイン画面にモデル要素。 **OnRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**ReceiveNAOrder**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**入り口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**Microsoft.Practices.ESB**です。  
  
    4.  **受信ポート**ドロップダウン リストをクリックして**OnRamp.Itinerary**です。  
  
2.  ツールボックスからドラッグ、**行程サービス**デザイン画面に要素をモデル化の右側に配置し、**入り口**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**RouteMessageEmail**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**エクステンダーのメッセージング**です。  
  
        > [!NOTE]
        >  このプロパティは、あるプロセスで行われます (メッセージング) パイプラインを定義します。 または、プロセスは、オーケストレーションで行われます、設定、**行程サービス エクステンダー**プロパティを**オーケストレーション Extender**です。  
  
    3.  **コンテナー**ドロップダウン リストで、展開**ReceiveNAOrder**、クリックして**受信ハンドラー**です。  
  
    4.  **サービス名**ドロップダウン リストをクリックして**Microsoft.Practices.ESB.Services.Routing**です。  
  
3.  右クリックし、**リゾルバー**のコレクション、 **RouteMessageEmail**モデル要素をクリックして**新しいリゾルバーを追加**です。 **Resolver1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**LdapResolver**です。  
  
    2.  **リゾルバーの実装**ドロップダウン リストをクリックして**LDAP 競合回避モジュールの拡張機能**します。  
  
    3.  **トランスポート名**ドロップダウン リストをクリックして**SMTP**です。  
  
    4.  クリックして、**トランスポート場所**プロパティ、および入力**{メール}**  
  
    5.  クリックして、 **SearchRoot**プロパティ、および入力**ou = 従業員、dc = globalbank、dc = com**  
  
        > [!NOTE]
        >  「前提条件」セクションで、仕様に従って環境を設定してされていない場合は、環境に適しているもので、上記プロパティ値を置き換えます。  
  
    6.  をクリックして、**フィルター**プロパティに値を変更し、 **(&(objectClass=User) (&#124;(givenName=john)))**  
  
        > [!NOTE]
        >  既存のテキストを置き換える前の値を入力します。  
  
    7.  **ThrowErrorIfNotFound**ドロップダウン リストをクリックして**True**です。  
  
4.  [プロパティ] ウィンドウでをクリックして、**エンドポイント構成**プロパティ、省略記号ボタン (...) をクリックします。  
  
    1.  **エンドポイント構成**ダイアログ ボックスで、をクリックして、 **EmailBodyText**プロパティ、および入力**注文を処理する準備が**です。  
  
    2.  クリックして、**から**プロパティ、および入力 **orders@globalbank.com**です。  
  
    3.  クリックして、 **MessagePartsAttachment**プロパティ、および入力**2**です。  
  
    4.  クリックして、**サブジェクト**プロパティ、および入力**{givenName} の順序**です。  
  
    5.  構成、 **SMTPAuthentication、smtphost の各ユーザー名、**と**パスワード**プロパティは、ローカル環境の接続情報を使用します。  
  
    6.  をクリックして**OK**を閉じる、**エンドポイント構成** ダイアログ ボックス。  
  
5.  右クリックし、 **LdapResolver**リゾルバーをクリックして**テスト構成の競合回避モジュール**です。  
  
6.  [出力] ウィンドウで、解決済みの対象者を確認してください**エンドポイント構成**値は**john 順序**、ことを確認は解決された**トランスポート場所**は、。電子メール アドレスを Active Directory のユーザーのアカウントに関連付けられている (たとえば、 johne@globalbank.com)。  
  
7.  ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **ReceiveNAOrder**モデル要素を**RouteMessageEmail**モデル要素。  
  
8.  ツールボックスからドラッグして、**出口**デザイン画面に要素をモデル化の右側に配置し、 **RouteMessageEmail**モデル要素。 **OffRamp1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**EmailNAOrderDoc**です。  
  
    2.  **Extender**ドロップダウン リストをクリックして**出口 ESB Extender**です。  
  
    3.  **BizTalk アプリケーション**ドロップダウン リストをクリックして**GlobalBank.ESB**です。  
  
    4.  **送信ポート**ドロップダウン リストをクリックして**DynamicResolutionOneWay**です。  
  
9. ツールボックスからドラッグ、**行程サービス**モデルをデザイン画面に要素との間に配置し、 **RouteMessageEmail**モデル要素と**EmailNAOrderDoc**モデル要素。 **ItineraryService1**プロパティ ウィンドウで、次のプロパティを構成します。  
  
    1.  クリックして、**名前**プロパティ、および入力**SendPortFilter**です。  
  
    2.  **行程サービス エクステンダー**ドロップダウン リストをクリックして**出口 Extender**です。  
  
    3.  **出口**ドロップダウン リストで、展開**EmailNAOrderDoc**、クリックして**送信ハンドラー**です。  
  
10. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **RouteMessageEmail**モデル要素を**SendPortFilter**モデル要素。  
  
11. ツールボックスで、をクリックして**コネクタ**です。 接続をドラッグして、 **SendPortFilter**モデル要素を**EmailNAOrderDoc**モデル要素。  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>行程テスト クライアントで使用するモデルをエクスポートするには  
  
1.  Visual Studio でのデザイン画面を右クリックし、 **LdapResolution**行程をクリックして**モデルのエクスポート**です。  
  
    > [!NOTE]
    >  旅行計画の XML バージョンは、Visual Studio で開きます。  
  
2.  すべてのプロジェクトの成果物を保存します。  
  
3.  Windows エクスプローラで、C:\HowTos\Itineraries を参照し、行程 XML (LdapResolution.xml) の作成に注意してください。  
  
#### <a name="to-test-the-itinerary"></a>旅行計画をテストするには  
  
1.  中に作成されたショートカットを使用して行程テスト用クライアントのサンプル アプリケーションを開く、[開発活動の前提条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB です。Itinerary.Test.exe - ショートカット)。  
  
2.  行程テスト クライアントで、クリア、**を使用して WCF サービス**チェック ボックスをクリックして**ロード行程**です。  
  
3.  **行程ファイルを開く** ダイアログ ボックスで、C:\HowTos\Itineraries を参照します。 選択**LdapResolution.xml**、順にクリック**開く**日程を読み込めません。  
  
4.  をクリックして**OK**をクリアする、**行程が正常に読み込まれる**メッセージ。  
  
5.  行程テスト クライアントで、横にある省略記号ボタン (...) をクリックして、**メッセージの読み込み**ボックス。  
  
6.  **選択読み込む XML ドキュメントを** ダイアログ ボックスで、C:\HowTos を参照します。 選択**NAOrderDoc.xml**、順にクリック**開く**テスト メッセージを読み込めません。  
  
7.  クリックして、**要求を提出**ボタンをクリックします。 テストが完了したらをクリックして**OK**表示される確認メッセージを破棄します。  
  
8.  Microsoft Outlook Express (または任意のメール クライアント) を開くし、John Evans の電子メールへのメッセージの配信を確認してください。  
  
## <a name="additional-resources"></a>その他のリソース  
 詳細については、次の関連項目を参照してください。  
  
-   [開発アクティビティ](../esb-toolkit/development-activities.md)  
  
-   [動的な解決とルーティングを利用する](../esb-toolkit/using-dynamic-resolution-and-routing.md)